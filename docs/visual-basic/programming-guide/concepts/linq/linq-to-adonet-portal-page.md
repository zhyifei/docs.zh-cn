---
title: LINQ to ADO.NET（门户网站页）
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: d5d7ba8230ae9737d4938c1c8c55f7cd4330b117
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636492"
---
# <a name="linq-to-adonet-portal-page"></a><span data-ttu-id="4839b-102">LINQ to ADO.NET（门户网站页）</span><span class="sxs-lookup"><span data-stu-id="4839b-102">LINQ to ADO.NET (Portal Page)</span></span>
<span data-ttu-id="4839b-103">LINQ to ADO.NET 使你能够使用语言集成查询（LINQ）编程模型在 ADO.NET 中查询任何可枚举对象。</span><span class="sxs-lookup"><span data-stu-id="4839b-103">LINQ to ADO.NET enables you to query over any enumerable object in ADO.NET by using the Language-Integrated Query (LINQ) programming model.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4839b-104">LINQ to ADO.NET 文档位于 .NET Framework SDK 的 ADO.NET 部分： [LINQ and ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)。</span><span class="sxs-lookup"><span data-stu-id="4839b-104">The LINQ to ADO.NET documentation is located in the ADO.NET section of the .NET Framework SDK: [LINQ and ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).</span></span>
  
 <span data-ttu-id="4839b-105">有三个独立的 ADO.NET 语言集成查询（LINQ）技术： LINQ to DataSet、[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]和 LINQ to Entities。</span><span class="sxs-lookup"><span data-stu-id="4839b-105">There are three separate ADO.NET Language-Integrated Query (LINQ) technologies: LINQ to DataSet, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], and LINQ to Entities.</span></span> <span data-ttu-id="4839b-106">LINQ to DataSet 提供针对 <xref:System.Data.DataSet> 的形式多样的优化查询，[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 可用于直接查询 SQL Server 数据库架构，而 LINQ to Entities 可实现实体数据模型的查询。</span><span class="sxs-lookup"><span data-stu-id="4839b-106">LINQ to DataSet provides richer, optimized querying over the <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] enables you to directly query SQL Server database schemas, and LINQ to Entities allows you to query an Entity Data Model.</span></span>  
  
## <a name="linq-to-dataset"></a><span data-ttu-id="4839b-107">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="4839b-107">LINQ to DataSet</span></span>  
 <span data-ttu-id="4839b-108"><xref:System.Data.DataSet> 是 ADO.NET 中使用最广泛的某个组件，也是断开编程模型（构建 ADO.NET 的基础）连接的重要元素。</span><span class="sxs-lookup"><span data-stu-id="4839b-108">The <xref:System.Data.DataSet> is one of the most widely used components in ADO.NET, and is a key element of the disconnected programming model that ADO.NET is built on.</span></span> <span data-ttu-id="4839b-109"><xref:System.Data.DataSet> 虽然具有突出的优点，但其查询功能也存在限制。</span><span class="sxs-lookup"><span data-stu-id="4839b-109">Despite this prominence, however, the <xref:System.Data.DataSet> has limited query capabilities.</span></span>  
  
 <span data-ttu-id="4839b-110">凭借 LINQ to DataSet，可通过使用为其他多个数据源提供的同一查询功能，在 <xref:System.Data.DataSet> 中加入更丰富的查询功能。</span><span class="sxs-lookup"><span data-stu-id="4839b-110">LINQ to DataSet enables you to build richer query capabilities into <xref:System.Data.DataSet> by using the same query functionality that is available for many other data sources.</span></span>  
  
 <span data-ttu-id="4839b-111">有关详细信息，请参阅 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="4839b-111">For more information, see [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).</span></span>  
  
## <a name="linq-to-sql"></a><span data-ttu-id="4839b-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4839b-112">LINQ to SQL</span></span>  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] <span data-ttu-id="4839b-113">提供用于将关系数据作为对象进行管理的运行时基础结构。</span><span class="sxs-lookup"><span data-stu-id="4839b-113">provides a run-time infrastructure for managing relational data as objects.</span></span> <span data-ttu-id="4839b-114">在 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 中，关系数据库的数据模型映射到用开发人员所用的编程语言表示的对象模型。</span><span class="sxs-lookup"><span data-stu-id="4839b-114">In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="4839b-115">执行应用程序时，[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 会将对象模型中的语言集成查询转换为 SQL，然后将其发送到数据库进行执行。</span><span class="sxs-lookup"><span data-stu-id="4839b-115">When you execute the application, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates language-integrated queries in the object model into SQL and sends them to the database for execution.</span></span> <span data-ttu-id="4839b-116">数据库返回结果时，[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 会将结果转换回可操作对象。</span><span class="sxs-lookup"><span data-stu-id="4839b-116">When the database returns the results, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates them back into objects that you can manipulate.</span></span>  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] <span data-ttu-id="4839b-117">包括对数据库中的已存储过程和用户定义的函数和对象模型中的继承的支持。</span><span class="sxs-lookup"><span data-stu-id="4839b-117">includes support for stored procedures and user-defined functions in the database, and for inheritance in the object model.</span></span>  
  
 <span data-ttu-id="4839b-118">有关详细信息，请参阅 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4839b-118">For more information, see [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).</span></span>  
  
## <a name="linq-to-entities"></a><span data-ttu-id="4839b-119">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4839b-119">LINQ to Entities</span></span>  
 <span data-ttu-id="4839b-120">通过实体数据模型，在 .NET 环境中将关系数据作为对象公开。</span><span class="sxs-lookup"><span data-stu-id="4839b-120">Through the Entity Data Model, relational data is exposed as objects in the .NET environment.</span></span> <span data-ttu-id="4839b-121">这使得对象层成为 LINQ 支持的理想目标，从而使开发人员能够根据构建业务逻辑所用的语言来构建数据库查询。</span><span class="sxs-lookup"><span data-stu-id="4839b-121">This makes the object layer an ideal target for LINQ support, allowing developers to formulate queries against the database from the language used to build the business logic.</span></span> <span data-ttu-id="4839b-122">此功能称为 LINQ to Entities。</span><span class="sxs-lookup"><span data-stu-id="4839b-122">This capability is known as LINQ to Entities.</span></span> <span data-ttu-id="4839b-123">有关详细信息，请参阅 [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)。</span><span class="sxs-lookup"><span data-stu-id="4839b-123">See [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4839b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4839b-124">See also</span></span>

- [<span data-ttu-id="4839b-125">LINQ 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4839b-125">LINQ and ADO.NET</span></span>](../../../../framework/data/adonet/linq-and-ado-net.md)
- [<span data-ttu-id="4839b-126">语言集成查询 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4839b-126">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
