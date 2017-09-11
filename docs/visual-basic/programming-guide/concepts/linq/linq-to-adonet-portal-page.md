---
title: "LINQ to ADO.NET (门户网站页) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: df23be4b87860afcde03328d0fe47e305860f5f7
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-adonet-portal-page"></a><span data-ttu-id="726ba-102">LINQ to ADO.NET（门户网站页）</span><span class="sxs-lookup"><span data-stu-id="726ba-102">LINQ to ADO.NET (Portal Page)</span></span>
[!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)]<span data-ttu-id="726ba-103">使您可以通过任何可枚举对象中查询[!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)]使用[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]编程模型。</span><span class="sxs-lookup"><span data-stu-id="726ba-103"> enables you to query over any enumerable object in [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] by using the [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] programming model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="726ba-104">[!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)]文档位于.NET Framework SDK 的 ADO.NET 部分中︰ [LINQ 和 ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec)。</span><span class="sxs-lookup"><span data-stu-id="726ba-104">The [!INCLUDE[linq_adonet](../../../../csharp/programming-guide/concepts/linq/includes/linq_adonet_md.md)] documentation is located in the ADO.NET section of the .NET Framework SDK: [LINQ and ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).</span></span>  
  
 <span data-ttu-id="726ba-105">有三种独立的 ADO.NET [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] 技术：[!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)]、[!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] 和 [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="726ba-105">There are three separate ADO.NET [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] technologies: [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)], [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], and [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)].</span></span> [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)]<span data-ttu-id="726ba-106">提供了更丰富且进行了优化查询<xref:System.Data.DataSet>，[!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]使您可以直接查询[!INCLUDE[ssNoVersion](../../../../csharp/programming-guide/concepts/linq/includes/ssnoversion_md.md)]数据库架构，并[!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)]允许您查询[!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)]。</xref:System.Data.DataSet></span><span class="sxs-lookup"><span data-stu-id="726ba-106"> provides richer, optimized querying over the <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] enables you to directly query [!INCLUDE[ssNoVersion](../../../../csharp/programming-guide/concepts/linq/includes/ssnoversion_md.md)] database schemas, and [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)] allows you to query an [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)].</span></span>  
  
## <a name="linq-to-dataset"></a><span data-ttu-id="726ba-107">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="726ba-107">LINQ to DataSet</span></span>  
 <span data-ttu-id="726ba-108"><xref:System.Data.DataSet>中最广泛使用的组件之一是[!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)]，并且是模型的关键元素断开连接式编程，[!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)]基于。</xref:System.Data.DataSet></span><span class="sxs-lookup"><span data-stu-id="726ba-108">The <xref:System.Data.DataSet> is one of the most widely used components in [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)], and is a key element of the disconnected programming model that [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] is built on.</span></span> <span data-ttu-id="726ba-109">尽管此具有突出的优点，但是，<xref:System.Data.DataSet>查询功能也存在限制。</xref:System.Data.DataSet></span><span class="sxs-lookup"><span data-stu-id="726ba-109">Despite this prominence, however, the <xref:System.Data.DataSet> has limited query capabilities.</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)]<span data-ttu-id="726ba-110">使您能够构建丰富的查询功能到<xref:System.Data.DataSet>使用相同的查询功能，可用于许多其他数据源。</xref:System.Data.DataSet></span><span class="sxs-lookup"><span data-stu-id="726ba-110"> enables you to build richer query capabilities into <xref:System.Data.DataSet> by using the same query functionality that is available for many other data sources.</span></span>  
  
 <span data-ttu-id="726ba-111">有关详细信息，请参阅[LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)。</span><span class="sxs-lookup"><span data-stu-id="726ba-111">For more information, see [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17).</span></span>  
  
## <a name="linq-to-sql"></a><span data-ttu-id="726ba-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="726ba-112">LINQ to SQL</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]<span data-ttu-id="726ba-113"> 提供用于将关系数据作为对象进行管理的运行时基础结构。</span><span class="sxs-lookup"><span data-stu-id="726ba-113"> provides a run-time infrastructure for managing relational data as objects.</span></span> <span data-ttu-id="726ba-114">在 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] 中，关系数据库的数据模型映射到用开发人员所用的编程语言表示的对象模型。</span><span class="sxs-lookup"><span data-stu-id="726ba-114">In [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="726ba-115">当您执行该应用程序，[!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]将对象模型中的语言集成查询转换为 SQL 并将其发送到数据库进行执行。</span><span class="sxs-lookup"><span data-stu-id="726ba-115">When you execute the application, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] translates language-integrated queries in the object model into SQL and sends them to the database for execution.</span></span> <span data-ttu-id="726ba-116">当数据库返回结果，[!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]会将它们转换回您可以处理的对象。</span><span class="sxs-lookup"><span data-stu-id="726ba-116">When the database returns the results, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] translates them back into objects that you can manipulate.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]<span data-ttu-id="726ba-117">在对象模型中包括对存储的过程和在数据库中，用户定义函数和继承的支持。</span><span class="sxs-lookup"><span data-stu-id="726ba-117"> includes support for stored procedures and user-defined functions in the database, and for inheritance in the object model.</span></span>  
  
 <span data-ttu-id="726ba-118">有关详细信息，请参阅[LINQ to SQL](https://msdn.microsoft.com/library/bb386976)。</span><span class="sxs-lookup"><span data-stu-id="726ba-118">For more information, see [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).</span></span>  
  
## <a name="linq-to-entities"></a><span data-ttu-id="726ba-119">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="726ba-119">LINQ to Entities</span></span>  
 <span data-ttu-id="726ba-120">通过 [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)]，在 .NET 环境中将关系数据作为对象公开。</span><span class="sxs-lookup"><span data-stu-id="726ba-120">Through the [!INCLUDE[adonet_edm](../../../../csharp/programming-guide/concepts/linq/includes/adonet_edm_md.md)], relational data is exposed as objects in the .NET environment.</span></span> <span data-ttu-id="726ba-121">这使得对象层成为实现 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 支持的理想目标，开发人员可以采用生成业务逻辑所用的语言来构建数据库查询。</span><span class="sxs-lookup"><span data-stu-id="726ba-121">This makes the object layer an ideal target for [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] support, allowing developers to formulate queries against the database from the language used to build the business logic.</span></span> <span data-ttu-id="726ba-122">此功能称为 [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="726ba-122">This capability is known as [!INCLUDE[linq_entities](../../../../csharp/programming-guide/concepts/linq/includes/linq_entities_md.md)].</span></span> <span data-ttu-id="726ba-123">请参阅[LINQ to Entities](http://msdn.microsoft.com/library/641f9b68-9046-47a1-abb0-1c8eaeda0e2d)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="726ba-123">See [LINQ to Entities](http://msdn.microsoft.com/library/641f9b68-9046-47a1-abb0-1c8eaeda0e2d) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726ba-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="726ba-124">See Also</span></span>  
 <span data-ttu-id="726ba-125">[LINQ 和 ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec) </span><span class="sxs-lookup"><span data-stu-id="726ba-125">[LINQ and ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec) </span></span>  
<span data-ttu-id="726ba-126"> [语言集成查询 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="726ba-126"> [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)</span></span>
