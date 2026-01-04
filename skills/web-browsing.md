# Web Browsing Skills

Web 浏览技能是 Agent 的核心能力之一，允许智能体访问互联网信息、搜索数据、浏览网页等。

## 📖 概述

Web 浏览技能使 AI Agent 能够：
- 搜索互联网信息
- 访问和解析网页内容
- 从网站提取数据
- 遵循链接进行导航
- 处理动态网页

## 🛠️ 主要工具和库

### 1. LangChain Web Browsing Tools

#### DuckDuckGo Search
```python
from langchain_community.tools import DuckDuckGoSearchRun

search = DuckDuckGoSearchRun()

# 基础搜索
results = search.run("Python programming tutorials")
print(results)

# 作为工具使用
from langchain.tools import Tool
tool = Tool(
    name="DuckDuckGo Search",
    func=search.run,
    description="Search the web using DuckDuckGo"
)
```

#### Google Search（需要 API Key）
```python
from langchain_community.tools import GoogleSearchAPIWrapper

search = GoogleSearchAPIWrapper(
    google_api_key="your-api-key",
    google_cse_id="your-cse-id"
)

results = search.results("AI agents", num_results=5)
```

#### Bing Search（需要 API Key）
```python
from langchain_community.utilities import BingSearchAPIWrapper

search = BingSearchAPIWrapper(
    bing_subscription_key="your-key",
    bing_search_url="https://api.bing.microsoft.com/v7.0/search"
)

results = search.run("machine learning")
```

### 2. AutoGen Web Browsing

```python
from autogen import AssistantAgent, UserProxyAgent
import requests

# 定义 Web 浏览工具
def browse_web(url: str) -> str:
    """Browse a webpage and return its content"""
    try:
        response = requests.get(url)
        return response.text[:1000]
    except Exception as e:
        return f"Error: {str(e)}"

# 创建使用工具的智能体
assistant = AssistantAgent(
    name="assistant",
    llm_config={
        "config_list": config_list,
        "functions": [
            {
                "name": "browse_web",
                "description": "Browse a webpage and return its content",
                "parameters": {
                    "type": "object",
                    "properties": {
                        "url": {
                            "type": "string",
                            "description": "The URL to browse"
                        }
                    },
                    "required": ["url"]
                }
            }
        ]
    }
)
```

### 3. CrewAI Web Browsing

```python
from crewai import Agent, Task, Crew
from crewai.tools import SerperDevTool

# 创建搜索工具
search_tool = SerperDevTool()

# 创建具备 Web 浏览能力的 Agent
researcher = Agent(
    role="Researcher",
    goal="Find information on the web",
    backstory="You are an expert researcher",
    tools=[search_tool],
    llm="gpt-4"
)

# 创建任务
task = Task(
    description="Research the latest developments in AI agents",
    agent=researcher
)

# 执行
crew = Crew(agents=[researcher], tasks=[task])
result = crew.kickoff()
```

## 🎯 高级 Web 浏览技能

### 1. 网页内容提取

#### 使用 BeautifulSoup
```python
from bs4 import BeautifulSoup
import requests

def extract_text(url: str) -> str:
    """Extract main text from a webpage"""
    response = requests.get(url)
    soup = BeautifulSoup(response.content, 'html.parser')
    
    # 移除脚本和样式
    for script in soup(["script", "style"]):
        script.decompose()
    
    # 获取文本
    text = soup.get_text()
    lines = (line.strip() for line in text.splitlines())
    chunks = (phrase.strip() for line in lines for phrase in line.split("  "))
    text = '\n'.join(chunk for chunk in chunks if chunk)
    
    return text
```

#### 使用 Trafilatura
```python
import trafilatura

def extract_article(url: str) -> str:
    """Extract article content from a webpage"""
    downloaded = trafilatura.fetch_url(url)
    result = trafilatura.extract(downloaded)
    return result
```

### 2. 多步搜索和浏览

```python
from langchain.agents import AgentType, initialize_agent, load_tools
from langchain_openai import ChatOpenAI

llm = ChatOpenAI(temperature=0)

# 加载多个搜索工具
tools = load_tools(
    ["serpapi", "requests_all"],
    serpapi_api_key="your-api-key"
)

# 创建 Agent
agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True
)

# 执行复杂搜索
result = agent.run("""
1. Search for recent news about AI agents
2. Find specific articles about LangChain
3. Summarize the key points
""")
```

### 3. 深度网页爬取

```python
import scrapy
from scrapy.crawler import CrawlerProcess

class WebSpider(scrapy.Spider):
    name = 'web_spider'
    
    def __init__(self, start_url=None, *args, **kwargs):
        super(WebSpider, self).__init__(*args, **kwargs)
        self.start_urls = [start_url] if start_url else []
    
    def parse(self, response):
        # 提取当前页面内容
        yield {
            'url': response.url,
            'title': response.css('title::text').get(),
            'content': response.css('body::text').get()
        }
        
        # 跟踪链接
        for link in response.css('a::attr(href)'):
            yield response.follow(link, self.parse)

# 运行爬虫
process = CrawlerProcess()
process.crawl(WebSpider, start_url='https://example.com')
process.start()
```

### 4. API 集成

```python
import requests

def fetch_api_data(endpoint: str, params: dict = None) -> dict:
    """Fetch data from a REST API"""
    response = requests.get(endpoint, params=params)
    if response.status_code == 200:
        return response.json()
    return {"error": f"Failed with status {response.status_code}"}

# 使用示例
data = fetch_api_data(
    "https://api.github.com/repos/langchain-ai/langchain",
    params={"state": "open"}
)
```

