---
title: WCF 数据服务客户端实用工具 (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 7c9b713571cea3d2c8c5f6511f2cfab7e87b80ee
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43739187"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a><span data-ttu-id="e591f-102">WCF 数据服务客户端实用工具 (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="e591f-102">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>

<span data-ttu-id="e591f-103">DataSvcUtil.exe 是由 WCF 数据服务使用提供的命令行工具[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]源，并生成从.NET Framework 客户端应用程序访问数据服务所需的客户端数据服务类。</span><span class="sxs-lookup"><span data-stu-id="e591f-103">DataSvcUtil.exe is a command-line tool provided by WCF Data Services that consumes an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed and generates the client data service classes that are needed to access a data service from a .NET Framework client application.</span></span> <span data-ttu-id="e591f-104">通过使用以下元数据源，该实用工具可以生成数据类：</span><span class="sxs-lookup"><span data-stu-id="e591f-104">This utility can generate data classes by using the following metadata sources:</span></span>

-   <span data-ttu-id="e591f-105">数据服务的根 URI。</span><span class="sxs-lookup"><span data-stu-id="e591f-105">The root URI of a data service.</span></span> <span data-ttu-id="e591f-106">该实用工具会请求描述数据服务所公开的数据模型的服务元数据文档。</span><span class="sxs-lookup"><span data-stu-id="e591f-106">The utility requests the service metadata document, which describes the data model exposed by the data service.</span></span> <span data-ttu-id="e591f-107">有关详细信息，请参阅[OData： 服务元数据文档](https://go.microsoft.com/fwlink/?LinkId=186070)。</span><span class="sxs-lookup"><span data-stu-id="e591f-107">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span>

-   <span data-ttu-id="e591f-108">使用定义的概念架构定义语言 (CSDL) 中定义的数据模型文件 (.csdl) [ \[MC CSDL\]： 概念架构定义文件格式](https://go.microsoft.com/fwlink/?LinkID=159072)规范。</span><span class="sxs-lookup"><span data-stu-id="e591f-108">A data model file (.csdl) defined by using the conceptual schema definition language (CSDL), as defined in the [\[MC-CSDL\]: Conceptual Schema Definition File Format](https://go.microsoft.com/fwlink/?LinkID=159072) specification.</span></span>

-   <span data-ttu-id="e591f-109">使用随实体框架提供的实体数据模型工具创建的 .edmx 文件。</span><span class="sxs-lookup"><span data-stu-id="e591f-109">An .edmx file created by using the Entity Data Model tools that are provided with the Entity Framework.</span></span> <span data-ttu-id="e591f-110">有关详细信息，请参阅[ \[MC EDMX\]： 用于数据服务打包格式的实体数据模型](https://go.microsoft.com/fwlink/?LinkID=178833)规范。</span><span class="sxs-lookup"><span data-stu-id="e591f-110">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification.</span></span>

<span data-ttu-id="e591f-111">有关详细信息，请参阅[如何： 手动生成客户端数据服务类](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e591f-111">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>

<span data-ttu-id="e591f-112">DataSvcUtil.exe 工具安装在 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 目录中。</span><span class="sxs-lookup"><span data-stu-id="e591f-112">The DataSvcUtil.exe tool is installed in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directory.</span></span> <span data-ttu-id="e591f-113">在许多情况下，它位于*C:\Windows\Microsoft.NET\Framework\v4.0*。</span><span class="sxs-lookup"><span data-stu-id="e591f-113">In many cases, this is located in *C:\Windows\Microsoft.NET\Framework\v4.0*.</span></span> <span data-ttu-id="e591f-114">对于 64 位系统，它位于*C:\Windows\Microsoft.NET\Framework64\v4.0*。</span><span class="sxs-lookup"><span data-stu-id="e591f-114">For 64-bit systems, this is located in *C:\Windows\Microsoft.NET\Framework64\v4.0*.</span></span> <span data-ttu-id="e591f-115">您可以从开发人员命令提示访问 DataSvcUtil.exe 工具，用于 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e591f-115">You can also access the DataSvcUtil.exe tool from Developer Command Prompt for Visual Studio.</span></span>

## <a name="syntax"></a><span data-ttu-id="e591f-116">语法</span><span class="sxs-lookup"><span data-stu-id="e591f-116">Syntax</span></span>

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

### <a name="parameters"></a><span data-ttu-id="e591f-117">参数</span><span class="sxs-lookup"><span data-stu-id="e591f-117">Parameters</span></span>

|<span data-ttu-id="e591f-118">选项</span><span class="sxs-lookup"><span data-stu-id="e591f-118">Option</span></span>|<span data-ttu-id="e591f-119">描述</span><span class="sxs-lookup"><span data-stu-id="e591f-119">Description</span></span>|
|------------|-----------------|
|`/dataservicecollection`|<span data-ttu-id="e591f-120">指定还生成了将对象绑定到控件所需的代码。</span><span class="sxs-lookup"><span data-stu-id="e591f-120">Specifies that the code required to bind objects to controls is also generated.</span></span>|
|`/help`<br /><br /> <span data-ttu-id="e591f-121">- 或 -</span><span class="sxs-lookup"><span data-stu-id="e591f-121">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="e591f-122">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="e591f-122">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="e591f-123">`/in:` *\<文件 >*</span><span class="sxs-lookup"><span data-stu-id="e591f-123">`/in:` *\<file>*</span></span>|<span data-ttu-id="e591f-124">指定 .csdl 或 .edmx 文件或该文件所在的目录。</span><span class="sxs-lookup"><span data-stu-id="e591f-124">Specifies the .csdl or .edmx file or a directory where the file is located.</span></span>|
|<span data-ttu-id="e591f-125">`/language:`[VB&#124;CSharp]</span><span class="sxs-lookup"><span data-stu-id="e591f-125">`/language:`[VB&#124;CSharp]</span></span>|<span data-ttu-id="e591f-126">指定生成的源代码文件的语言。</span><span class="sxs-lookup"><span data-stu-id="e591f-126">Specifies the language for the generated source code files.</span></span> <span data-ttu-id="e591f-127">默认语言为 C#。</span><span class="sxs-lookup"><span data-stu-id="e591f-127">The language defaults to C#.</span></span>|
|`/nologo`|<span data-ttu-id="e591f-128">禁止显示版权信息。</span><span class="sxs-lookup"><span data-stu-id="e591f-128">Suppresses the copyright message from displaying.</span></span>|
|<span data-ttu-id="e591f-129">`/out:` *\<文件 >*</span><span class="sxs-lookup"><span data-stu-id="e591f-129">`/out:` *\<file>*</span></span>|<span data-ttu-id="e591f-130">指定包含生成的客户端数据服务类的源代码文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e591f-130">Specifies the name of the source code file that contains the generated client data service classes.</span></span>|
|<span data-ttu-id="e591f-131">`/uri:` *\<字符串 >*</span><span class="sxs-lookup"><span data-stu-id="e591f-131">`/uri:` *\<string>*</span></span>|<span data-ttu-id="e591f-132">OData 数据源的 URI。</span><span class="sxs-lookup"><span data-stu-id="e591f-132">The URI of the OData feed.</span></span>|
|<span data-ttu-id="e591f-133">`/version:`[1.0&#124;2.0]</span><span class="sxs-lookup"><span data-stu-id="e591f-133">`/version:`[1.0&#124;2.0]</span></span>|<span data-ttu-id="e591f-134">指定 OData 接受的最高版本。</span><span class="sxs-lookup"><span data-stu-id="e591f-134">Specifies the highest accepted version of OData.</span></span> <span data-ttu-id="e591f-135">基于确定版本`DataServiceVersion`返回的数据服务元数据中的 DataService 元素的属性。</span><span class="sxs-lookup"><span data-stu-id="e591f-135">The version is determined based on the `DataServiceVersion` attribute of the DataService element in the returned data service metadata.</span></span> <span data-ttu-id="e591f-136">有关详细信息，请参阅[数据服务版本控制](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e591f-136">For more information, see [Data Service Versioning](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).</span></span> <span data-ttu-id="e591f-137">当指定`/dataservicecollection`参数，则还必须指定`/version:2.0`以启用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="e591f-137">When you specify the `/dataservicecollection` parameter, you must also specify `/version:2.0` to enable data binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="e591f-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="e591f-138">See Also</span></span>

- [<span data-ttu-id="e591f-139">生成数据服务客户端库</span><span class="sxs-lookup"><span data-stu-id="e591f-139">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="e591f-140">如何：添加数据服务引用</span><span class="sxs-lookup"><span data-stu-id="e591f-140">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
