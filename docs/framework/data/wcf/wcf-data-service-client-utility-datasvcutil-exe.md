---
title: WCF 数据服务客户端实用工具 (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 7632362339cf9e23599f4f688f98cbc1d0b32114
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894246"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a><span data-ttu-id="d1404-102">WCF 数据服务客户端实用工具 (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="d1404-102">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>

<span data-ttu-id="d1404-103">DataSvcUtil 是 WCF 数据服务提供的命令行工具，它使用[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]源，并生成从 .NET Framework 客户端应用程序访问数据服务所需的客户端数据服务类。</span><span class="sxs-lookup"><span data-stu-id="d1404-103">DataSvcUtil.exe is a command-line tool provided by WCF Data Services that consumes an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed and generates the client data service classes that are needed to access a data service from a .NET Framework client application.</span></span> <span data-ttu-id="d1404-104">通过使用以下元数据源，该实用工具可以生成数据类：</span><span class="sxs-lookup"><span data-stu-id="d1404-104">This utility can generate data classes by using the following metadata sources:</span></span>

- <span data-ttu-id="d1404-105">数据服务的根 URI。</span><span class="sxs-lookup"><span data-stu-id="d1404-105">The root URI of a data service.</span></span> <span data-ttu-id="d1404-106">该实用工具会请求描述数据服务所公开的数据模型的服务元数据文档。</span><span class="sxs-lookup"><span data-stu-id="d1404-106">The utility requests the service metadata document, which describes the data model exposed by the data service.</span></span> <span data-ttu-id="d1404-107">有关详细信息，请[参阅 OData：服务元数据](https://go.microsoft.com/fwlink/?LinkId=186070)文档。</span><span class="sxs-lookup"><span data-stu-id="d1404-107">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span>

- <span data-ttu-id="d1404-108">一种数据模型文件（csdl），该文件是使用 "模型定义语言" （csdl）定义的， [如\[MC\]中定义的那样：概念架构定义文件格式](https://go.microsoft.com/fwlink/?LinkID=159072)规范。</span><span class="sxs-lookup"><span data-stu-id="d1404-108">A data model file (.csdl) defined by using the conceptual schema definition language (CSDL), as defined in the [\[MC-CSDL\]: Conceptual Schema Definition File Format](https://go.microsoft.com/fwlink/?LinkID=159072) specification.</span></span>

- <span data-ttu-id="d1404-109">使用随实体框架提供的实体数据模型工具创建的 .edmx 文件。</span><span class="sxs-lookup"><span data-stu-id="d1404-109">An .edmx file created by using the Entity Data Model tools that are provided with the Entity Framework.</span></span> <span data-ttu-id="d1404-110">有关详细信息，请参阅[ \[MC-EDMX\]：用于数据服务打包格式](https://go.microsoft.com/fwlink/?LinkID=178833)规范的实体数据模型。</span><span class="sxs-lookup"><span data-stu-id="d1404-110">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification.</span></span>

<span data-ttu-id="d1404-111">有关详细信息，请参阅[如何：手动生成客户端数据服务](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)类。</span><span class="sxs-lookup"><span data-stu-id="d1404-111">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>

<span data-ttu-id="d1404-112">DataSvcUtil 工具安装在 .NET Framework 目录中。</span><span class="sxs-lookup"><span data-stu-id="d1404-112">The DataSvcUtil.exe tool is installed in the .NET Framework directory.</span></span> <span data-ttu-id="d1404-113">在许多情况下，它位于*C:\Windows\Microsoft.NET\Framework\v4.0*中。</span><span class="sxs-lookup"><span data-stu-id="d1404-113">In many cases, this is located in *C:\Windows\Microsoft.NET\Framework\v4.0*.</span></span> <span data-ttu-id="d1404-114">对于64位系统，它位于*C:\Windows\Microsoft.NET\Framework64\v4.0*中。</span><span class="sxs-lookup"><span data-stu-id="d1404-114">For 64-bit systems, this is located in *C:\Windows\Microsoft.NET\Framework64\v4.0*.</span></span> <span data-ttu-id="d1404-115">还可以从 Visual Studio 开发人员命令提示访问 DataSvcUtil 工具。</span><span class="sxs-lookup"><span data-stu-id="d1404-115">You can also access the DataSvcUtil.exe tool from Developer Command Prompt for Visual Studio.</span></span>

## <a name="syntax"></a><span data-ttu-id="d1404-116">语法</span><span class="sxs-lookup"><span data-stu-id="d1404-116">Syntax</span></span>

```console
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a><span data-ttu-id="d1404-117">参数</span><span class="sxs-lookup"><span data-stu-id="d1404-117">Parameters</span></span>

|<span data-ttu-id="d1404-118">选项</span><span class="sxs-lookup"><span data-stu-id="d1404-118">Option</span></span>|<span data-ttu-id="d1404-119">描述</span><span class="sxs-lookup"><span data-stu-id="d1404-119">Description</span></span>|
|------------|-----------------|
|`/dataservicecollection`|<span data-ttu-id="d1404-120">指定还生成了将对象绑定到控件所需的代码。</span><span class="sxs-lookup"><span data-stu-id="d1404-120">Specifies that the code required to bind objects to controls is also generated.</span></span>|
|`/help`<br /><br /> <span data-ttu-id="d1404-121">或</span><span class="sxs-lookup"><span data-stu-id="d1404-121">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="d1404-122">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="d1404-122">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="d1404-123">`/in:`*文件\<>*</span><span class="sxs-lookup"><span data-stu-id="d1404-123">`/in:` *\<file>*</span></span>|<span data-ttu-id="d1404-124">指定 .csdl 或 .edmx 文件或该文件所在的目录。</span><span class="sxs-lookup"><span data-stu-id="d1404-124">Specifies the .csdl or .edmx file or a directory where the file is located.</span></span>|
|<span data-ttu-id="d1404-125">`/language:`[VB&#124;CSharp]</span><span class="sxs-lookup"><span data-stu-id="d1404-125">`/language:`[VB&#124;CSharp]</span></span>|<span data-ttu-id="d1404-126">指定生成的源代码文件的语言。</span><span class="sxs-lookup"><span data-stu-id="d1404-126">Specifies the language for the generated source code files.</span></span> <span data-ttu-id="d1404-127">默认语言为 C#。</span><span class="sxs-lookup"><span data-stu-id="d1404-127">The language defaults to C#.</span></span>|
|`/nologo`|<span data-ttu-id="d1404-128">禁止显示版权信息。</span><span class="sxs-lookup"><span data-stu-id="d1404-128">Suppresses the copyright message from displaying.</span></span>|
|<span data-ttu-id="d1404-129">`/out:`*文件\<>*</span><span class="sxs-lookup"><span data-stu-id="d1404-129">`/out:` *\<file>*</span></span>|<span data-ttu-id="d1404-130">指定包含生成的客户端数据服务类的源代码文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d1404-130">Specifies the name of the source code file that contains the generated client data service classes.</span></span>|
|<span data-ttu-id="d1404-131">`/uri:`*字符串\<>*</span><span class="sxs-lookup"><span data-stu-id="d1404-131">`/uri:` *\<string>*</span></span>|<span data-ttu-id="d1404-132">OData 源的 URI。</span><span class="sxs-lookup"><span data-stu-id="d1404-132">The URI of the OData feed.</span></span>|
|<span data-ttu-id="d1404-133">`/version:`[1.0&#124;2.0]</span><span class="sxs-lookup"><span data-stu-id="d1404-133">`/version:`[1.0&#124;2.0]</span></span>|<span data-ttu-id="d1404-134">指定 OData 最高的接受版本。</span><span class="sxs-lookup"><span data-stu-id="d1404-134">Specifies the highest accepted version of OData.</span></span> <span data-ttu-id="d1404-135">根据返回的数据服务元数据`DataServiceVersion`中的 DataService 元素的属性确定版本。</span><span class="sxs-lookup"><span data-stu-id="d1404-135">The version is determined based on the `DataServiceVersion` attribute of the DataService element in the returned data service metadata.</span></span> <span data-ttu-id="d1404-136">有关详细信息，请参阅[数据服务版本控制](data-service-versioning-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d1404-136">For more information, see [Data Service Versioning](data-service-versioning-wcf-data-services.md).</span></span> <span data-ttu-id="d1404-137">指定`/dataservicecollection`参数时，还必须指定`/version:2.0`启用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="d1404-137">When you specify the `/dataservicecollection` parameter, you must also specify `/version:2.0` to enable data binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d1404-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1404-138">See also</span></span>

- [<span data-ttu-id="d1404-139">生成数据服务客户端库</span><span class="sxs-lookup"><span data-stu-id="d1404-139">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="d1404-140">如何：添加数据服务引用</span><span class="sxs-lookup"><span data-stu-id="d1404-140">How to: Add a Data Service Reference</span></span>](how-to-add-a-data-service-reference-wcf-data-services.md)
