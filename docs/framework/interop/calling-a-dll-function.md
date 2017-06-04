---
title: "调用 DLL 函数 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM 互操作, 平台调用"
  - "DLL 函数"
  - "与非托管代码间的互操作, 平台调用"
  - "平台调用, 调用非托管函数"
  - "非托管函数"
  - "非托管函数, 调用"
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 调用 DLL 函数
虽然调用非托管 DLL 函数与调用其他托管代码基本相同，但仍有一些差异会使 DLL 函数初看起来颇为费解。  本节包括以下主题，它们将说明某些与异常调用相关的问题。  
  
 从平台调用返回的结构必须为在托管和非托管代码中具有相同表示形式的数据类型。  因为这些类型不需要转换，因此称为“可直接复制到本机结构中的类型”（参见[可直接复制到本机结构中的类型和非直接复制到本机结构中的类型](../../../docs/framework/interop/blittable-and-non-blittable-types.md)）。  若要调用将非直接复制到本机结构中的结构作为其返回类型的函数，可以定义一个与非直接复制到本机结构中的类型具有相同大小的可直接复制到本机结构中的帮助器类型，并在此函数返回后转换数据。  
  
## 本节内容  
 [传递结构](../../../docs/framework/interop/passing-structures.md)  
 说明用已定义的布局传送数据结构时的问题。  
  
 [回调函数](../../../docs/framework/interop/callback-functions.md)  
 提供关于回调函数的基本信息。  
  
 [如何：实现回调函数](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 描述如何实现托管代码中的回调函数。  
  
## 相关章节  
 [使用非托管 DLL 函数](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 描述如何使用平台调用来调用非托管的 DLL 函数。  
  
 [用平台调用封送数据](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 描述如何声明方法参数以及将变量传递给由非托管库导出的函数。