---
title: 访问控制机制
ms.date: 03/30/2017
helpviewer_keywords:
- WCF security
- access control [WCF]
ms.assetid: 9d576122-3f55-4425-9acf-b23d0781e966
ms.openlocfilehash: 9ebd1489c35bb3b023ed73cd86fac1b6a352012b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882173"
---
# <a name="access-control-mechanisms"></a>访问控制机制
您可以控制采用多种方式使用 Windows Communication Foundation (WCF) 的访问。 本主题简要讨论各种机制并提供关于何时使用每种机制的建议；旨在帮助您选择使用正确的机制。 访问技术按复杂程度顺序列出。 最简单的是 <xref:System.Security.Permissions.PrincipalPermissionAttribute>；而最复杂的是标识模型。  
  
 除了这些机制，模拟和委托使用 WCF 所述[委托和模拟](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)。  
  
## <a name="principalpermissionattribute"></a>PrincipalPermissionAttribute  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 用于限制对服务方法的访问。 当该特性应用于方法时，可以用于请求特定调用方的标识或 Windows 组或 ASP.NET 角色的成员身份。 如果使用 X.509 证书对客户端进行身份验证，则将为该客户端提供一个由该证书的主题名称和指纹组成的主标识。  
  
 如果服务用户将始终属于运行服务的同一个 Windows 域的成员，请使用 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 来控制对运行服务的计算机上的资源的访问。 您可以轻松创建已指定访问级别（如，无、只读或读写）的 Windows 组。  
  
 有关使用特性的详细信息，请参阅[如何：使用 PrincipalPermissionAttribute 类限制访问](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)。 有关标识的详细信息，请参阅[服务标识和身份验证](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。  
  
## <a name="aspnet-membership-provider"></a>ASP.NET 成员身份提供程序  
 ASP.NET 的一项功能是成员资格提供程序。 虽然成员资格提供程序在技术上不是访问控制机制，但它允许通过限制可以访问服务终结点的可能标识的集来控制对服务的访问。 成员资格功能包括一个可以用用户名/密码组合（允许网站用户开立该网站的帐户）来填充的数据库。 若要访问使用成员资格提供程序的服务，用户必须使用自己的用户名和密码登录。  
  
> [!NOTE]
>  您首先必须填充的 WCF 服务可以使用它进行授权之前，使用 ASP.NET 功能的数据库。  
  
 如果已具有现有的 ASP.NET Web 站点中的成员资格数据库，并且你想要启用相同的用户可以使用你的服务，具有相同用户名和密码授权，还可以使用成员资格功能。  
  
 有关使用 WCF 服务中的成员资格功能的详细信息，请参阅[如何：使用 ASP.NET 成员资格提供程序](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)。  
  
## <a name="aspnet-role-provider"></a>ASP.NET 角色提供程序  
 ASP.NET 的另一个功能是能够使用角色管理授权。 ASP.NET 角色提供程序，开发人员为用户创建角色，并且每个用户分配给一个或多个角色。 使用成员资格提供程序，如角色和分配存储在数据库中，并可以使用提供的 ASP.NET 角色提供程序的特定实现的工具来填充。 作为成员资格功能，使用 WCF 开发人员信息可用于在数据库中授权服务用户角色。 例如，他们可以将该角色提供程序与上述 `PrincipalPermissionAttribute` 访问控制机制结合使用。  
  
 如果你有现有的 ASP.NET 角色提供程序数据库并想要在您的 WCF 服务中使用的规则和用户分配相同的组，还可以使用 ASP.NET 角色提供程序。  
  
 有关使用角色提供程序功能的详细信息，请参阅[如何：与服务一起使用 ASP.NET 角色提供程序](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)。  
  
## <a name="authorization-manager"></a>授权管理器  
 另一项功能将授权管理器 (AzMan) 与 ASP.NET 角色提供程序客户端进行授权相结合。 当 ASP.NET 托管的 Web 服务时，AzMan 可以集成到应用程序，以便通过 AzMan 完成向服务的授权。 ASP.NET 角色管理器提供了一个 API，使你能够管理应用程序角色添加和从角色中删除用户以及检查角色成员资格，但它不允许你查询用户是否有权执行命名的任务或操作。 AzMan 允许您定义单个操作，然后将这些操作组合成任务。 使用 AZMan，除了可以执行角色检查以外，还可以检查用户是否可以执行某项任务。 角色分配和任务授权可以在应用程序外部配置，也可以在应用程序内部以编程方式执行。 使用 AzMan 管理 Microsoft 管理控制台 (MMC) 管理单元，管理员可以更改角色可以在运行时执行的任务，还可以管理每个用户的角色成员资格。  
  
 如果已有权访问现有 AzMan 安装并想要授权您服务的用户使用 AzMan/角色提供程序组合的功能，还可以使用 AzMan 和 ASP.NET 角色提供程序。  
  
 AzMan 和 ASP.NET 角色提供程序有关的详细信息，请参阅[How To:使用授权管理器 (AzMan) 与 ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=88951)。 有关为 WCF 服务使用 AzMan 和角色提供程序的详细信息，请参阅[如何：将 ASP.NET 授权管理器角色提供程序用于服务](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)。  
  
## <a name="identity-model"></a>标识模型  
 标识模型是一组 API，可以用于管理用于向客户端授权的声明和策略。 使用标识模型，可以检查包含在调用方用于将其自身向服务进行身份验证的凭据中的每个声明，将这些声明与服务策略的集进行比较，然后基于比较结果授予或拒绝访问权限。  
  
 如果在授予访问权限之前需要良好的控制以及可以设置特定的条件，请使用标识模型。 例如，在使用 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 时，标准不过是对用户的标识进行身份验证以及该用户标识属于特定的角色。 相比之下，使用标识模型，您可以创建如下策略：规定用户必须年满 18 周岁，并且必须持有有效的驾驶执照才准许查看文档。  
  
 您可以从标识模型基于声明的访问控制中获益的一个示例是在颁发的令牌方案中使用联合身份验证凭据的情形。 有关联合身份验证和已颁发的令牌的详细信息，请参阅[联合身份验证和颁发令牌](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)。  
  
 有关标识模型的详细信息，请参阅[管理声明和使用标识模型的授权](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [如何：使用 PrincipalPermissionAttribute 类限制访问](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [如何：与服务一起使用 ASP.NET 角色提供程序](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [如何：将用于服务 ASP.NET 授权管理器角色提供程序](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)
- [使用标识模型管理声明和授权](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [委托和模拟](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
