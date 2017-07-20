---
title: ".NET Framework 中的安全性更改 | Microsoft Docs"
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
  - "允许部分受信任调用方特性"
  - ".NET Framework 4, 安全更改"
  - ".NET Framework 安全性"
  - "安全透明的代码"
  - "安全-关键代码"
  - "代码访问安全性, 更改"
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
caps.latest.revision: 52
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 52
---
# .NET Framework 中的安全性更改
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中对安全性最重要的更改是强命名。 有关这些更改的说明，请参阅[改进的强命名](../../../docs/framework/app-domains/enhanced-strong-naming.md)。  
  
 .NET Framework 为托管应用程序提供两层安全模型。[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用程序在限制访问资源的 Windows 安全容器中运行。 在该容器中，托管应用程序以完全信任方式运行。 从代码访问安全性 \(CAS\) 角度看，开发人员不可执行任何将提升特权的操作。 有关 Windows 授予的特权的信息，请参阅 Windows 开发人员中心的[应用功能声明（Windows 应用商店应用）](http://go.microsoft.com/fwlink/?LinkId=230436)。 有关创建 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用的信息，请参阅[使用 C\# 或 Visual Basic 创建第一个 Windows 应用商店应用](http://go.microsoft.com/fwlink/?LinkId=230461)。