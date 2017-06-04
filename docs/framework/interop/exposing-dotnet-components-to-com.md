---
title: "向 COM 公开 .NET Framework 组件 | Microsoft Docs"
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
  - "向 COM 公开 .NET Framework 组件"
  - "与非托管代码间的互操作, 公开 .NET Framework 组件"
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# 向 COM 公开 .NET Framework 组件
对于开发人员而言，编写 .NET 类型和从非托管代码中使用该类型是截然不同的活动。  本节将介绍几条有关编写与 COM 客户端互用的托管代码的提示。  
  
-   [为互用性限定 .NET 类型](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)。  
  
     要向 COM 公开的所有托管类型、方法、属性、字段和事件都必须是公共的。  类型必须具有公共的默认构造函数，该构造函数是唯一可以通过 COM 调用的构造函数。  
  
-   [应用 Interop 特性](../../../docs/framework/interop/applying-interop-attributes.md)。  
  
     托管代码中的自定义特性可以增强组件的互用性。  
  
-   [将 COM 的程序集打包](../../../docs/framework/interop/packaging-an-assembly-for-com.md)。  
  
     COM 开发人员可能会要求您总结引用和部署程序集所涉及的步骤。  
  
 另外，本节还将说明有关从 COM 客户端使用托管类型的任务。  
  
#### 从 COM 中使用托管类型  
  
1.  [向 COM 注册程序集](../../../docs/framework/interop/registering-assemblies-with-com.md)。  
  
     程序集（和类型库）中的类型必须在设计时注册。  如果安装程序未注册程序集，应指示 COM 开发人员使用 Regasm.exe。  
  
2.  [从 COM 中引用 .NET 类型](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)。  
  
     COM 开发人员可以通过他们当前使用的相同工具和技术来引用程序集中的类型。  
  
3.  [调用 .NET 对象](http://msdn.microsoft.com/zh-cn/40c9626c-aea6-4bad-b8f0-c1de462efd33)。  
  
     COM 开发人员可以按照对任何非托管类型调用方法的相同方式来对 .NET 对象调用方法。  例如，COM **CoCreateInstance** API 将激活 .NET 对象。  
  
4.  [为 COM 访问部署应用程序](http://msdn.microsoft.com/zh-cn/fb63564c-c1b9-4655-a094-a235625882ce)。  
  
     具有强名称的程序集可以安装在全局程序集缓存中并需要其发行者的签名。  不具有强名称的程序集必须安装在客户端的应用程序目录中。  
  
## 请参阅  
 [与非托管代码交互操作](../../../docs/framework/interop/index.md)   
 [COM 互操作示例：COM 客户端和 .NET 服务器](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)