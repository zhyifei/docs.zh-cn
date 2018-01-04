---
title: "如何：创建自定义声明"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92420b993a1959b03090181944a34a32ab500733
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="8c095-102">如何：创建自定义声明</span><span class="sxs-lookup"><span data-stu-id="8c095-102">How to: Create a Custom Claim</span></span>
<span data-ttu-id="8c095-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的标识模型基础结构提供了一组内置的声明类型和权限，并且提供了用来创建具有这些类型和权限的 <xref:System.IdentityModel.Claims.Claim> 实例的帮助器函数。</span><span class="sxs-lookup"><span data-stu-id="8c095-103">The Identity Model infrastructure in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="8c095-104">这些内置的声明用于对 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 默认支持的客户端凭据类型中的信息进行建模。</span><span class="sxs-lookup"><span data-stu-id="8c095-104">These built-in claims are designed to model information found in client credential types that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports by default.</span></span> <span data-ttu-id="8c095-105">在许多情况下，这些内置的声明足够满足需要，然而一些应用程序可能需要自定义声明。</span><span class="sxs-lookup"><span data-stu-id="8c095-105">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="8c095-106">声明由声明类型、要应用该声明的资源和在该资源上断言的权限组成。</span><span class="sxs-lookup"><span data-stu-id="8c095-106">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="8c095-107">本主题描述如何创建自定义声明。</span><span class="sxs-lookup"><span data-stu-id="8c095-107">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="8c095-108">创建基于基元数据类型的自定义声明</span><span class="sxs-lookup"><span data-stu-id="8c095-108">To create a custom claim that is based on a primitive data type</span></span>  
  
