---
title: "生成数据服务客户端库（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6adbaafe170cf3f5398677d5df3b3d2ff0a95abe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>生成数据服务客户端库（WCF 数据服务）
数据服务实现[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]可以返回描述公开的数据模型的服务元数据文档[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]源。 有关详细信息，请参阅[OData： 服务元数据文档](http://go.microsoft.com/fwlink/?LinkId=186070)。 你可以使用**添加服务引用**对话框在 Visual Studio 中添加对引用[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-基于服务。 当你使用此工具以添加对返回的元数据的引用[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]送入在客户端项目，请执行下列操作：  
  
-   从数据服务请求服务元数据文档并截获返回的元数据。  
  
    > [!NOTE]
    >  返回的元数据作为 .edmx 文件存储在客户端项目中。 此 .edmx 文件无法通过实体数据模型设计器打开，因为此文件的格式与实体框架所使用的 .edmx 文件的格式不相同。 可以通过使用 XML 编辑器或任何文本编辑器查看此元数据文件。 有关详细信息，请参阅[ \[MC-EDMX\]： 用于数据服务打包格式的实体数据模型](http://go.microsoft.com/fwlink/?LinkID=178833)规范  
  
-   作为从 <xref:System.Data.Services.Client.DataServiceContext> 继承的实体容器类生成数据服务的表示形式。 此生成的实体容器类与实体数据模型工具生成的实体容器类似。 有关详细信息，请参阅[对象服务概述 (Entity Framework)](http://msdn.microsoft.com/en-us/43014cf9-c9cb-4538-bfbb-197820b60038)。  
  
-   为在服务元数据中发现的数据模型类型生成数据类。  
  
-   在项目中添加对 `System.Data.Services.Client` 程序集的引用。  
  
 有关详细信息，请参阅[如何： 添加数据服务引用](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)。  
  
 也可以通过使用生成的客户端数据服务类[DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)工具在命令提示符。 有关详细信息，请参阅[如何： 手动生成客户端数据服务类](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)。  
  
## <a name="client-data-type-mapping"></a>客户端数据类型映射  
 当你使用**添加服务引用**Visual Studio 中的对话框或`DataSvcUtil.exe`工具生成基于的客户端数据类[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]馈送，.NET Framework 数据类型映射到中的基元类型数据模型，如下所示：  
  
|数据模型类型|.NET Framework 数据类型|  
|---------------------|------------------------------|  
|`Edm.Binary`|<xref:System.Byte> `[]`|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 有关详细信息，请参阅[OData： 基元数据类型](http://go.microsoft.com/fwlink/?LinkId=186072)。  
  
## <a name="see-also"></a>请参阅  
 [WCF Data Services 客户端库](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
