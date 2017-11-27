---
title: "将数据公开为服务（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 122d05d5e4bd7690f32b22453dccbfaab2fb7f13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="exposing-your-data-as-a-service-wcf-data-services"></a>将数据公开为服务（WCF 数据服务）
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]与 Visual Studio 使你能够更轻松地定义服务以公开你的数据作为集成[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]馈送。 创建数据服务公开[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]源涉及以下基本步骤：  
  
1.  **定义****数据模型**。 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]以本机方式支持数据模型在基于[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)。 有关详细信息，请参阅[如何： 创建数据服务使用 ADO.NET 实体框架数据源](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)。  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 还支持基于公共语言运行时 (CLR) 对象的数据模型，这些对象返回 <xref:System.Linq.IQueryable%601> 接口的实例。 通过此功能，您可以在 .NET Framework 中部署基于列表、数组和集合的数据服务。 若要启用针对这些数据结构的创建、更新和删除操作，还必须实现 <xref:System.Data.Services.IUpdatable> 接口。 有关详细信息，请参阅[如何： 创建数据服务使用反射提供程序](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)。  
  
     对于更高级方案，[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]包括一套提供程序使您能够定义基于后期绑定数据类型的数据模型。 有关详细信息，请参阅[自定义数据服务提供商](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)。  
  
2.  **创建数据服务。** 大多数基本数据服务公开一个从 <xref:System.Data.Services.DataService%601> 类继承的类和一个作为实体容器的命名空间限定名称的 `T` 类型。 有关详细信息，请参阅 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)的信息。  
  
3.  **配置数据服务。** 默认情况下， [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 会禁用对实体容器所公开的资源的访问。 通过 <xref:System.Data.Services.DataServiceConfiguration> 接口可以配置对资源和服务操作的访问、指定支持的 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 版本并定义其他服务范围的行为，例如批处理行为或可在单个响应中返回的最大实体数。 有关详细信息，请参阅[配置数据服务](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)。  
  
 有关如何创建基于 Northwind 示例数据库的简单数据服务的示例，请参阅[快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。  
  
## <a name="see-also"></a>另请参阅  
 [入门](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [概述](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)
