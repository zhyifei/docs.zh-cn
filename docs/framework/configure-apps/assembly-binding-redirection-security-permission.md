---
title: 程序集绑定重定向安全权限
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: b59689e78f901637674c0a1df28ed74411e8e7c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921376"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="e6d66-102">程序集绑定重定向安全权限</span><span class="sxs-lookup"><span data-stu-id="e6d66-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="e6d66-103">应用程序配置文件中的显式程序集绑定重定向需要安全权限。</span><span class="sxs-lookup"><span data-stu-id="e6d66-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="e6d66-104">这适用于对 .NET Framework 程序集和来自第三方的程序集的重定向。</span><span class="sxs-lookup"><span data-stu-id="e6d66-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="e6d66-105">通过在<xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission>上设置标志来授予权限。</span><span class="sxs-lookup"><span data-stu-id="e6d66-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="e6d66-106">默认情况下, 托管程序集没有权限。</span><span class="sxs-lookup"><span data-stu-id="e6d66-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="e6d66-107">此安全权限将授予受信任区域 (本地计算机) 和 Intranet 区域中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6d66-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="e6d66-108">严格禁止在 Internet 区域中运行的应用程序执行程序集绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="e6d66-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="e6d66-109">如果程序集重定向是在由组件发行者控制的发行者策略文件中执行, 或者在管理员控制的计算机配置文件中执行, 则不需要该权限。</span><span class="sxs-lookup"><span data-stu-id="e6d66-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="e6d66-110">但是, 应用程序需要权限才能使用应用程序配置文件中的[ \<publisherpolicy apply apply = "no"/>](./file-schema/runtime/publisherpolicy-element.md)元素显式忽略发布服务器策略。</span><span class="sxs-lookup"><span data-stu-id="e6d66-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="e6d66-111">下表显示了**BindingRedirects**标志的默认安全设置。</span><span class="sxs-lookup"><span data-stu-id="e6d66-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="e6d66-112">区域</span><span class="sxs-lookup"><span data-stu-id="e6d66-112">Zone</span></span>|<span data-ttu-id="e6d66-113">BindingRedirects 标志设置</span><span class="sxs-lookup"><span data-stu-id="e6d66-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="e6d66-114">受信任区域 (本地计算机)</span><span class="sxs-lookup"><span data-stu-id="e6d66-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="e6d66-115">**基于**</span><span class="sxs-lookup"><span data-stu-id="e6d66-115">**ON**</span></span>|  
|<span data-ttu-id="e6d66-116">Intranet 区域</span><span class="sxs-lookup"><span data-stu-id="e6d66-116">Intranet Zone</span></span>|<span data-ttu-id="e6d66-117">**基于**</span><span class="sxs-lookup"><span data-stu-id="e6d66-117">**ON**</span></span>|  
|<span data-ttu-id="e6d66-118">Internet 区域</span><span class="sxs-lookup"><span data-stu-id="e6d66-118">Internet Zone</span></span>|<span data-ttu-id="e6d66-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="e6d66-119">**OFF**</span></span>|  
|<span data-ttu-id="e6d66-120">不受信任区域</span><span class="sxs-lookup"><span data-stu-id="e6d66-120">Untrusted zones</span></span>|<span data-ttu-id="e6d66-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="e6d66-121">**OFF**</span></span>|  
  
 <span data-ttu-id="e6d66-122">管理员可以更改这些安全设置, 以支持或限制给定计算机上的特定方案。</span><span class="sxs-lookup"><span data-stu-id="e6d66-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="e6d66-123">没有用于更改**BindingRedirects**标志设置的默认值的工具;管理员必须手动编辑用户计算机上的安全配置文件。</span><span class="sxs-lookup"><span data-stu-id="e6d66-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d66-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6d66-124">See also</span></span>

- <span data-ttu-id="e6d66-125">[发行者策略文件和并行执行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e6d66-125">[Publisher Policy Files and Side-by-Side Execution](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span></span>
- [<span data-ttu-id="e6d66-126">如何：启用和禁用自动绑定重定向</span><span class="sxs-lookup"><span data-stu-id="e6d66-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="e6d66-127">并行执行</span><span class="sxs-lookup"><span data-stu-id="e6d66-127">Side-by-Side Execution</span></span>](../deployment/side-by-side-execution.md)