1.  <span data-ttu-id="8c095-109">通过将声明类型、资源值和权限传递到 <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> 构造函数来创建自定义声明。</span><span class="sxs-lookup"><span data-stu-id="8c095-109">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="8c095-110">确定声明类型的唯一值。</span><span class="sxs-lookup"><span data-stu-id="8c095-110">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="8c095-111">声明类型是一个唯一的字符串标识符。</span><span class="sxs-lookup"><span data-stu-id="8c095-111">The claim type is a unique string identifier.</span></span> <span data-ttu-id="8c095-112">自定义声明的设计者负责确保声明类型所使用的字符串标识符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8c095-112">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="8c095-113">有关 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 定义的声明类型的列表，请参见 <xref:System.IdentityModel.Claims.ClaimTypes> 类。</span><span class="sxs-lookup"><span data-stu-id="8c095-113">For a list of claim types that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="8c095-114">选择资源的基元数据类型和值。</span><span class="sxs-lookup"><span data-stu-id="8c095-114">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="8c095-115">资源是一个对象。</span><span class="sxs-lookup"><span data-stu-id="8c095-115">A resource is an object.</span></span> <span data-ttu-id="8c095-116">资源的 CLR 类型可以是一个基元类型，例如 <xref:System.String> 或 <xref:System.Int32>，也可以是任何可序列化的类型。</span><span class="sxs-lookup"><span data-stu-id="8c095-116">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="8c095-117">资源的 CLR 类型必须是可序列化的，因为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 会在不同时刻将声明序列化。</span><span class="sxs-lookup"><span data-stu-id="8c095-117">The CLR type of the resource must be serializable, because claims are serialized at various points by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="8c095-118">基元类型是可序列化的类型。</span><span class="sxs-lookup"><span data-stu-id="8c095-118">Primitive types are serializable.</span></span>  
  
    3.  <span data-ttu-id="8c095-119">选择 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 定义的一个权限，或者为自定义权限选择一个唯一值。</span><span class="sxs-lookup"><span data-stu-id="8c095-119">Choose a right that is defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="8c095-120">权限是一个唯一的字符串标识符。</span><span class="sxs-lookup"><span data-stu-id="8c095-120">A right is a unique string identifier.</span></span> <span data-ttu-id="8c095-121">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 定义的权限是在 <xref:System.IdentityModel.Claims.Rights> 类中定义的。</span><span class="sxs-lookup"><span data-stu-id="8c095-121">The rights that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="8c095-122">自定义声明的设计者负责确保权限所使用的字符串标识符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8c095-122">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="8c095-123">下面的代码示例创建了一个声明类型为 `http://example.org/claims/simplecustomclaim`、资源名称为 `Driver's License` 并具有 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 权限的自定义声明。</span><span class="sxs-lookup"><span data-stu-id="8c095-123">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="8c095-124">创建基于非基元数据类型的自定义声明</span><span class="sxs-lookup"><span data-stu-id="8c095-124">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1.  <span data-ttu-id="8c095-125">通过将声明类型、资源值和权限传递到 <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> 构造函数来创建自定义声明。</span><span class="sxs-lookup"><span data-stu-id="8c095-125">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="8c095-126">确定声明类型的唯一值。</span><span class="sxs-lookup"><span data-stu-id="8c095-126">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="8c095-127">声明类型是一个唯一的字符串标识符。</span><span class="sxs-lookup"><span data-stu-id="8c095-127">The claim type is a unique string identifier.</span></span> <span data-ttu-id="8c095-128">自定义声明的设计者负责确保声明类型所使用的字符串标识符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8c095-128">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="8c095-129">有关 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 定义的声明类型的列表，请参见 <xref:System.IdentityModel.Claims.ClaimTypes> 类。</span><span class="sxs-lookup"><span data-stu-id="8c095-129">For a list of claim types that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="8c095-130">为资源选择或定义一个可序列化的非基元类型。</span><span class="sxs-lookup"><span data-stu-id="8c095-130">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="8c095-131">资源是一个对象。</span><span class="sxs-lookup"><span data-stu-id="8c095-131">A resource is an object.</span></span> <span data-ttu-id="8c095-132">资源的 CLR 类型必须是可序列化的，因为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 会在不同时刻将声明序列化。</span><span class="sxs-lookup"><span data-stu-id="8c095-132">The CLR type of the resource must be serializable, because claims are serialized at various points by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="8c095-133">基元类型本身是可序列化的类型。</span><span class="sxs-lookup"><span data-stu-id="8c095-133">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="8c095-134">在定义一个新类型时，请将 <xref:System.Runtime.Serialization.DataContractAttribute> 应用于类。</span><span class="sxs-lookup"><span data-stu-id="8c095-134">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="8c095-135">另外，请将 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性应用于新类型的需要作为声明的一部分序列化的所有成员。</span><span class="sxs-lookup"><span data-stu-id="8c095-135">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="8c095-136">下面的代码示例定义了一个名为 `MyResourceType` 的自定义资源类型。</span><span class="sxs-lookup"><span data-stu-id="8c095-136">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)] 
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]        
  
    3.  <span data-ttu-id="8c095-137">选择 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 定义的一个权限，或者为自定义权限选择一个唯一值。</span><span class="sxs-lookup"><span data-stu-id="8c095-137">Choose a right that is defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="8c095-138">权限是一个唯一的字符串标识符。</span><span class="sxs-lookup"><span data-stu-id="8c095-138">A right is a unique string identifier.</span></span> <span data-ttu-id="8c095-139">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 定义的权限是在 <xref:System.IdentityModel.Claims.Rights> 类中定义的。</span><span class="sxs-lookup"><span data-stu-id="8c095-139">The rights that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="8c095-140">自定义声明的设计者负责确保权限所使用的字符串标识符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8c095-140">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="8c095-141">下面的代码示例创建了一个声明类型为 `http://example.org/claims/complexcustomclaim`、自定义资源类型为 `MyResourceType` 并具有 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 权限的自定义声明。</span><span class="sxs-lookup"><span data-stu-id="8c095-141">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)] 
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]     
  
## <a name="example"></a><span data-ttu-id="8c095-142">示例</span><span class="sxs-lookup"><span data-stu-id="8c095-142">Example</span></span>  
 <span data-ttu-id="8c095-143">下面的代码示例演示如何创建一个具有基元资源类型的自定义声明和一个具有非基元资源类型的自定义声明。</span><span class="sxs-lookup"><span data-stu-id="8c095-143">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="8c095-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c095-144">See Also</span></span>  
 <xref:System.IdentityModel.Claims.Claim>  
 <xref:System.IdentityModel.Claims.Rights>  
 <xref:System.IdentityModel.Claims.ClaimTypes>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="8c095-145">使用标识模型管理声明和授权</span><span class="sxs-lookup"><span data-stu-id="8c095-145">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="8c095-146">使用标识模型管理声明和授权</span><span class="sxs-lookup"><span data-stu-id="8c095-146">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