## 🔍 搜索策略

### 1. 多引擎搜索
```python
def multi_engine_search(query: str, engines: list) -> list:
    """Search using multiple search engines"""
    results = []
    for engine in engines:
        if engine == "duckduckgo":
            tool = DuckDuckGoSearchRun()
        elif engine == "google":
            tool = GoogleSearchAPIWrapper()
        elif engine == "bing":
            tool = BingSearchAPIWrapper()
        
        result = tool.run(query)
        results.append({
            "engine": engine,
            "results": result
        })
    
    return results

# 使用
results = multi_engine_search(
    "AI agent frameworks",
    ["duckduckgo", "google", "bing"]
)
```

### 2. 递归搜索
```python
def recursive_search(query: str, depth: int = 2, current_depth: int = 0) -> list:
    """Recursively search and explore results"""
    if current_depth >= depth:
        return []
    
    # 搜索
    search = DuckDuckGoSearchRun()
    initial_results = search.run(query)
    
    # 解析结果并递归
    results = [{"query": query, "content": initial_results}]
    
    # 如果有链接，进一步搜索
    # 这里简化处理，实际应用中需要解析URL
    if current_depth < depth - 1:
        sub_results = recursive_search(
            f"more info about {query}",
            depth,
            current_depth + 1
        )
        results.extend(sub_results)
    
    return results
```

## 🛡️ 安全考虑

### 1. 请求限制
```python
import time
from functools import wraps

def rate_limit(max_calls: int, time_frame: int):
    """Rate limiting decorator"""
    calls = []
    
    def decorator(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            now = time.time()
            
            # 清理过期调用
            calls[:] = [c for c in calls if c > now - time_frame]
            
            if len(calls) >= max_calls:
                wait_time = time_frame - (now - calls[0])
                time.sleep(wait_time)
            
            calls.append(now)
            return func(*args, **kwargs)
        
        return wrapper
    return decorator

@rate_limit(max_calls=10, time_frame=60)
def browse_url(url: str):
    """Browse URL with rate limiting"""
    return requests.get(url)
```

### 2. 验证和清理
```python
from urllib.parse import urlparse

def is_safe_url(url: str) -> bool:
    """Check if a URL is safe to visit"""
    parsed = urlparse(url)
    
    # 只允许 http 和 https
    if parsed.scheme not in ['http', 'https']:
        return False
    
    # 防止内部网络访问
    if parsed.hostname in ['localhost', '127.0.0.1']:
        return False
    
    return True

def safe_browse(url: str):
    """Safely browse a URL"""
    if not is_safe_url(url):
        raise ValueError(f"Unsafe URL: {url}")
    
    response = requests.get(url)
    return response.text
```

## 📊 性能优化

### 1. 并发请求
```python
import concurrent.futures
import requests

def parallel_fetch(urls: list, max_workers: int = 5) -> list:
    """Fetch multiple URLs in parallel"""
    results = []
    
    with concurrent.futures.ThreadPoolExecutor(max_workers=max_workers) as executor:
        future_to_url = {
            executor.submit(requests.get, url): url
            for url in urls
        }
        
        for future in concurrent.futures.as_completed(future_to_url):
            url = future_to_url[future]
            try:
                result = future.result()
                results.append({
                    "url": url,
                    "status": result.status_code,
                    "content": result.text[:500]
                })
            except Exception as e:
                results.append({
                    "url": url,
                    "error": str(e)
                })
    
    return results
```

### 2. 缓存结果
```python
import hashlib
import json
from pathlib import Path

class Cache:
    def __init__(self, cache_dir: str = "cache"):
        self.cache_dir = Path(cache_dir)
        self.cache_dir.mkdir(exist_ok=True)
    
    def _get_cache_path(self, key: str) -> Path:
        """Get cache file path for a key"""
        hashed = hashlib.md5(key.encode()).hexdigest()
        return self.cache_dir / f"{hashed}.json"
    
    def get(self, key: str):
        """Get cached value"""
        cache_path = self._get_cache_path(key)
        if cache_path.exists():
            with open(cache_path, 'r') as f:
                return json.load(f)
        return None
    
    def set(self, key: str, value):
        """Set cached value"""
        cache_path = self._get_cache_path(key)
        with open(cache_path, 'w') as f:
            json.dump(value, f)

# 使用示例
cache = Cache()

def cached_search(query: str):
    """Search with caching"""
    cached = cache.get(query)
    if cached:
        return cached
    
    search = DuckDuckGoSearchRun()
    result = search.run(query)
    
    cache.set(query, result)
    return result
```

## 🎓 最佳实践

1. **使用多个搜索源**: 不要依赖单一搜索引擎
2. **实现缓存**: 避免重复请求相同内容
3. **限制递归深度**: 防止无限循环
4. **验证 URL**: 确保只访问安全网站
5. **遵守 robots.txt**: 尊重网站的爬虫规则
6. **处理错误**: 实现健壮的错误处理
7. **控制请求频率**: 避免被网站封禁
8. **解析结构化数据**: 使用专门的解析工具提高准确性

## 🔗 相关资源

- [BeautifulSoup Documentation](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
- [Trafilatura](https://github.com/adbar/trafilatura)
- [Scrapy](https://scrapy.org/)
- [Requests Library](https://requests.readthedocs.io/)

---

**更新日期**: 2026-01-04
**版本**: v0.1
