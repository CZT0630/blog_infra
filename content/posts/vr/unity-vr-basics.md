---
title: "Unity VR 开发入门"
date: 2026-06-05
draft: false
categories: ["VR"]
tags: ["Unity", "VR", "XR"]
summary: "使用 Unity 开启 VR 开发之旅"
---

## 开发环境准备

1. 安装 Unity Hub
2. 安装 Unity 2022 LTS 或更高版本
3. 安装 XR Plugin Management

## 创建 VR 项目

```csharp
// 在 Unity 中创建新项目，选择 3D (URP) 模板
// 然后通过 Package Manager 安装：
// - XR Plugin Management
// - OpenXR Plugin
```

## 基本场景搭建

```csharp
using UnityEngine;
using UnityEngine.XR.Interaction.Toolkit;

public class VRSimpleGrab : MonoBehaviour
{
    private XRGrabInteractable grabInteractable;

    void Start()
    {
        grabInteractable = GetComponent<XRGrabInteractable>();
        grabInteractable.selectEntered.AddListener(OnGrab);
    }

    private void OnGrab(SelectEnterEventArgs args)
    {
        Debug.Log("物体被抓住了！");
    }
}
```

## 常用组件

| 组件 | 用途 |
|------|------|
| XR Origin | VR 玩家根节点 |
| XR Grab Interactable | 可抓取物体 |
| XR Direct Interactor | 手部直接交互 |
| XR Ray Interactor | 射线交互 |
