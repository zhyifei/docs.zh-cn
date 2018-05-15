---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 8a16e3fe0cea04813be50a83f906170199e78e3e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="linq-to-dataset"></a><span data-ttu-id="dfff9-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="dfff9-102">LINQ to DataSet</span></span>
<span data-ttu-id="dfff9-103">使用 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 可以更快更容易地查询在 <xref:System.Data.DataSet> 对象中缓存的数据。</span><span class="sxs-lookup"><span data-stu-id="dfff9-103">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="dfff9-104">具体而言，通过使开发人员能够使用编程语言本身而不是通过使用单独的查询语言来编写查询，[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 可以简化查询。</span><span class="sxs-lookup"><span data-stu-id="dfff9-104">Specifically, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="dfff9-105">这是非常适合 Visual Studio 开发人员，他们现在可以充分利用编译时语法检查、 静态类型和提供的 Visual Studio 在查询中的 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="dfff9-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="dfff9-106"> 也可用于查询从一个或多个数据源合并的数据。</span><span class="sxs-lookup"><span data-stu-id="dfff9-106"> can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="dfff9-107">这可以使许多需要灵活表示和处理数据的方案（例如查询本地聚合的数据和 Web 应用程序中的中间层缓存）能够实现。</span><span class="sxs-lookup"><span data-stu-id="dfff9-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="dfff9-108">具体地说，一般报告、分析和业务智能应用程序将需要这种操作方法。</span><span class="sxs-lookup"><span data-stu-id="dfff9-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="dfff9-109">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]主要通过中的扩展方法公开功能<xref:System.Data.DataRowExtensions>和<xref:System.Data.DataTableExtensions>类。</span><span class="sxs-lookup"><span data-stu-id="dfff9-109">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="dfff9-110"> 基于并使用现有[!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)]体系结构，不能替换[!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)]应用程序代码中。</span><span class="sxs-lookup"><span data-stu-id="dfff9-110"> builds on and uses the existing [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] architecture, and is not meant to replace [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] in application code.</span></span> <span data-ttu-id="dfff9-111">现有的 ADO.NET 2.0 代码将继续在 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 应用程序中有效。</span><span class="sxs-lookup"><span data-stu-id="dfff9-111">Existing ADO.NET 2.0 code will continue to function in a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] application.</span></span> <span data-ttu-id="dfff9-112">下图阐释了 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 与 [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] 和数据存储区的关系。</span><span class="sxs-lookup"><span data-stu-id="dfff9-112">The relationship of [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] and the data store is illustrated in the following diagram.</span></span>  
  
 <span data-ttu-id="dfff9-113">![LINQ to DataSet 基于 ADO.NET 提供程序](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")</span><span class="sxs-lookup"><span data-stu-id="dfff9-113">![LINQ to DataSet is based on the ADO.NET Provider](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dfff9-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="dfff9-114">In This Section</span></span>  
 [<span data-ttu-id="dfff9-115">入门</span><span class="sxs-lookup"><span data-stu-id="dfff9-115">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="dfff9-116">编程指南</span><span class="sxs-lookup"><span data-stu-id="dfff9-116">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="dfff9-117">参考</span><span class="sxs-lookup"><span data-stu-id="dfff9-117">Reference</span></span>  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="dfff9-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfff9-118">See Also</span></span>  
 [<span data-ttu-id="dfff9-119">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="dfff9-119">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="dfff9-120">LINQ 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dfff9-120">LINQ and ADO.NET</span></span>](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 [<span data-ttu-id="dfff9-121">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dfff9-121">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
