---
title: 如何：比较声明
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], comparing
- claims [WCF]
ms.assetid: 0c4ec84d-53df-408f-8953-9bc437f56c28
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5188ed17e3a10bfd93b885fcdd93e01391dd8256
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-compare-claims"></a><span data-ttu-id="59444-102">如何：比较声明</span><span class="sxs-lookup"><span data-stu-id="59444-102">How to: Compare Claims</span></span>
<span data-ttu-id="59444-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的标识模型基础结构用于执行授权检查。</span><span class="sxs-lookup"><span data-stu-id="59444-103">The Identity Model infrastructure in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is used to perform authorization checking.</span></span> <span data-ttu-id="59444-104">因此，一个常见的任务是将授权上下文中的声明与执行请求的操作或访问请求的资源所需的声明进行比较。</span><span class="sxs-lookup"><span data-stu-id="59444-104">As such, a common task is to compare claims in the authorization context to the claims required to perform the requested action or access the requested resource.</span></span> <span data-ttu-id="59444-105">本主题说明如何比较声明，包括内置和自定义声明类型。</span><span class="sxs-lookup"><span data-stu-id="59444-105">This topic describes how to compare claims, including built-in and custom claim types.</span></span> <span data-ttu-id="59444-106">有关标识模型基础结构的详细信息，请参阅[管理声明和使用标识模型的授权](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)。</span><span class="sxs-lookup"><span data-stu-id="59444-106">For more information about the Identity Model infrastructure, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>  
  
 <span data-ttu-id="59444-107">声明比较包括将一个声明的三个部分（类型、权限和资源）与另一个声明中的相同部分进行比较，以确定它们是否相等。</span><span class="sxs-lookup"><span data-stu-id="59444-107">Claim comparison involves comparing the three parts of a claim (type, right, and resource) against the same parts in another claim to see if they are equal.</span></span> <span data-ttu-id="59444-108">请参见以下示例。</span><span class="sxs-lookup"><span data-stu-id="59444-108">See the following example.</span></span>  
  
 [!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
 [!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]  
  
 <span data-ttu-id="59444-109">两个声明都具有 <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A> 声明类型、<xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 权限和字符串“someone”资源。</span><span class="sxs-lookup"><span data-stu-id="59444-109">Both claims have a claim type of <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource of the string "someone".</span></span> <span data-ttu-id="59444-110">由于声明的三个部分都相等，因此声明本身也是相等的。</span><span class="sxs-lookup"><span data-stu-id="59444-110">As all three parts of the claim are equal, the claims themselves are equal.</span></span>  
  
 <span data-ttu-id="59444-111">内置的声明类型通过 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 方法进行比较。</span><span class="sxs-lookup"><span data-stu-id="59444-111">The built-in claim types are compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="59444-112">必要时使用特定于声明的比较代码。</span><span class="sxs-lookup"><span data-stu-id="59444-112">Claim-specific comparison code is used where necessary.</span></span> <span data-ttu-id="59444-113">例如，给定以下两个用户主要名称 (UPN) 声明：</span><span class="sxs-lookup"><span data-stu-id="59444-113">For example, given the following two user principal name (UPN) claims:</span></span>  
  
 [!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
 [!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]  
  
 <span data-ttu-id="59444-114">中的比较代码<xref:System.IdentityModel.Claims.Claim.Equals%2A>方法返回`true`，那么`example\someone`作为同一个域用户标识"someone@example.com"。</span><span class="sxs-lookup"><span data-stu-id="59444-114">the comparison code in the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method returns `true`, assuming `example\someone` identifies the same domain user as "someone@example.com".</span></span>  
  
 <span data-ttu-id="59444-115">还可以使用 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 方法比较自定义声明类型。</span><span class="sxs-lookup"><span data-stu-id="59444-115">Custom claim types can also be compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="59444-116">但是，在声明的 <xref:System.IdentityModel.Claims.Claim.Resource%2A> 属性返回的类型不是基元类型的情况下，只有当 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 属性返回的值依据 `true` 方法相等时，`Resource` 才会返回 <xref:System.IdentityModel.Claims.Claim.Equals%2A>。</span><span class="sxs-lookup"><span data-stu-id="59444-116">However, in cases where the type returned by the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property of the claim is something other than a primitive type, the <xref:System.IdentityModel.Claims.Claim.Equals%2A> returns `true` only if the values returned by the `Resource` properties are equal according to the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="59444-117">当此情况不适用时，`Resource` 属性返回的自定义类型应该重写 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 和 <xref:System.Object.GetHashCode%2A> 方法，以执行任何必要的自定义处理。</span><span class="sxs-lookup"><span data-stu-id="59444-117">In cases where this is not appropriate, the custom type returned by the `Resource` property should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods to perform whatever custom processing is necessary.</span></span>  
  
### <a name="comparing-built-in-claims"></a><span data-ttu-id="59444-118">比较内置声明</span><span class="sxs-lookup"><span data-stu-id="59444-118">Comparing built-in claims</span></span>  
  
1.  <span data-ttu-id="59444-119">给定 <xref:System.IdentityModel.Claims.Claim> 类的两个实例，使用 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 进行比较，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="59444-119">Given two instances of the <xref:System.IdentityModel.Claims.Claim> class, use the <xref:System.IdentityModel.Claims.Claim.Equals%2A> to make the comparison, as shown in the following code.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]  
  
### <a name="comparing-custom-claims-with-primitive-resource-types"></a><span data-ttu-id="59444-120">比较具有基元资源类型的自定义声明</span><span class="sxs-lookup"><span data-stu-id="59444-120">Comparing custom claims with primitive resource types</span></span>  
  
1.  <span data-ttu-id="59444-121">对于具有基元资源类型的自定义声明，可以按照内置声明那样的方式执行比较，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="59444-121">For custom claims with primitive resource types, comparison can be performed as for built-in claims, as shown in the following code.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]  
  
