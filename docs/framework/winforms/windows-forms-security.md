---
title: 安全性
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: a3debf487b9b2a04277d9ce3007f28662fa4899e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734500"
---
# <a name="windows-forms-security"></a><span data-ttu-id="8ac50-102">Windows 窗体安全</span><span class="sxs-lookup"><span data-stu-id="8ac50-102">Windows Forms Security</span></span>
<span data-ttu-id="8ac50-103">Windows 窗体功能是基于代码的安全模型（为代码设置安全级别，而不考虑运行代码的用户）。</span><span class="sxs-lookup"><span data-stu-id="8ac50-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="8ac50-104">这是对你的计算机系统上已有的任何安全架构的补充。</span><span class="sxs-lookup"><span data-stu-id="8ac50-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="8ac50-105">这些功能可能包括在浏览器中（例如 Internet Explorer 中提供的基于区域的安全性）或操作系统（例如，Windows NT 基于凭据的安全）。</span><span class="sxs-lookup"><span data-stu-id="8ac50-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ac50-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="8ac50-106">In This Section</span></span>  
 [<span data-ttu-id="8ac50-107">Windows 窗体中的安全性概述</span><span class="sxs-lookup"><span data-stu-id="8ac50-107">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)  
 <span data-ttu-id="8ac50-108">简要说明 .NET Framework 安全模型和确保你的应用程序中的 Windows 窗体安全所需的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="8ac50-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="8ac50-109">在 Windows 窗体中提高文件和数据访问的安全性</span><span class="sxs-lookup"><span data-stu-id="8ac50-109">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="8ac50-110">描述如何在不完全受信任的环境中访问文件和数据。</span><span class="sxs-lookup"><span data-stu-id="8ac50-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="8ac50-111">Windows 窗体中更加安全的打印</span><span class="sxs-lookup"><span data-stu-id="8ac50-111">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="8ac50-112">介绍如何在不完全受信任的环境中访问打印功能。</span><span class="sxs-lookup"><span data-stu-id="8ac50-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="8ac50-113">Windows 窗体中额外的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="8ac50-113">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="8ac50-114">介绍如何在不完全受信任的环境中执行窗口操作、使用剪贴板和调用非托管代码。</span><span class="sxs-lookup"><span data-stu-id="8ac50-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8ac50-115">相关章节</span><span class="sxs-lookup"><span data-stu-id="8ac50-115">Related Sections</span></span>  
 <span data-ttu-id="8ac50-116">[默认安全策略](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8ac50-116">[Default Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span></span>  
 <span data-ttu-id="8ac50-117">列出在完全信任、本地 Intranet 和 Internet 权限集中授予的默认权限。</span><span class="sxs-lookup"><span data-stu-id="8ac50-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 <span data-ttu-id="8ac50-118">[常规安全策略管理](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8ac50-118">[General Security Policy Administration](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span></span>  
 <span data-ttu-id="8ac50-119">提供有关管理 .NET Framework 安全策略和提升权限的信息。</span><span class="sxs-lookup"><span data-stu-id="8ac50-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="8ac50-120">危险权限和策略管理</span><span class="sxs-lookup"><span data-stu-id="8ac50-120">Dangerous Permissions and Policy Administration</span></span>](../misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="8ac50-121">讨论某些 the.NET 框架权限，这些权限可能允许规避安全系统。</span><span class="sxs-lookup"><span data-stu-id="8ac50-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="8ac50-122">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="8ac50-122">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="8ac50-123">相关主题的链接，这些主题说明了针对 .NET Framework 安全地编写代码的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="8ac50-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 <span data-ttu-id="8ac50-124">[请求权限](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8ac50-124">[Requesting Permissions](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span></span>  
 <span data-ttu-id="8ac50-125">讨论特性的用法，使运行时知道您的代码运行所需的权限。</span><span class="sxs-lookup"><span data-stu-id="8ac50-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="8ac50-126">安全性的基础概念</span><span class="sxs-lookup"><span data-stu-id="8ac50-126">Key Security Concepts</span></span>](../../standard/security/key-security-concepts.md)  
 <span data-ttu-id="8ac50-127">指向涵盖代码安全性基本方面的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="8ac50-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="8ac50-128">代码访问安全性基础知识</span><span class="sxs-lookup"><span data-stu-id="8ac50-128">Code Access Security Basics</span></span>](../misc/code-access-security-basics.md)  
 <span data-ttu-id="8ac50-129">讨论使用 .NET Framework 运行时安全策略的基本知识。</span><span class="sxs-lookup"><span data-stu-id="8ac50-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 <span data-ttu-id="8ac50-130">[确定何时修改安全策略](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8ac50-130">[Determining When to Modify Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span></span>  
 <span data-ttu-id="8ac50-131">介绍如何确定应用程序何时需要从默认安全策略中分离。</span><span class="sxs-lookup"><span data-stu-id="8ac50-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 <span data-ttu-id="8ac50-132">[部署安全策略](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8ac50-132">[Deploying Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span></span>  
 <span data-ttu-id="8ac50-133">讨论部署安全策略更改的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="8ac50-133">Discusses the best manner for deploying security policy changes.</span></span>
