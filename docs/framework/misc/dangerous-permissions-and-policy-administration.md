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
ms.openlocfilehash: ae24cdcb97e30da0bd4aec6569ef3dcda11488c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775760"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="df431-102">危险权限和策略管理</span><span class="sxs-lookup"><span data-stu-id="df431-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="df431-103">.NET Framework 为其提供权限的多个受保护的操作可能允许绕过安全系统。</span><span class="sxs-lookup"><span data-stu-id="df431-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="df431-104">应仅对可信的代码，并且仅在必要的时候授予这些危险的权限。</span><span class="sxs-lookup"><span data-stu-id="df431-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="df431-105">如果它被授予这些权限，通常会对恶意代码没有任何防范。</span><span class="sxs-lookup"><span data-stu-id="df431-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df431-106">在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]中，已对 .NET Framework 安全模型和术语作出重要更改。</span><span class="sxs-lookup"><span data-stu-id="df431-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="df431-107">有关这些更改的详细信息，请参阅[安全更改](../../../docs/framework/security/security-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="df431-107">For more information about these changes, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="df431-108">下表介绍了危险权限。</span><span class="sxs-lookup"><span data-stu-id="df431-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="df431-109">权限</span><span class="sxs-lookup"><span data-stu-id="df431-109">Permission</span></span>|<span data-ttu-id="df431-110">潜在的风险</span><span class="sxs-lookup"><span data-stu-id="df431-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="df431-111">允许托管代码调用到非托管代码中，常常是很危险的。</span><span class="sxs-lookup"><span data-stu-id="df431-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="df431-112">如果没有验证，代码可以执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="df431-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="df431-113">无效证据可以欺骗安全策略。</span><span class="sxs-lookup"><span data-stu-id="df431-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="df431-114">修改安全策略的功能可以禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="df431-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="df431-115">序列化的使用可以避开可访问性机制。</span><span class="sxs-lookup"><span data-stu-id="df431-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="df431-116">有关详细信息，请参阅 [安全和序列化](../../../docs/framework/misc/security-and-serialization.md)。</span><span class="sxs-lookup"><span data-stu-id="df431-116">For details, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="df431-117">设置当前主体的功能可以欺骗基于角色的安全性。</span><span class="sxs-lookup"><span data-stu-id="df431-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="df431-118">由于与线程关联的安全状态，因此对线程进行操作很危险。</span><span class="sxs-lookup"><span data-stu-id="df431-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="df431-119">可以使用私有成员来攻克可访问性机制。</span><span class="sxs-lookup"><span data-stu-id="df431-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df431-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="df431-120">See also</span></span>

- [<span data-ttu-id="df431-121">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="df431-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
