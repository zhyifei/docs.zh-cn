---
title: 替换 Principal 对象
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfcd912fc16aa8d4b89a4f455d65b0294593cead
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205849"
---
# <a name="replacing-a-principal-object"></a><span data-ttu-id="35878-102">替换 Principal 对象</span><span class="sxs-lookup"><span data-stu-id="35878-102">Replacing a Principal Object</span></span>
<span data-ttu-id="35878-103">提供身份验证服务的应用程序必须能够为给定的线程替换 **主体** 对象 (<xref:System.Security.Principal.IPrincipal>)。</span><span class="sxs-lookup"><span data-stu-id="35878-103">Applications that provide authentication services must be able to replace the **Principal** object (<xref:System.Security.Principal.IPrincipal>) for a given thread.</span></span> <span data-ttu-id="35878-104">此外，安全系统必须帮助保护这种替换 **主体** 对象的能力，因为恶意附加的不正确的 **主体** 会通过声明一个不真实的身份或角色危及应用程序的安全。</span><span class="sxs-lookup"><span data-stu-id="35878-104">Furthermore, the security system must help protect the ability to replace **Principal** objects because a maliciously attached, incorrect **Principal** compromises the security of your application by claiming an untrue identity or role.</span></span> <span data-ttu-id="35878-105">因此，应用程序，需要能够替换**主体**必须授予对象<xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>对象以进行主体控制。</span><span class="sxs-lookup"><span data-stu-id="35878-105">Therefore, applications that require the ability to replace **Principal** objects must be granted the <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> object for principal control.</span></span> <span data-ttu-id="35878-106">（请注意，对于执行基于角色的安全检查或创建 **主体** 对象，此权限不是必需的。）</span><span class="sxs-lookup"><span data-stu-id="35878-106">(Note that this permission is not required for performing role-based security checks or for creating **Principal** objects.)</span></span>  
  
 <span data-ttu-id="35878-107">可通过执行以下任务替换当前 **主体** 对象：</span><span class="sxs-lookup"><span data-stu-id="35878-107">The current **Principal** object can be replaced by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="35878-108">创建替换的 **主体** 对象和关联的 **标识** 对象。</span><span class="sxs-lookup"><span data-stu-id="35878-108">Create the replacement **Principal** object and associated **Identity** object.</span></span>  
  
2.  <span data-ttu-id="35878-109">将新的 **主体** 附加到调用上下文。</span><span class="sxs-lookup"><span data-stu-id="35878-109">Attach the new **Principal** object to the call context.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35878-110">示例</span><span class="sxs-lookup"><span data-stu-id="35878-110">Example</span></span>  
 <span data-ttu-id="35878-111">下面的示例演示如何创建一般主体对象并用该对象来设置线程的主体。</span><span class="sxs-lookup"><span data-stu-id="35878-111">The following example shows how to create a generic principal object and use it to set the principal of a thread.</span></span>  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="35878-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="35878-112">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
- [<span data-ttu-id="35878-113">主体和标识对象</span><span class="sxs-lookup"><span data-stu-id="35878-113">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