2.  <span data-ttu-id="59444-122">对于具有基于结构或类的资源类型的自定义声明，资源类型应重写 <xref:System.IdentityModel.Claims.Claim.Equals%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="59444-122">For custom claims with structure or class based resource types, the resource type should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span>  
  
3.  <span data-ttu-id="59444-123">首先检查 `obj` 参数是否为 `null`，如果是，则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="59444-123">First check whether the `obj` parameter is `null`, and if so, return `false`.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]  
  
4.  <span data-ttu-id="59444-124">接下来调用 <xref:System.Object.ReferenceEquals%2A>，并将 `this` 和 `obj` 作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="59444-124">Next call <xref:System.Object.ReferenceEquals%2A> and pass `this` and `obj` as parameters.</span></span> <span data-ttu-id="59444-125">如果它返回 `true`，则返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="59444-125">If it returns `true`, then return `true`.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]  
  
5.  <span data-ttu-id="59444-126">然后尝试将 `obj` 分配给一个类类型的局部变量。</span><span class="sxs-lookup"><span data-stu-id="59444-126">Next attempt to assign `obj` to a local variable of the class type.</span></span> <span data-ttu-id="59444-127">如果此操作失败，则引用为 `null`。</span><span class="sxs-lookup"><span data-stu-id="59444-127">If this fails, the reference is `null`.</span></span> <span data-ttu-id="59444-128">在这种情况下返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="59444-128">In such cases, return `false`.</span></span>  
  
6.  <span data-ttu-id="59444-129">执行将当前声明与提供的声明进行正确比较所需的自定义比较。</span><span class="sxs-lookup"><span data-stu-id="59444-129">Perform the custom comparison necessary to correctly compare the current claim to the provided claim.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59444-130">示例</span><span class="sxs-lookup"><span data-stu-id="59444-130">Example</span></span>  
 <span data-ttu-id="59444-131">下面的示例显示自定义声明的比较，其中声明资源是非基元类型。</span><span class="sxs-lookup"><span data-stu-id="59444-131">The following example shows a comparison of custom claims where the claim resource is a non-primitive type.</span></span>  
  
 [!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
 [!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="59444-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="59444-132">See Also</span></span>  
 [<span data-ttu-id="59444-133">使用标识模型管理声明和授权</span><span class="sxs-lookup"><span data-stu-id="59444-133">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="59444-134">如何：创建自定义声明</span><span class="sxs-lookup"><span data-stu-id="59444-134">How to: Create a Custom Claim</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
