---
title: "回调函数 | Microsoft Docs"
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
  - "回调函数"
  - "平台调用, 调用非托管函数"
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# 回调函数
回调函数是托管应用程序中可帮助非托管 DLL 函数完成任务的代码。  对回调函数的调用将从托管应用程序中，通过一个 DLL 函数，间接地传递给托管实现。  在用平台调用调用的多种 DLL 函数中，有些函数要求正确地运行托管代码中的回调函数。  
  
 要从托管代码中调用大多数 DLL 函数，可创建该函数的托管定义，然后调用该函数。  此过程比较直接。  
  
 要使用需要回调函数的 DLL 函数，则会有一些附加的步骤。  首先，必须在文档中查阅该函数，确定该函数是否需要回调。  接着，必须在托管应用程序中创建回调函数。  最后，调用该 DLL 函数，并将指向回调函数的指针当作参数进行传递。  下图总结了这些步骤。  
  
 ![平台调用回调](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")  
回调函数和实现  
  
 回调函数非常适合在重复执行任务的情况下使用。  另一个常见用途是与枚举函数（如 Win32 API 中的 **EnumFontFamilies**、**EnumPrinters** 和 **EnumWindows**）一起使用。  **EnumWindows** 函数枚举计算机上的所有现有窗口，并调用回调函数以针对每个窗口执行任务。  有关说明和示例，请参见[如何：实现回调函数](../../../docs/framework/interop/how-to-implement-callback-functions.md)。  
  
## 请参阅  
 [如何：实现回调函数](../../../docs/framework/interop/how-to-implement-callback-functions.md)   
 [调用 DLL 函数](../../../docs/framework/interop/calling-a-dll-function.md)