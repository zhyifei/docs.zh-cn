---
title: "与非托管代码交互操作 | Microsoft Docs"
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
  - ".NET Framework, 与非托管代码间的互操作"
  - "组件 [.NET Framework], 与非托管代码间的互操作"
  - "与非托管代码间的互操作"
  - "与非托管代码间的互操作, 关于互操作"
  - "托管代码, 与非托管代码间的互操作"
  - "非托管代码"
  - "非托管代码, 互操作"
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 与非托管代码交互操作
.NET Framework 将促进与 COM 组件、COM\+ 服务、外部类型库和许多操作系统服务的交互操作。  在托管和非托管对象模型之间，数据类型、方法签名和错误处理机制都存在差异。  为了简化 .NET Framework 组件和非托管代码之间的互用并便于进行迁移，公共语言运行时将从客户端和服务器中隐藏这两种对象模型之间的差异。  
  
 在运行时控制下执行的代码称作托管代码。  相反，在运行时之外运行的代码称作非托管代码。  COM 组件、ActiveX 接口和 Win32 API 函数都是非托管代码的示例。  
  
## 本节内容  
 [Interoperating with Unmanaged Code How\-to Topics](http://msdn.microsoft.com/zh-cn/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 提供指向在有关与非托管代码进行互操作的概念性文档中找到的所有帮助主题的链接。  
  
 [向 .NET Framework 公开 COM 组件](../../../docs/framework/interop/exposing-com-components.md)  
 描述如何从 .NET Framework 应用程序使用 COM 组件。  
  
 [向 COM 公开 .NET Framework 组件](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 描述如何从 COM 应用程序使用 .NET Framework 组件。  
  
 [使用非托管 DLL 函数](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 描述如何使用平台调用来调用非托管的 DLL 函数。  
  
 [互操作的设计注意事项](http://msdn.microsoft.com/zh-cn/b59637f6-fe35-40d6-ae72-901e7a707689)  
 提供有关编写集成 COM 组件的提示。  
  
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)  
 描述如何对 COM 互操作和平台调用进行封送处理。  
  
 [如何：映射 HRESULT 和异常](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 描述异常和 HRESULT 之间的映射。  
  
 [Interoperating Using Generic Types](http://msdn.microsoft.com/zh-cn/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 描述泛型类型在用于 COM 互操作时的行为。  
  
## 相关章节  
 [Advanced COM Interoperability](http://msdn.microsoft.com/zh-cn/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 提供一些链接，指向关于将 COM 组件并入 .NET Framework 应用程序中的更多信息。