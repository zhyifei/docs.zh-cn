---
title: 如何：创建自定义声明
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: 3ee707ae4e2a7dafeb7cb42d6d56eeece8f23306
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="1d03a-102">如何：创建自定义声明</span><span class="sxs-lookup"><span data-stu-id="1d03a-102">How to: Create a Custom Claim</span></span>
<span data-ttu-id="1d03a-103">标识模型基础结构在 Windows Communication Foundation (WCF) 提供一套内置的声明类型和权限的帮助器函数具有用于创建<xref:System.IdentityModel.Claims.Claim>具有这些类型和权限的实例。</span><span class="sxs-lookup"><span data-stu-id="1d03a-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="1d03a-104">这些内置的声明设计为默认情况下在 WCF 支持的客户端凭据类型中找到的模型信息。</span><span class="sxs-lookup"><span data-stu-id="1d03a-104">These built-in claims are designed to model information found in client credential types that WCF supports by default.</span></span> <span data-ttu-id="1d03a-105">在许多情况下，这些内置的声明足够满足需要，然而一些应用程序可能需要自定义声明。</span><span class="sxs-lookup"><span data-stu-id="1d03a-105">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="1d03a-106">声明由声明类型、要应用该声明的资源和在该资源上断言的权限组成。</span><span class="sxs-lookup"><span data-stu-id="1d03a-106">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="1d03a-107">本主题描述如何创建自定义声明。</span><span class="sxs-lookup"><span data-stu-id="1d03a-107">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="1d03a-108">创建基于基元数据类型的自定义声明</span><span class="sxs-lookup"><span data-stu-id="1d03a-108">To create a custom claim that is based on a primitive data type</span></span>  
  
