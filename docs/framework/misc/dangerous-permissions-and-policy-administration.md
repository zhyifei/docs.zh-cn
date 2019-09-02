---
title: 危险权限和策略管理
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ffe4f3e000c80610d5a105dddef90f9cfd51f0dc
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205583"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="9487e-102">危险权限和策略管理</span><span class="sxs-lookup"><span data-stu-id="9487e-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="9487e-103">.NET Framework 为其提供权限的多个受保护的操作可能允许绕过安全系统。</span><span class="sxs-lookup"><span data-stu-id="9487e-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="9487e-104">应仅对可信的代码，并且仅在必要的时候授予这些危险的权限。</span><span class="sxs-lookup"><span data-stu-id="9487e-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="9487e-105">如果它被授予这些权限，通常会对恶意代码没有任何防范。</span><span class="sxs-lookup"><span data-stu-id="9487e-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9487e-106">在 .NET Framework 4 中, 对 .NET Framework 安全模型和术语进行了重大更改。</span><span class="sxs-lookup"><span data-stu-id="9487e-106">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="9487e-107">有关这些更改的详细信息, 请参阅[安全更改](../security/security-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="9487e-107">For more information about these changes, see [Security Changes](../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="9487e-108">下表介绍了危险权限。</span><span class="sxs-lookup"><span data-stu-id="9487e-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="9487e-109">权限</span><span class="sxs-lookup"><span data-stu-id="9487e-109">Permission</span></span>|<span data-ttu-id="9487e-110">潜在的风险</span><span class="sxs-lookup"><span data-stu-id="9487e-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="9487e-111">允许托管代码调用到非托管代码中，常常是很危险的。</span><span class="sxs-lookup"><span data-stu-id="9487e-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="9487e-112">如果没有验证，代码可以执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="9487e-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="9487e-113">无效证据可以欺骗安全策略。</span><span class="sxs-lookup"><span data-stu-id="9487e-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="9487e-114">修改安全策略的功能可以禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="9487e-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="9487e-115">序列化的使用可以避开可访问性机制。</span><span class="sxs-lookup"><span data-stu-id="9487e-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="9487e-116">有关详细信息，请参阅 [安全和序列化](security-and-serialization.md)。</span><span class="sxs-lookup"><span data-stu-id="9487e-116">For details, see [Security and Serialization](security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="9487e-117">设置当前主体的功能可以欺骗基于角色的安全性。</span><span class="sxs-lookup"><span data-stu-id="9487e-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="9487e-118">由于与线程关联的安全状态，因此对线程进行操作很危险。</span><span class="sxs-lookup"><span data-stu-id="9487e-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="9487e-119">可以使用私有成员来攻克可访问性机制。</span><span class="sxs-lookup"><span data-stu-id="9487e-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9487e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="9487e-120">See also</span></span>

- [<span data-ttu-id="9487e-121">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="9487e-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
