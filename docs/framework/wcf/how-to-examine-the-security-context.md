---
title: 如何：检查安全上下文
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 8ff6969095a49dcae8b1d59b5b0ab28a8af24274
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499471"
---
# <a name="how-to-examine-the-security-context"></a><span data-ttu-id="23d06-102">如何：检查安全上下文</span><span class="sxs-lookup"><span data-stu-id="23d06-102">How to: Examine the Security Context</span></span>
<span data-ttu-id="23d06-103">编程时 Windows Communication Foundation (WCF) 服务，服务安全上下文可用于确定有关的客户端凭据和声明用于与服务进行身份验证的详细信息。</span><span class="sxs-lookup"><span data-stu-id="23d06-103">When programming Windows Communication Foundation (WCF) services, the service security context enables you to determine details about the client credentials and claims used to authenticate with the service.</span></span> <span data-ttu-id="23d06-104">这是使用 <xref:System.ServiceModel.ServiceSecurityContext> 类的属性进行的。</span><span class="sxs-lookup"><span data-stu-id="23d06-104">This is done by using the properties of the <xref:System.ServiceModel.ServiceSecurityContext> class.</span></span>  
  
 <span data-ttu-id="23d06-105">例如，使用 <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> 或 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 属性可检索当前客户端的标识。</span><span class="sxs-lookup"><span data-stu-id="23d06-105">For example, you can retrieve the identity of the current client by using the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> or the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property.</span></span> <span data-ttu-id="23d06-106">若要确定客户端是否匿名，请使用 <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="23d06-106">To determine whether the client is anonymous, use the <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> property.</span></span>  
  
 <span data-ttu-id="23d06-107">通过循环访问 <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> 属性中的声明集合，还可以确定以客户端的名义进行了哪些声明。</span><span class="sxs-lookup"><span data-stu-id="23d06-107">You can also determine what claims are being made on behalf of the client by iterating through the collection of claims in the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
### <a name="to-get-the-current-security-context"></a><span data-ttu-id="23d06-108">获取当前安全上下文</span><span class="sxs-lookup"><span data-stu-id="23d06-108">To get the current security context</span></span>  
  
-   <span data-ttu-id="23d06-109">访问静态属性 <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> 以获取当前的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="23d06-109">Access the static property <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> to get the current security context.</span></span> <span data-ttu-id="23d06-110">从参考检查当前上下文的任何属性。</span><span class="sxs-lookup"><span data-stu-id="23d06-110">Examine any of the properties of the current context from the reference.</span></span>  
  
### <a name="to-determine-the-identity-of-the-caller"></a><span data-ttu-id="23d06-111">确定调用方的标识</span><span class="sxs-lookup"><span data-stu-id="23d06-111">To determine the identity of the caller</span></span>  
  
1.  <span data-ttu-id="23d06-112">打印 <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> 和 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="23d06-112">Print the value of the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> properties.</span></span>  
  
### <a name="to-parse-the-claims-of-a-caller"></a><span data-ttu-id="23d06-113">分析调用方的声明</span><span class="sxs-lookup"><span data-stu-id="23d06-113">To parse the claims of a caller</span></span>  
  
1.  <span data-ttu-id="23d06-114">返回当前 <xref:System.IdentityModel.Policy.AuthorizationContext> 类。</span><span class="sxs-lookup"><span data-stu-id="23d06-114">Return the current <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span> <span data-ttu-id="23d06-115">使用 <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> 属性返回当前服务安全上下文，然后使用 `AuthorizationContext` 属性返回 <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>。</span><span class="sxs-lookup"><span data-stu-id="23d06-115">Use the <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> property to return the current service security context, then return the `AuthorizationContext` using the <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> property.</span></span>  
  
2.  <span data-ttu-id="23d06-116">分析由 <xref:System.IdentityModel.Claims.ClaimSet> 类的 <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> 属性返回的 <xref:System.IdentityModel.Policy.AuthorizationContext> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="23d06-116">Parse the collection of <xref:System.IdentityModel.Claims.ClaimSet> objects returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23d06-117">示例</span><span class="sxs-lookup"><span data-stu-id="23d06-117">Example</span></span>  
 <span data-ttu-id="23d06-118">下面的示例打印当前安全上下文的 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 和 <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> 属性的值及 <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> 属性、声明的资源值，以及当前安全上下文中每个声明的 <xref:System.IdentityModel.Claims.Claim.Right%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="23d06-118">The following example prints the values of the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> and <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> properties of the current security context and the <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> property, the resource value of the claim, and the <xref:System.IdentityModel.Claims.Claim.Right%2A> property of every claim in the current security context.</span></span>  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="23d06-119">编译代码</span><span class="sxs-lookup"><span data-stu-id="23d06-119">Compiling the Code</span></span>  
 <span data-ttu-id="23d06-120">该代码使用以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="23d06-120">The code uses the following namespaces:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.IdentityModel.Policy>  
  
-   <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a><span data-ttu-id="23d06-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="23d06-121">See Also</span></span>  
 [<span data-ttu-id="23d06-122">保护服务</span><span class="sxs-lookup"><span data-stu-id="23d06-122">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="23d06-123">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="23d06-123">Service Identity and Authentication</span></span>](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
