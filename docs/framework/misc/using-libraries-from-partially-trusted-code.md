---
title: 通过部分受信任的代码使用库
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7a3bbbaa565a6c118082456a1ab6d7af59db7067
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119270"
---
# <a name="using-libraries-from-partially-trusted-code"></a><span data-ttu-id="6bf69-102">通过部分受信任的代码使用库</span><span class="sxs-lookup"><span data-stu-id="6bf69-102">Using Libraries from Partially Trusted Code</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
>  <span data-ttu-id="6bf69-103">本主题介绍强命名程序集的行为，并且仅适用于[级别 1](../../../docs/framework/misc/security-transparent-code-level-1.md)程序集。</span><span class="sxs-lookup"><span data-stu-id="6bf69-103">This topic addresses the behavior of strong-named assemblies and applies only to [Level 1](../../../docs/framework/misc/security-transparent-code-level-1.md) assemblies.</span></span> <span data-ttu-id="6bf69-104">[安全透明的代码，级别 2](../../../docs/framework/misc/security-transparent-code-level-2.md)中的程序集[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]或更高版本不受强名称。</span><span class="sxs-lookup"><span data-stu-id="6bf69-104">[Security-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md) assemblies in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] or later are not affected by strong names.</span></span> <span data-ttu-id="6bf69-105">有关安全系统更改的详细信息，请参阅[安全更改](../../../docs/framework/security/security-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="6bf69-105">For more information about changes to the security system, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="6bf69-106">不允许未从其主机或沙盒获取完全信任的应用程序调用共享的托管库，除非库编写器明确允许它们使用 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="6bf69-106">Applications that receive less than full trust from their host or sandbox are not allowed to call shared managed libraries unless the library writer specifically allows them to through the use of the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="6bf69-107">因此，应用程序编写器必须注意某些库在部分受信任的上下文中将不可用。</span><span class="sxs-lookup"><span data-stu-id="6bf69-107">Therefore, application writers must be aware that some libraries will not be available to them from a partially trusted context.</span></span> <span data-ttu-id="6bf69-108">默认情况下执行的所有代码在部分信任[沙盒](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)和并不处于完全信任程序集的列表为部分受信任。</span><span class="sxs-lookup"><span data-stu-id="6bf69-108">By default, all code that executes in a partial-trust [sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) and is not in the list of full-trust assemblies is partially trusted.</span></span> <span data-ttu-id="6bf69-109">如果不希望从部分受信任的上下文中执行或由部分受信任的代码调用自己的代码，则不必关心此部分的信息。</span><span class="sxs-lookup"><span data-stu-id="6bf69-109">If you do not expect your code to be executed from a partially trusted context or to be called by partially trusted code, you do not have to be concerned about the information in this section.</span></span> <span data-ttu-id="6bf69-110">但是，如果所编写的代码必须与部分受信任的代码进行交互或从部分受信任的上下文环境进行操作，则应考虑以下因素：</span><span class="sxs-lookup"><span data-stu-id="6bf69-110">However, if you write code that must interact with partially trusted code or operate from a partially trusted context, you should consider the following factors:</span></span>  
  
-   <span data-ttu-id="6bf69-111">为了方便多个应用程序共享库，则必须使用强名称对库进行签名。</span><span class="sxs-lookup"><span data-stu-id="6bf69-111">Libraries must be signed with a strong name in order to be shared by multiple applications.</span></span> <span data-ttu-id="6bf69-112">强名称允许你的代码可放入全局程序集缓存中或添加到沙盒处理 <xref:System.AppDomain> 的完全信任列表，并允许使用者验证实际来自你的移动代码的特定部分。</span><span class="sxs-lookup"><span data-stu-id="6bf69-112">Strong names allow your code to be placed in the global assembly cache or added to the full-trust list of a sandboxing <xref:System.AppDomain>, and allow consumers to verify that a particular piece of mobile code actually originates from you.</span></span>  
  
-   <span data-ttu-id="6bf69-113">默认情况下，强名称的[一级](../../../docs/framework/misc/security-transparent-code-level-1.md)共享的库执行隐式[LinkDemand](../../../docs/framework/misc/link-demands.md)信任自动，而无需库编写器无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="6bf69-113">By default, strong-named [Level 1](../../../docs/framework/misc/security-transparent-code-level-1.md) shared libraries perform an implicit [LinkDemand](../../../docs/framework/misc/link-demands.md) for full trust automatically, without the library writer having to do anything.</span></span>  
  
-   <span data-ttu-id="6bf69-114">如果调用方不具有完全信任但仍尝试调用这样的库，则运行时会引发 <xref:System.Security.SecurityException>，且会不允许调用方链接到库。</span><span class="sxs-lookup"><span data-stu-id="6bf69-114">If a caller does not have full trust but still tries to call such a library, the runtime throws a <xref:System.Security.SecurityException> and the caller is not allowed to link to the library.</span></span>  
  
-   <span data-ttu-id="6bf69-115">若要禁用自动**LinkDemand**并避免引发异常，可以将放置**AllowPartiallyTrustedCallersAttribute**上的共享程序集作用域的属性库。</span><span class="sxs-lookup"><span data-stu-id="6bf69-115">In order to disable the automatic **LinkDemand** and prevent the exception from being thrown, you can place the **AllowPartiallyTrustedCallersAttribute** attribute on the assembly scope of a shared library.</span></span> <span data-ttu-id="6bf69-116">此属性允许从部分受信任的托管代码调用你的库。</span><span class="sxs-lookup"><span data-stu-id="6bf69-116">This attribute allows your libraries to be called from partially trusted managed code.</span></span>  
  
-   <span data-ttu-id="6bf69-117">被授予访问具有此属性的库的权限的部分受信任代码仍将受到由 <xref:System.AppDomain> 定义的进一步限制。</span><span class="sxs-lookup"><span data-stu-id="6bf69-117">Partially trusted code that is granted access to a library with this attribute is still subject to further restrictions defined by the <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="6bf69-118">部分受信任的代码来调用一个库，它不具有任何通过编程方式**AllowPartiallyTrustedCallersAttribute**属性。</span><span class="sxs-lookup"><span data-stu-id="6bf69-118">There is no programmatic way for partially trusted code to call a library that does not have the **AllowPartiallyTrustedCallersAttribute** attribute.</span></span>  
  
 <span data-ttu-id="6bf69-119">对特定应用程序都是私有的库不需要强名称或**AllowPartiallyTrustedCallersAttribute**属性，不能引用的应用程序外部的潜在恶意代码。</span><span class="sxs-lookup"><span data-stu-id="6bf69-119">Libraries that are private to a specific application do not require a strong name or the **AllowPartiallyTrustedCallersAttribute** attribute and cannot be referenced by potentially malicious code outside the application.</span></span> <span data-ttu-id="6bf69-120">保护此类代码免受部分受信任的移动代码的有意或无意滥用，而无需开发人员进行任何额外操作。</span><span class="sxs-lookup"><span data-stu-id="6bf69-120">Such code is protected against intentional or unintentional misuse by partially trusted mobile code without the developer having to do anything extra.</span></span>  
  
 <span data-ttu-id="6bf69-121">你应该考虑显式启用以下代码类型的部分受信任代码的用法：</span><span class="sxs-lookup"><span data-stu-id="6bf69-121">You should consider explicitly enabling use by partially trusted code for the following types of code:</span></span>  
  
-   <span data-ttu-id="6bf69-122">代码已安全漏洞进行认真测试并且符合中所述的准则[安全编码准则](../../../docs/standard/security/secure-coding-guidelines.md)。</span><span class="sxs-lookup"><span data-stu-id="6bf69-122">Code that has been diligently tested for security vulnerabilities and is in compliance with the guidelines described in [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md).</span></span>  
  
-   <span data-ttu-id="6bf69-123">专门为部分受信任的情况进行编写的强名称代码库。</span><span class="sxs-lookup"><span data-stu-id="6bf69-123">Strong-named code libraries that are specifically written for partially trusted scenarios.</span></span>  
  
-   <span data-ttu-id="6bf69-124">使用强名称签名的任何组件（无论是部分或完全受信任）都将由从 Internet 下载的代码调用。</span><span class="sxs-lookup"><span data-stu-id="6bf69-124">Any components (whether partially or fully trusted) signed with a strong name that will be called by code that is downloaded from the Internet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bf69-125">.NET Framework 类库中的某些类不具备**AllowPartiallyTrustedCallersAttribute**属性，不能由部分受信任代码调用。</span><span class="sxs-lookup"><span data-stu-id="6bf69-125">Some classes in the .NET Framework class library do not have the **AllowPartiallyTrustedCallersAttribute** attribute and cannot be called by partially trusted code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf69-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bf69-126">See also</span></span>

- [<span data-ttu-id="6bf69-127">代码访问安全性</span><span class="sxs-lookup"><span data-stu-id="6bf69-127">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
