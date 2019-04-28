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
ms.openlocfilehash: c62a469b3e31283e5790c747092a8fe504ef8c2a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670141"
---
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="b1d61-102">.NET Framework 中的安全性更改</span><span class="sxs-lookup"><span data-stu-id="b1d61-102">Security Changes in the .NET Framework</span></span>
<span data-ttu-id="b1d61-103">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中对安全性最重要的更改是强命名。</span><span class="sxs-lookup"><span data-stu-id="b1d61-103">The most important change to security in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is in strong naming.</span></span> <span data-ttu-id="b1d61-104">有关这些更改的说明，请参阅 [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) 。</span><span class="sxs-lookup"><span data-stu-id="b1d61-104">See [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
 <span data-ttu-id="b1d61-105">.NET Framework 为托管应用程序提供两层安全模型。</span><span class="sxs-lookup"><span data-stu-id="b1d61-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] <span data-ttu-id="b1d61-106">应用程序在限制访问资源的 Windows 安全容器中运行。</span><span class="sxs-lookup"><span data-stu-id="b1d61-106">apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="b1d61-107">在该容器中，托管应用程序以完全信任方式运行。</span><span class="sxs-lookup"><span data-stu-id="b1d61-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="b1d61-108">从代码访问安全性 (CAS) 角度看，开发人员不可执行任何将提升特权的操作。</span><span class="sxs-lookup"><span data-stu-id="b1d61-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="b1d61-109">有关 Windows 授予的特权的信息，请参阅 Windows 开发人员中心的 [应用功能声明（Windows 应用商店应用）](https://go.microsoft.com/fwlink/?LinkId=230436) 。</span><span class="sxs-lookup"><span data-stu-id="b1d61-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="b1d61-110">有关创建 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 应用的信息，请参阅 [使用 C# 或 Visual Basic 创建第一个 Windows 应用商店应用](https://go.microsoft.com/fwlink/?LinkId=230461)。</span><span class="sxs-lookup"><span data-stu-id="b1d61-110">For information about creating a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span></span>
