---
title: "如何：启用对数据服务的访问（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b41de296143d325ba0e1932831d4a3ef1bd7dc80
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a>如何：启用对数据服务的访问（WCF 数据服务）
在 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]中，您必须显式授予对数据服务公开的资源的访问权限。 这意味着您在创建新的数据服务之后，仍必须显式提供对实体集形式的各个资源的访问。 本主题演示如何启用读取和写入访问权限五个实体设置完毕后创建的 Northwind 数据服务中[快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。 由于 <xref:System.Data.Services.EntitySetRights> 枚举是通过使用 <xref:System.FlagsAttribute> 定义的，因此您可以使用逻辑 OR 运算符来为单个实体集指定多个权限。  
  
> [!NOTE]
>  任何可以访问该 ASP.NET 应用程序的客户端也能够访问由数据服务公开的资源。 在生产数据服务中，为防止对资源进行未经授权的访问，还应保护应用程序本身的安全。 有关详细信息，请参阅[NIB: ASP.NET 安全](http://msdn.microsoft.com/en-us/04b37532-18d9-40b4-8e5f-ee09a70b311d)。  
  
### <a name="to-enable-access-to-the-data-service"></a>启用对数据服务的访问  
  
-   在数据服务的代码中，用下列代码替换 `InitializeService` 函数中的占位符代码：  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     这使得客户端能够对 `Orders` 和 `Order_Details` 实体集进行读写访问，以及对 `Customers` 实体集进行只读访问。  
  
## <a name="see-also"></a>另请参阅  
 [如何： 开发在 IIS 上运行的 WCF 数据服务](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)  
 [配置数据服务](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
