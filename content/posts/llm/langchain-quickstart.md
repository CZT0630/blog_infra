---
title: "LangChain 快速入门"
date: 2026-06-06
draft: false
categories: ["AI/LLM"]
tags: ["LangChain", "LLM", "Python"]
summary: "使用 LangChain 构建你的第一个 LLM 应用"
---

## 什么是 LangChain？

LangChain 是一个用于构建 LLM 应用的框架，提供了：

- 模型调用抽象
- 链式调用（Chain）
- 记忆管理（Memory）
- 工具集成（Tools）

## 安装

```bash
pip install langchain langchain-openai
```

## 第一个示例

```python
from langchain_openai import ChatOpenAI
from langchain_core.messages import HumanMessage

llm = ChatOpenAI(model="gpt-4")
response = llm.invoke([HumanMessage(content="你好！")])
print(response.content)
```

## 使用 Chain

```python
from langchain_core.prompts import ChatPromptTemplate
from langchain_core.output_parsers import StrOutputParser

prompt = ChatPromptTemplate.from_template("用一句话解释：{topic}")
chain = prompt | llm | StrOutputParser()

result = chain.invoke({"topic": "量子计算"})
print(result)
```

## 下一步

- 学习 RAG（检索增强生成）
- 了解 Agent 和 Tools
- 探索 LangGraph 构建复杂工作流
