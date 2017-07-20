---
title: "启动设置架构 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "配置架构 [.NET Framework], 启动设置"
  - "架构启动设置"
  - "启动设置架构"
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 启动设置架构
启动设置指定应运行应用程序的公共语言运行时版本。  
  
|元素|说明|  
|--------|--------|  
|[\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|指定应用程序仅支持公共语言运行时 1.0 版。  用运行时 1.1 版生成的应用程序应使用 **\<supportedRuntime\>** 元素。|  
|[\<运行时\>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|指定此应用程序支持的公共语言运行时版本。|  
|[\<启动\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|包含 **\<requiredRuntime\>**和 **\<supportedRuntime\>**。|  
  
## 请参阅  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/zh-cn/c376208d-980d-42b4-865b-fbe0d9cc97c2)