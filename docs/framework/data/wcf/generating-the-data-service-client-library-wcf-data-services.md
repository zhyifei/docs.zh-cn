---
title: 生成数据服务客户端库（WCF 数据服务）
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 999cbaa98c26d2d00b7e8f319ee87f8b07d7f5c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357746"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="ba01d-102">生成数据服务客户端库（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="ba01d-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="ba01d-103">数据服务实现[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]可以返回描述公开的数据模型的服务元数据文档[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]源。</span><span class="sxs-lookup"><span data-stu-id="ba01d-103">A data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] can return a service metadata document that describes the data model exposed by the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span> <span data-ttu-id="ba01d-104">有关详细信息，请参阅[OData： 服务元数据文档](http://go.microsoft.com/fwlink/?LinkId=186070)。</span><span class="sxs-lookup"><span data-stu-id="ba01d-104">For more information, see [OData: Service Metadata Document](http://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="ba01d-105">你可以使用**添加服务引用**对话框在 Visual Studio 中添加对引用[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-基于服务。</span><span class="sxs-lookup"><span data-stu-id="ba01d-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service.</span></span> <span data-ttu-id="ba01d-106">当你使用此工具以添加对返回的元数据的引用[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]送入在客户端项目，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ba01d-106">When you use this tool to add a reference to the metadata returned by an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in a client project, it performs the following actions:</span></span>  
  
-   <span data-ttu-id="ba01d-107">从数据服务请求服务元数据文档并截获返回的元数据。</span><span class="sxs-lookup"><span data-stu-id="ba01d-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba01d-108">返回的元数据作为 .edmx 文件存储在客户端项目中。</span><span class="sxs-lookup"><span data-stu-id="ba01d-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="ba01d-109">此 .edmx 文件无法通过实体数据模型设计器打开，因为此文件的格式与实体框架所使用的 .edmx 文件的格式不相同。</span><span class="sxs-lookup"><span data-stu-id="ba01d-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="ba01d-110">可以通过使用 XML 编辑器或任何文本编辑器查看此元数据文件。</span><span class="sxs-lookup"><span data-stu-id="ba01d-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="ba01d-111">有关详细信息，请参阅[ \[MC-EDMX\]： 用于数据服务打包格式的实体数据模型](http://go.microsoft.com/fwlink/?LinkID=178833)规范</span><span class="sxs-lookup"><span data-stu-id="ba01d-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
-   <span data-ttu-id="ba01d-112">作为从 <xref:System.Data.Services.Client.DataServiceContext> 继承的实体容器类生成数据服务的表示形式。</span><span class="sxs-lookup"><span data-stu-id="ba01d-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="ba01d-113">此生成的实体容器类与实体数据模型工具生成的实体容器类似。</span><span class="sxs-lookup"><span data-stu-id="ba01d-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="ba01d-114">有关详细信息，请参阅[对象服务概述 (Entity Framework)](http://msdn.microsoft.com/library/43014cf9-c9cb-4538-bfbb-197820b60038)。</span><span class="sxs-lookup"><span data-stu-id="ba01d-114">For more information, see [Object Services Overview (Entity Framework)](http://msdn.microsoft.com/library/43014cf9-c9cb-4538-bfbb-197820b60038).</span></span>  
  
-   <span data-ttu-id="ba01d-115">为在服务元数据中发现的数据模型类型生成数据类。</span><span class="sxs-lookup"><span data-stu-id="ba01d-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
-   <span data-ttu-id="ba01d-116">在项目中添加对 `System.Data.Services.Client` 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="ba01d-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="ba01d-117">有关详细信息，请参阅[如何： 添加数据服务引用](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ba01d-117">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="ba01d-118">也可以通过使用生成的客户端数据服务类[DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)工具在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ba01d-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="ba01d-119">有关详细信息，请参阅[如何： 手动生成客户端数据服务类](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ba01d-119">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="ba01d-120">客户端数据类型映射</span><span class="sxs-lookup"><span data-stu-id="ba01d-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="ba01d-121">当你使用**添加服务引用**Visual Studio 中的对话框或`DataSvcUtil.exe`工具生成基于的客户端数据类[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]馈送，.NET Framework 数据类型映射到中的基元类型数据模型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ba01d-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="ba01d-122">数据模型类型</span><span class="sxs-lookup"><span data-stu-id="ba01d-122">Data model type</span></span>|<span data-ttu-id="ba01d-123">.NET Framework 数据类型</span><span class="sxs-lookup"><span data-stu-id="ba01d-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="ba01d-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="ba01d-124"><xref:System.Byte> `[]`</span></span>|  
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
  
 <span data-ttu-id="ba01d-125">有关详细信息，请参阅[OData： 基元数据类型](http://go.microsoft.com/fwlink/?LinkId=186072)。</span><span class="sxs-lookup"><span data-stu-id="ba01d-125">For more information, see [OData: Primitive Data Types](http://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba01d-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba01d-126">See Also</span></span>  
 [<span data-ttu-id="ba01d-127">WCF Data Services 客户端库</span><span class="sxs-lookup"><span data-stu-id="ba01d-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [<span data-ttu-id="ba01d-128">快速入门</span><span class="sxs-lookup"><span data-stu-id="ba01d-128">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
