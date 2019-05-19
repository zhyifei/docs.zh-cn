---
title: 如何：在服务上模拟客户端
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, impersonation
- impersonation
- WCF, security
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
ms.openlocfilehash: 1e6e0597f40f32df17d435cb959b246b3b7872fa
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881090"
---
# <a name="how-to-impersonate-a-client-on-a-service"></a>如何：在服务上模拟客户端
模拟 Windows Communication Foundation (WCF) 服务上的客户端使服务能够代表客户端执行操作。 对于受访问控制列表 (ACL) 检查的操作（例如，访问计算机上的目录和文件，或访问 SQL Server 数据库），ACL 检查针对的是客户端用户帐户。 本主题演示一些基本步骤，通过这些步骤，Windows 域中的客户端可以设置客户端模拟级别。 有关此操作的可运行示例，请参阅 [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md)。 有关客户端模拟的详细信息，请参阅[委托和模拟](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)。  
  
> [!NOTE]
>  当客户端和服务运行在同一计算机上，客户端运行在系统帐户（即 `Local System` 或 `Network Service`）下时，如果安全会话是使用状态安全上下文令牌建立的，则不能模拟客户端。 WinForms 或控制台应用程序通常运行在当前登录的帐户下，因此，默认情况下可以模拟该帐户。 但是，当客户端是 ASP.NET 页，该页面托管在[!INCLUDE[iis601](../../../includes/iis601-md.md)]下运行 IIS 7.0 中，则客户端或`Network Service`默认情况下的帐户。 默认情况下，系统提供的所有支持安全会话的绑定都使用无状态安全上下文令牌。 但是，如果客户端是 ASP.NET 页，并且使用与有状态安全上下文令牌的安全会话，则不能模拟该客户端。 有关在安全会话中使用有状态安全上下文令牌的详细信息，请参阅[如何：创建安全上下文令牌的安全会话](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)。  
  
### <a name="to-enable-impersonation-of-a-client-from-a-cached-windows-token-on-a-service"></a>根据缓存的 Windows 令牌在服务上启用客户端模拟  
  
1. 创建服务。 有关此基本过程的教程，请参阅 [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md)。  
  
2. 使用采用 Windows 身份验证并创建会话的绑定，例如 <xref:System.ServiceModel.NetTcpBinding> 或 <xref:System.ServiceModel.WSHttpBinding>。  
  
3. 在创建服务接口的实现时，将 <xref:System.ServiceModel.OperationBehaviorAttribute> 类应用于要求客户端模拟的方法。 将 <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> 属性设置为 <xref:System.ServiceModel.ImpersonationOption.Required>。  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### <a name="to-set-the-allowed-impersonation-level-on-the-client"></a>设置客户端允许的模拟级别  
  
1. 通过使用 [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)创建服务客户端代码。 有关详细信息，请参阅[使用 WCF 客户端访问服务](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)。  
  
2. 创建 WCF 客户端之后, 设置<xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>的属性<xref:System.ServiceModel.Security.WindowsClientCredential>类的一个<xref:System.Security.Principal.TokenImpersonationLevel>枚举值。  
  
    > [!NOTE]
    >  若要使用 <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>，则必须使用协商 Kerberos 身份验证（有时称为“多段”  或“多步”  Kerberos）。 有关如何实现这一方案的说明，请参阅[安全性的最佳做法](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)。  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.OperationBehaviorAttribute>
- <xref:System.Security.Principal.TokenImpersonationLevel>
- [模拟客户端](../../../docs/framework/wcf/samples/impersonating-the-client.md)
- [委托和模拟](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
