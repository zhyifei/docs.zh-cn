---
title: .NET Framework 中的安全性更改
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: af2869e5ca3b41778c094b7a78a9493e74868811
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204497"
---
# <a name="security-changes-in-the-net-framework"></a>.NET Framework 中的安全性更改

.NET Framework 4.5 中对安全性的最重要的更改是强命名。 有关这些更改的说明，请参阅 [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) 。  
  
.NET Framework 为托管应用程序提供两层安全模型。 Windows 8.x 应用商店应用在限制对资源的访问权限的 Windows 安全容器中运行。 在该容器中，托管应用程序以完全信任方式运行。 从代码访问安全性 (CAS) 角度看，开发人员不可执行任何将提升特权的操作。 有关 Windows 授予的特权的信息，请参阅 Windows 开发人员中心的 [应用功能声明（Windows 应用商店应用）](https://go.microsoft.com/fwlink/?LinkId=230436) 。 有关创建 Windows 8.x 应用商店应用的信息，请参阅[使用C#或 Visual Basic 创建您的第一个 Windows 应用商店应用](https://go.microsoft.com/fwlink/?LinkId=230461)。
