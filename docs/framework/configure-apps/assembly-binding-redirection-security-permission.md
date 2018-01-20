---
title: "程序集绑定重定向安全权限"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d2593df04b93db17f9ca61a98b21aaec1d534d46
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="d7d42-102">程序集绑定重定向安全权限</span><span class="sxs-lookup"><span data-stu-id="d7d42-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="d7d42-103">应用程序配置文件中的显式程序集绑定重定向需要安全权限。</span><span class="sxs-lookup"><span data-stu-id="d7d42-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="d7d42-104">这适用于对 .NET Framework 程序集和来自第三方的程序集的重定向。</span><span class="sxs-lookup"><span data-stu-id="d7d42-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="d7d42-105">通过设置授予此权限<xref:System.Security.Permissions.SecurityPermissionFlag>标志<xref:System.Security.Permissions.SecurityPermission>。</span><span class="sxs-lookup"><span data-stu-id="d7d42-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="d7d42-106">默认情况下，托管程序集具有任何权限。</span><span class="sxs-lookup"><span data-stu-id="d7d42-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="d7d42-107">安全权限授予的受信任的区域 （本地计算机） 和 Intranet 区域中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7d42-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="d7d42-108">在 Internet 区域中运行的应用程序严格禁止执行程序集绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="d7d42-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="d7d42-109">如果控制由组件的发布者，发布服务器策略文件中或由管理员控制的计算机配置文件中执行程序集重定向，则不需要的权限。</span><span class="sxs-lookup"><span data-stu-id="d7d42-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="d7d42-110">但是，权限是若要显式忽略发行者策略使用的应用需要[ \<publisherPolicy 适用 ="no"/ >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)应用程序配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="d7d42-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="d7d42-111">下表显示的默认安全设置**可**标志。</span><span class="sxs-lookup"><span data-stu-id="d7d42-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="d7d42-112">区域</span><span class="sxs-lookup"><span data-stu-id="d7d42-112">Zone</span></span>|<span data-ttu-id="d7d42-113">可标志设置</span><span class="sxs-lookup"><span data-stu-id="d7d42-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="d7d42-114">受信任的区域 （本地计算机）</span><span class="sxs-lookup"><span data-stu-id="d7d42-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="d7d42-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="d7d42-115">**ON**</span></span>|  
|<span data-ttu-id="d7d42-116">Intranet 区域</span><span class="sxs-lookup"><span data-stu-id="d7d42-116">Intranet Zone</span></span>|<span data-ttu-id="d7d42-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="d7d42-117">**ON**</span></span>|  
|<span data-ttu-id="d7d42-118">Internet 区域</span><span class="sxs-lookup"><span data-stu-id="d7d42-118">Internet Zone</span></span>|<span data-ttu-id="d7d42-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="d7d42-119">**OFF**</span></span>|  
|<span data-ttu-id="d7d42-120">不受信任的区域</span><span class="sxs-lookup"><span data-stu-id="d7d42-120">Untrusted zones</span></span>|<span data-ttu-id="d7d42-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="d7d42-121">**OFF**</span></span>|  
  
 <span data-ttu-id="d7d42-122">管理员可以更改这些安全设置以支持或限制由给定计算机上的特定方案。</span><span class="sxs-lookup"><span data-stu-id="d7d42-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="d7d42-123">没有用于更改工具**可**标志设置从默认设置; 管理员必须手动编辑用户的计算机上的 Security.config 文件。</span><span class="sxs-lookup"><span data-stu-id="d7d42-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d42-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7d42-124">See Also</span></span>  
 [<span data-ttu-id="d7d42-125">发布服务器策略文件，并通过并行执行</span><span class="sxs-lookup"><span data-stu-id="d7d42-125">Publisher Policy Files and Side-by-Side Execution</span></span>](http://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [<span data-ttu-id="d7d42-126">如何：启用和禁用自动绑定重定向</span><span class="sxs-lookup"><span data-stu-id="d7d42-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [<span data-ttu-id="d7d42-127">并行执行</span><span class="sxs-lookup"><span data-stu-id="d7d42-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
