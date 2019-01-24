---
title: ADO.NET 概述
ms.date: 03/30/2017
ms.assetid: ee3bc1d8-11db-4be4-89eb-c708cf04117d
ms.openlocfilehash: 6769370396fc263f237a2884435630a2930b882b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714381"
---
# <a name="adonet-overview"></a><span data-ttu-id="d526d-102">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="d526d-102">ADO.NET Overview</span></span>
<span data-ttu-id="d526d-103">ADO.NET 提供对诸如 SQL Server 和 XML 这样的数据源以及通过 OLE DB 和 ODBC 公开的数据源的一致访问。</span><span class="sxs-lookup"><span data-stu-id="d526d-103">ADO.NET provides consistent access to data sources such as SQL Server and XML, and to data sources exposed through OLE DB and ODBC.</span></span> <span data-ttu-id="d526d-104">共享数据的使用方应用程序可以使用 ADO.NET 连接到这些数据源，并可以检索、处理和更新其中包含的数据。</span><span class="sxs-lookup"><span data-stu-id="d526d-104">Data-sharing consumer applications can use ADO.NET to connect to these data sources and retrieve, handle, and update the data that they contain.</span></span>  
  
 <span data-ttu-id="d526d-105">ADO.NET 通过数据处理将数据访问分解为多个可以单独使用或一前一后使用的不连续组件。</span><span class="sxs-lookup"><span data-stu-id="d526d-105">ADO.NET separates data access from data manipulation into discrete components that can be used separately or in tandem.</span></span> <span data-ttu-id="d526d-106">ADO.NET 包含用于连接到数据库、执行命令和检索结果的 .NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="d526d-106">ADO.NET includes .NET Framework data providers for connecting to a database, executing commands, and retrieving results.</span></span> <span data-ttu-id="d526d-107">这些结果或者被直接处理，放在 ADO.NET <xref:System.Data.DataSet> 对象中以便以特别的方式向用户公开，并与来自多个源的数据组合；或者在层之间传递。</span><span class="sxs-lookup"><span data-stu-id="d526d-107">Those results are either processed directly, placed in an ADO.NET <xref:System.Data.DataSet> object in order to be exposed to the user in an ad hoc manner, combined with data from multiple sources, or passed between tiers.</span></span> <span data-ttu-id="d526d-108">`DataSet` 对象也可以独立于 .NET Framework 数据提供程序，用于管理应用程序本地的数据或源自 XML 的数据。</span><span class="sxs-lookup"><span data-stu-id="d526d-108">The `DataSet` object can also be used independently of a .NET Framework data provider to manage data local to the application or sourced from XML.</span></span>  
  
 <span data-ttu-id="d526d-109">ADO.NET 类位于 System.Data.dll 中，并与 System.Xml.dll 中的 XML 类集成。</span><span class="sxs-lookup"><span data-stu-id="d526d-109">The ADO.NET classes are found in System.Data.dll, and are integrated with the XML classes found in System.Xml.dll.</span></span> <span data-ttu-id="d526d-110">有关连接到的数据库的示例代码检索数据，并在控制台窗口中，然后显示该数据请参阅[ADO.NET 代码示例](../../../../docs/framework/data/adonet/ado-net-code-examples.md)。</span><span class="sxs-lookup"><span data-stu-id="d526d-110">For sample code that connects to a database, retrieves data from it, and then displays that data in a console window, see [ADO.NET Code Examples](../../../../docs/framework/data/adonet/ado-net-code-examples.md).</span></span>  
  
 <span data-ttu-id="d526d-111">ADO.NET 向编写托管代码的开发人员提供类似于 ActiveX 数据对象 (ADO) 向本机组件对象模型 (COM) 开发人员提供的功能。</span><span class="sxs-lookup"><span data-stu-id="d526d-111">ADO.NET provides functionality to developers who write managed code similar to the functionality provided to native component object model (COM) developers by ActiveX Data Objects (ADO).</span></span> <span data-ttu-id="d526d-112">建议您在 .NET 应用程序中使用 ADO.NET 而不使用 ADO 来访问数据。</span><span class="sxs-lookup"><span data-stu-id="d526d-112">We recommend that you use ADO.NET, not ADO, for accessing data in your .NET applications.</span></span>  
  
 <span data-ttu-id="d526d-113">ADO.NET 在 .NET Framework 中提供最直接的数据访问方法。</span><span class="sxs-lookup"><span data-stu-id="d526d-113">ADO.NET provides the most direct method of data access within the .NET Framework.</span></span> <span data-ttu-id="d526d-114">有关更高级别的抽象，让应用程序能够对概念模型而不是基础存储模型的说明，请参阅[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)。</span><span class="sxs-lookup"><span data-stu-id="d526d-114">For a higher-level abstraction that allows applications to work against a conceptual model instead of the underlying storage model, see the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).</span></span>  
  
 <span data-ttu-id="d526d-115">**隐私声明**:System.Data.dll、System.Data.Design.dll、System.Data.OracleClient.dll、System.Data.SqlXml.dll、System.Data.Linq.dll、System.Data.SqlServerCe.dll 和 System.Data.DataSetExtensions.dll 程序集不区分用户的隐私数据和非隐私数据。</span><span class="sxs-lookup"><span data-stu-id="d526d-115">**Privacy Statement**: The System.Data.dll, System.Data.Design.dll, System.Data.OracleClient.dll, System.Data.SqlXml.dll, System.Data.Linq.dll, System.Data.SqlServerCe.dll, and System.Data.DataSetExtensions.dll assemblies do not distinguish between a user's private data and non-private data.</span></span>  <span data-ttu-id="d526d-116">这些程序集不收集、存储或传输任何用户隐私数据。</span><span class="sxs-lookup"><span data-stu-id="d526d-116">These assemblies do not collect, store, or transport any user's private data.</span></span> <span data-ttu-id="d526d-117">不过，第三方应用程序可能会使用这些程序集收集、存储或传输用户的隐私数据。</span><span class="sxs-lookup"><span data-stu-id="d526d-117">However, third-party applications might collect, store, or transport a user's private data using these assemblies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d526d-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="d526d-118">In This Section</span></span>  
 [<span data-ttu-id="d526d-119">ADO.NET 体系结构</span><span class="sxs-lookup"><span data-stu-id="d526d-119">ADO.NET Architecture</span></span>](../../../../docs/framework/data/adonet/ado-net-architecture.md)  
 <span data-ttu-id="d526d-120">提供 ADO.NET 结构和组件的概述。</span><span class="sxs-lookup"><span data-stu-id="d526d-120">Provides an overview of the architecture and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="d526d-121">ADO.NET 技术选项和准则</span><span class="sxs-lookup"><span data-stu-id="d526d-121">ADO.NET Technology Options and Guidelines</span></span>](../../../../docs/framework/data/adonet/ado-net-technology-options-and-guidelines.md)  
 <span data-ttu-id="d526d-122">描述实体数据平台附带的产品和技术。</span><span class="sxs-lookup"><span data-stu-id="d526d-122">Describes the products and technologies included with the Entity Data Platform.</span></span>  
  
 [<span data-ttu-id="d526d-123">LINQ 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d526d-123">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 <span data-ttu-id="d526d-124">描述如何在 ADO.NET 中实现语言集成查询 (LINQ) 并提供指向相关主题的链接。</span><span class="sxs-lookup"><span data-stu-id="d526d-124">Describes how Language-Integrated Query (LINQ) is implemented in ADO.NET and provides links to relevant topics.</span></span>  
  
 [<span data-ttu-id="d526d-125">.NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="d526d-125">.NET Framework Data Providers</span></span>](../../../../docs/framework/data/adonet/data-providers.md)  
 <span data-ttu-id="d526d-126">提供有关 .NET Framework 数据提供程序的设计的概述以及有关随 ADO.NET 提供的 .NET Framework 数据提供程序的概述。</span><span class="sxs-lookup"><span data-stu-id="d526d-126">Provides an overview of the design of the .NET Framework data provider and of the .NET Framework data providers that are included with ADO.NET.</span></span>  
  
 [<span data-ttu-id="d526d-127">ADO.NET 数据集</span><span class="sxs-lookup"><span data-stu-id="d526d-127">ADO.NET DataSets</span></span>](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 <span data-ttu-id="d526d-128">提供有关 `DataSet` 设计和组件的概述。</span><span class="sxs-lookup"><span data-stu-id="d526d-128">Provides an overview of the `DataSet` design and components.</span></span>  
  
 [<span data-ttu-id="d526d-129">ADO.NET 中的并行执行</span><span class="sxs-lookup"><span data-stu-id="d526d-129">Side-by-Side Execution in ADO.NET</span></span>](../../../../docs/framework/data/adonet/side-by-side-execution.md)  
 <span data-ttu-id="d526d-130">讨论 ADO.NET 各个版本之间的区别及其对并行执行和应用程序兼容性的影响。</span><span class="sxs-lookup"><span data-stu-id="d526d-130">Discusses differences in ADO.NET versions and their effect on side-by-side execution and application compatibility.</span></span>  
  
 [<span data-ttu-id="d526d-131">ADO.NET 代码示例</span><span class="sxs-lookup"><span data-stu-id="d526d-131">ADO.NET Code Examples</span></span>](../../../../docs/framework/data/adonet/ado-net-code-examples.md)  
 <span data-ttu-id="d526d-132">提供使用 ADO.NET 数据提供程序检索数据的代码示例。</span><span class="sxs-lookup"><span data-stu-id="d526d-132">Provides code samples that retrieve data using the ADO.NET data providers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d526d-133">相关章节</span><span class="sxs-lookup"><span data-stu-id="d526d-133">Related Sections</span></span>  
 [<span data-ttu-id="d526d-134">ADO.NET 新增功能</span><span class="sxs-lookup"><span data-stu-id="d526d-134">What's New in ADO.NET</span></span>](../../../../docs/framework/data/adonet/whats-new.md)  
 <span data-ttu-id="d526d-135">介绍 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d526d-135">Introduces features that are new in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
 [<span data-ttu-id="d526d-136">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="d526d-136">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="d526d-137">描述使用 ADO.NET 时的安全编码做法。</span><span class="sxs-lookup"><span data-stu-id="d526d-137">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="d526d-138">ADO.NET 中的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="d526d-138">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 <span data-ttu-id="d526d-139">描述 .NET Framework 数据类型与 .NET Framework 数据提供程序之间的数据类型映射。</span><span class="sxs-lookup"><span data-stu-id="d526d-139">Describes data type mappings between .NET Framework data types and the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="d526d-140">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="d526d-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="d526d-141">说明如何连接到数据源、检索数据和修改数据。</span><span class="sxs-lookup"><span data-stu-id="d526d-141">Describes how to connect to a data source, retrieve data, and modify data.</span></span> <span data-ttu-id="d526d-142">这包括 `DataReaders` 和 `DataAdapters`。</span><span class="sxs-lookup"><span data-stu-id="d526d-142">This includes `DataReaders` and `DataAdapters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d526d-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="d526d-143">See also</span></span>
- [<span data-ttu-id="d526d-144">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d526d-144">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="d526d-145">在 Visual Studio 中访问数据</span><span class="sxs-lookup"><span data-stu-id="d526d-145">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
- [<span data-ttu-id="d526d-146">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="d526d-146">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
