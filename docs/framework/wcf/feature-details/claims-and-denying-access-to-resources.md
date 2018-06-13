---
title: 声明和拒绝访问资源
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
ms.openlocfilehash: a53affe5e21b5ef532e7094eed032b44f5a5ea7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488606"
---
# <a name="claims-and-denying-access-to-resources"></a><span data-ttu-id="3bb6e-102">声明和拒绝访问资源</span><span class="sxs-lookup"><span data-stu-id="3bb6e-102">Claims and Denying Access to Resources</span></span>
<span data-ttu-id="3bb6e-103">Windows Communication Foundation (WCF) 支持基于声明的授权机制。</span><span class="sxs-lookup"><span data-stu-id="3bb6e-103">Windows Communication Foundation (WCF) supports a claims-based authorization mechanism.</span></span> <span data-ttu-id="3bb6e-104">在基于是否存在声明来允许访问资源的同时，系统通常也基于是否存在声明来拒绝访问资源。</span><span class="sxs-lookup"><span data-stu-id="3bb6e-104">As well as allowing access to resources based on the presence of claims, systems often deny access to resources based on the presence of claims.</span></span> <span data-ttu-id="3bb6e-105">这样的系统应该在查找导致允许访问的声明之前先检查 <xref:System.IdentityModel.Policy.AuthorizationContext> 是否存在导致拒绝访问的声明。</span><span class="sxs-lookup"><span data-stu-id="3bb6e-105">Such systems should examine the <xref:System.IdentityModel.Policy.AuthorizationContext> for claims that result in access being denied before looking for claims that result in access being allowed.</span></span>  
  
 <span data-ttu-id="3bb6e-106">例如，对于具有类型为 `Age`、权限为 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 和资源值为 `Under 21` 的声明的任何用户，仅当该标识同时也具有类型为 `Name`、权限为 <xref:System.IdentityModel.Claims.Rights.Identity%2A> 和资源值为 `Mallory` 的声明时，系统才会拒绝其访问资源。</span><span class="sxs-lookup"><span data-stu-id="3bb6e-106">For example, a system might deny access to a resource to anyone who has a claim with a type of `Age`, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource value of `Under 21` only when that identity also has a claim of type `Name`, a right of <xref:System.IdentityModel.Claims.Rights.Identity%2A>, and a resource value of `Mallory`.</span></span> <span data-ttu-id="3bb6e-107">换言之，对于年龄不到 21 岁的任何人，系统拒绝其访问资源，如果姓名为 Mallory，则系统允许其访问资源。</span><span class="sxs-lookup"><span data-stu-id="3bb6e-107">Put another way, the system denies access to anyone who is under 21 years old and grants access when the name is Mallory.</span></span> <span data-ttu-id="3bb6e-108">为了正确地实现此语义，必须首先查找 `Age` 声明，然后确定年龄是否低于 21 岁。</span><span class="sxs-lookup"><span data-stu-id="3bb6e-108">To correctly implement this semantic, it is important to look for the `Age` claim first and determine whether the age is under 21 years old.</span></span> <span data-ttu-id="3bb6e-109">否则，如果 Mallory 不到 21 岁，则仅基于 `Name` 声明授予对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3bb6e-109">Otherwise, if Mallory is under 21, then the resource may be granted access solely on the basis of the `Name` claim.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb6e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bb6e-110">See Also</span></span>  
 [<span data-ttu-id="3bb6e-111">使用标识模型管理声明和授权</span><span class="sxs-lookup"><span data-stu-id="3bb6e-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="3bb6e-112">声明和令牌</span><span class="sxs-lookup"><span data-stu-id="3bb6e-112">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
