---
title: 自定义数据服务提供程序（WCF 数据服务）
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
ms.openlocfilehash: 4a6079db5e969154c4a9bb6451dd7c698c6d2088
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780381"
---
# <a name="custom-data-service-providers-wcf-data-services"></a>自定义数据服务提供程序（WCF 数据服务）
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 包括一组提供程序，用于基于后期绑定数据类型定义数据模型。  
  
|提供程序|描述|  
|--------------|-----------------|  
|元数据提供程序|这是核心的自定义数据服务提供程序，用于通过实现 <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 接口在运行时定义自定义数据模型。|  
|查询提供程序|该提供程序用于对使用 <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 接口定义的自定义数据模型执行查询。 查询提供程序通过实现 <xref:System.Data.Services.Providers.IDataServiceQueryProvider> 接口而创建。|  
|更新提供程序|该提供程序用于更新在自定义数据服务提供程序中公开的类型和管理并发性。 更新提供程序通过实现 <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> 接口而创建。|  
|分页提供程序|该提供程序用于与自定义数据服务提供程序一起启用服务器驱动的分页支持。 自定义数据服务的分页提供程序通过实现 <xref:System.Data.Services.Providers.IDataServicePagingProvider> 接口而创建。|  
|流提供程序|此提供程序用于以流形式公开二进制大型对象数据类型。 流提供程序通过实现 <xref:System.Data.Services.Providers.IDataServiceStreamProvider> 接口而创建。 流提供程序还可与实体框架提供程序和反射数据源提供程序一起使用。 有关详细信息，请参阅[流式处理提供程序](streaming-provider-wcf-data-services.md)。|  
  
 有关详细信息，请参阅[OData SDK](https://go.microsoft.com/fwlink/?LinkId=186069)中的[自定义数据服务提供程序](https://go.microsoft.com/fwlink/?LinkID=186850)和[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]提供程序工具包一文。  
  
## <a name="see-also"></a>请参阅

- [数据服务提供程序](data-services-providers-wcf-data-services.md)
- [实体框架提供程序](entity-framework-provider-wcf-data-services.md)
- [反射提供程序](reflection-provider-wcf-data-services.md)
