---
title: "如何：检查安全上下文"
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
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 72bc3dfcc91cb0fe5b393c9735c83b6331d5e0dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-examine-the-security-context"></a>如何：检查安全上下文
在编程 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 服务时，服务安全上下文可用于确定有关用来向服务验明身份的客户端凭据和声明的详细信息。 这是使用 <xref:System.ServiceModel.ServiceSecurityContext> 类的属性进行的。  
  
 例如，使用 <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> 或 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 属性可检索当前客户端的标识。 若要确定客户端是否匿名，请使用 <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> 属性。  
  
 通过循环访问 <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> 属性中的声明集合，还可以确定以客户端的名义进行了哪些声明。  
  
### <a name="to-get-the-current-security-context"></a>获取当前安全上下文  
  
-   访问静态属性 <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> 以获取当前的安全上下文。 从参考检查当前上下文的任何属性。  
  
### <a name="to-determine-the-identity-of-the-caller"></a>确定调用方的标识  
  
1.  打印 <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> 和 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 属性的值。  
  
### <a name="to-parse-the-claims-of-a-caller"></a>分析调用方的声明  
  
1.  返回当前 <xref:System.IdentityModel.Policy.AuthorizationContext> 类。 使用 <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> 属性返回当前服务安全上下文，然后使用 `AuthorizationContext` 属性返回 <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>。  
  
2.  分析由 <xref:System.IdentityModel.Claims.ClaimSet> 类的 <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> 属性返回的 <xref:System.IdentityModel.Policy.AuthorizationContext> 对象的集合。  
  
## <a name="example"></a>示例  
 下面的示例打印当前安全上下文的 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 和 <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> 属性的值及 <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> 属性、声明的资源值，以及当前安全上下文中每个声明的 <xref:System.IdentityModel.Claims.Claim.Right%2A> 属性。  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a>编译代码  
 该代码使用以下命名空间：  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.IdentityModel.Policy>  
  
-   <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a>另请参阅  
 [保护服务](../../../docs/framework/wcf/securing-services.md)  
 [服务标识和身份验证](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
