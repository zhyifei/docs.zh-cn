---
title: "向 .NET Framework 公开 COM 组件 | Microsoft Docs"
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
  - "COM 互操作, 公开 COM 组件"
  - "向 .NET Framework 公开 COM 组件"
  - "与非托管代码间的互操作, 公开 COM 组件"
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 向 .NET Framework 公开 COM 组件
本节将概述向托管代码公开现有 COM 组件所需的步骤。  有关如何编写与 .NET Framework 紧密集成的 COM 服务器的详细信息，请参见[交互操作的设计注意事项](http://msdn.microsoft.com/zh-cn/b59637f6-fe35-40d6-ae72-901e7a707689)。  
  
 作为中间层商业应用程序或作为独立的功能，现有 COM 组件是托管代码中的宝贵资源。  理想的组件具有一个主 Interop 程序集，并严格符合 COM 所规定的编程标准。  
  
#### 向 .NET Framework 公开 COM 组件  
  
1.  [将类型库当作程序集导入](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)。  
  
     公共语言运行时需要所有类型（包括 COM 类型）的元数据。  您可以通过几种方法获取包含作为元数据导入的 COM 类型的程序集。  
  
2.  [在托管代码中使用 COM 类型](http://msdn.microsoft.com/zh-cn/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)。  
  
     您可以按处理任何托管类型的相同方式来检查 COM 类型、激活实例或对 COM 对象调用方法。  
  
3.  [编译 Interop 项目](../../../docs/framework/interop/compiling-an-interop-project.md)。  
  
     [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 为几种符合公共语言规范 \(CLS\) 的语言提供了编译器，这些语言包括 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]、C\# 和 C\+\+。  
  
4.  [部署 Interop 应用程序](../../../docs/framework/interop/deploying-an-interop-application.md)。  
  
     Interop 应用程序最好作为[具有强名称的](../../../docs/framework/app-domains/strong-named-assemblies.md)、带签名的程序集在全局程序集缓存中部署。  
  
## 请参阅  
 [与非托管代码交互操作](../../../docs/framework/interop/index.md)   
 [Design Considerations for Interoperation](http://msdn.microsoft.com/zh-cn/b59637f6-fe35-40d6-ae72-901e7a707689)   
 [COM 互操作示例：.NET 客户端和 COM 服务器](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)   
 [语言独立性和与语言无关的组件](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Gacutil.exe（全局程序集缓存工具）](../../../docs/framework/tools/gacutil-exe-gac-tool.md)