1.  <span data-ttu-id="1d03a-109">通过将声明类型、资源值和权限传递到 <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> 构造函数来创建自定义声明。</span><span class="sxs-lookup"><span data-stu-id="1d03a-109">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="1d03a-110">确定声明类型的唯一值。</span><span class="sxs-lookup"><span data-stu-id="1d03a-110">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="1d03a-111">声明类型是一个唯一的字符串标识符。</span><span class="sxs-lookup"><span data-stu-id="1d03a-111">The claim type is a unique string identifier.</span></span> <span data-ttu-id="1d03a-112">自定义声明的设计者负责确保声明类型所使用的字符串标识符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1d03a-112">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="1d03a-113">Wcf 定义的声明类型的列表，请参阅<xref:System.IdentityModel.Claims.ClaimTypes>类。</span><span class="sxs-lookup"><span data-stu-id="1d03a-113">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="1d03a-114">选择资源的基元数据类型和值。</span><span class="sxs-lookup"><span data-stu-id="1d03a-114">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="1d03a-115">资源是一个对象。</span><span class="sxs-lookup"><span data-stu-id="1d03a-115">A resource is an object.</span></span> <span data-ttu-id="1d03a-116">资源的 CLR 类型可以是一个基元类型，例如 <xref:System.String> 或 <xref:System.Int32>，也可以是任何可序列化的类型。</span><span class="sxs-lookup"><span data-stu-id="1d03a-116">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="1d03a-117">资源的 CLR 类型必须可序列化，因为声明会在序列化不同的时间点由 WCF。</span><span class="sxs-lookup"><span data-stu-id="1d03a-117">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="1d03a-118">基元类型是可序列化的类型。</span><span class="sxs-lookup"><span data-stu-id="1d03a-118">Primitive types are serializable.</span></span>  
  
    3.  <span data-ttu-id="1d03a-119">选择一个权限，由 WCF 或自定义权限的唯一值。</span><span class="sxs-lookup"><span data-stu-id="1d03a-119">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="1d03a-120">权限是一个唯一的字符串标识符。</span><span class="sxs-lookup"><span data-stu-id="1d03a-120">A right is a unique string identifier.</span></span> <span data-ttu-id="1d03a-121">Wcf 定义的权限定义在<xref:System.IdentityModel.Claims.Rights>类。</span><span class="sxs-lookup"><span data-stu-id="1d03a-121">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="1d03a-122">自定义声明的设计者负责确保权限所使用的字符串标识符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1d03a-122">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="1d03a-123">下面的代码示例创建了一个声明类型为 `http://example.org/claims/simplecustomclaim`、资源名称为 `Driver's License` 并具有 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 权限的自定义声明。</span><span class="sxs-lookup"><span data-stu-id="1d03a-123">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="1d03a-124">创建基于非基元数据类型的自定义声明</span><span class="sxs-lookup"><span data-stu-id="1d03a-124">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1.  <span data-ttu-id="1d03a-125">通过将声明类型、资源值和权限传递到 <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> 构造函数来创建自定义声明。</span><span class="sxs-lookup"><span data-stu-id="1d03a-125">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="1d03a-126">确定声明类型的唯一值。</span><span class="sxs-lookup"><span data-stu-id="1d03a-126">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="1d03a-127">声明类型是一个唯一的字符串标识符。</span><span class="sxs-lookup"><span data-stu-id="1d03a-127">The claim type is a unique string identifier.</span></span> <span data-ttu-id="1d03a-128">自定义声明的设计者负责确保声明类型所使用的字符串标识符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1d03a-128">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="1d03a-129">Wcf 定义的声明类型的列表，请参阅<xref:System.IdentityModel.Claims.ClaimTypes>类。</span><span class="sxs-lookup"><span data-stu-id="1d03a-129">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="1d03a-130">为资源选择或定义一个可序列化的非基元类型。</span><span class="sxs-lookup"><span data-stu-id="1d03a-130">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="1d03a-131">资源是一个对象。</span><span class="sxs-lookup"><span data-stu-id="1d03a-131">A resource is an object.</span></span> <span data-ttu-id="1d03a-132">资源的 CLR 类型必须可序列化，因为声明会在序列化不同的时间点由 WCF。</span><span class="sxs-lookup"><span data-stu-id="1d03a-132">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="1d03a-133">基元类型本身是可序列化的类型。</span><span class="sxs-lookup"><span data-stu-id="1d03a-133">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="1d03a-134">在定义一个新类型时，请将 <xref:System.Runtime.Serialization.DataContractAttribute> 应用于类。</span><span class="sxs-lookup"><span data-stu-id="1d03a-134">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="1d03a-135">另外，请将 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性应用于新类型的需要作为声明的一部分序列化的所有成员。</span><span class="sxs-lookup"><span data-stu-id="1d03a-135">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="1d03a-136">下面的代码示例定义了一个名为 `MyResourceType` 的自定义资源类型。</span><span class="sxs-lookup"><span data-stu-id="1d03a-136">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)] 
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]        
  
    3.  <span data-ttu-id="1d03a-137">选择一个权限，由 WCF 或自定义权限的唯一值。</span><span class="sxs-lookup"><span data-stu-id="1d03a-137">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="1d03a-138">权限是一个唯一的字符串标识符。</span><span class="sxs-lookup"><span data-stu-id="1d03a-138">A right is a unique string identifier.</span></span> <span data-ttu-id="1d03a-139">Wcf 定义的权限定义在<xref:System.IdentityModel.Claims.Rights>类。</span><span class="sxs-lookup"><span data-stu-id="1d03a-139">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="1d03a-140">自定义声明的设计者负责确保权限所使用的字符串标识符是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1d03a-140">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="1d03a-141">下面的代码示例创建了一个声明类型为 `http://example.org/claims/complexcustomclaim`、自定义资源类型为 `MyResourceType` 并具有 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 权限的自定义声明。</span><span class="sxs-lookup"><span data-stu-id="1d03a-141">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)] 
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]     
  
## <a name="example"></a><span data-ttu-id="1d03a-142">示例</span><span class="sxs-lookup"><span data-stu-id="1d03a-142">Example</span></span>  
 <span data-ttu-id="1d03a-143">下面的代码示例演示如何创建一个具有基元资源类型的自定义声明和一个具有非基元资源类型的自定义声明。</span><span class="sxs-lookup"><span data-stu-id="1d03a-143">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="1d03a-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d03a-144">See Also</span></span>  
 <xref:System.IdentityModel.Claims.Claim>  
 <xref:System.IdentityModel.Claims.Rights>  
 <xref:System.IdentityModel.Claims.ClaimTypes>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="1d03a-145">使用标识模型管理声明和授权</span><span class="sxs-lookup"><span data-stu-id="1d03a-145">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="1d03a-146">使用标识模型管理声明和授权</span><span class="sxs-lookup"><span data-stu-id="1d03a-146">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
