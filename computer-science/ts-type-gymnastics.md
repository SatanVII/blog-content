---
title: TypeScript 类型体操入门
date: 2024-11-30
category: Note
tags:
  - TypeScript
  - 前端
description: 记录几个常用的类型工具实现。
---

类型体操的本质是在类型层面做计算。TS 的类型系统是图灵完备的，但日常只需要掌握几个模式。

## 条件类型

```ts
type IsString<T> = T extends string ? true : false

type A = IsString<'hello'> // true
type B = IsString<42> // false
```

## 映射类型

```ts
type Optional<T> = {
  [K in keyof T]?: T[K]
}
```

## 模板字面量类型

```ts
type Getter<T extends string> = `get${Capitalize<T>}`

type Name = Getter<'name'> // 'getName'
```

外部链接测试：[Astro 文档](https://docs.astro.build/)。
