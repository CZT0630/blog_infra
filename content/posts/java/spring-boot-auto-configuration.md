---
title: "Spring Boot 自动配置原理"
date: 2026-06-07
draft: false
categories: ["Java"]
tags: ["Spring Boot", "源码分析", "自动配置"]
summary: "深入理解 @EnableAutoConfiguration 的工作原理"
---

## 什么是自动配置？

Spring Boot 的核心特性之一就是**自动配置**（Auto-Configuration）。它能根据你引入的依赖，自动配置 Spring 应用。

## @SpringBootApplication 注解

```java
@SpringBootApplication
public class MyApplication {
    public static void main(String[] args) {
        SpringApplication.run(MyApplication.class, args);
    }
}
```

`@SpringBootApplication` 是一个组合注解，包含了：

- `@SpringBootConfiguration`
- `@EnableAutoConfiguration`
- `@ComponentScan`

## 自动配置的原理

1. **@EnableAutoConfiguration** 触发自动配置机制
2. 通过 `SpringFactoriesLoader` 加载 `META-INF/spring.factories` 文件
3. 根据 `@Conditional` 条件判断是否生效

```java
@AutoConfiguration
@ConditionalOnClass(DataSource.class)
@EnableConfigurationProperties(DataSourceProperties.class)
public class DataSourceAutoConfiguration {
    // 自动配置数据源
}
```

## 总结

自动配置让我们只需引入依赖，就能获得默认配置，极大简化了开发。
