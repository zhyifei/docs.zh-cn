---
title: LINQ 注意事项（WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ
- querying the data service [WCF Data Services]
- WCF Data Services, querying
ms.assetid: cc4ec9e9-348f-42a6-a78e-1cd40e370656
ms.openlocfilehash: 92b3444f81f00ee709c22836126073d342c6fa05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526812"
---
# <a name="linq-considerations-wcf-data-services"></a><span data-ttu-id="b7a62-102">LINQ 注意事项（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="b7a62-102">LINQ Considerations (WCF Data Services)</span></span>
<span data-ttu-id="b7a62-103">本主题提供有关使用 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 客户端时 LINQ 查询的编写和执行方式的信息以及使用 LINQ 查询实现[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 的数据服务的限制。</span><span class="sxs-lookup"><span data-stu-id="b7a62-103">This topic provides information about the way in which LINQ queries are composed and executed when you are using the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client and limitations of using LINQ to query a data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)].</span></span> <span data-ttu-id="b7a62-104">有关编写和执行针对查询的详细信息[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-基于数据服务，请参阅[查询数据服务](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="b7a62-104">For more information about composing and executing queries against an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based data service, see [Querying the Data Service](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).</span></span>  
  
## <a name="composing-linq-queries"></a><span data-ttu-id="b7a62-105">编写 LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="b7a62-105">Composing LINQ Queries</span></span>  
 <span data-ttu-id="b7a62-106">LINQ 允许针对实现 <xref:System.Collections.Generic.IEnumerable%601> 的对象集合编写查询。</span><span class="sxs-lookup"><span data-stu-id="b7a62-106">LINQ enables you to compose queries against a collection of objects that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="b7a62-107">这两个**添加服务引用**使用 Visual Studio 中的对话框和 DataSvcUtil.exe 工具生成的表示形式[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]服务作为继承的实体容器类<xref:System.Data.Services.Client.DataServiceContext>，以及表示源中返回的实体的对象。</span><span class="sxs-lookup"><span data-stu-id="b7a62-107">Both the **Add Service Reference** dialog box in Visual Studio and the DataSvcUtil.exe tool are used to generate a representation of an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>, as well as objects that represent the entities returned in feeds.</span></span> <span data-ttu-id="b7a62-108">这些工具还可为由服务作为源公开的集合的实体容器类生成属性。</span><span class="sxs-lookup"><span data-stu-id="b7a62-108">These tools also generate properties on the entity container class for the collections that are exposed as feeds by the service.</span></span> <span data-ttu-id="b7a62-109">封装了数据服务的类的每个属性都会返回一个 <xref:System.Data.Services.Client.DataServiceQuery%601>。</span><span class="sxs-lookup"><span data-stu-id="b7a62-109">Each of these properties of the class that encapsulates the data service return a <xref:System.Data.Services.Client.DataServiceQuery%601>.</span></span> <span data-ttu-id="b7a62-110">因为 <xref:System.Data.Services.Client.DataServiceQuery%601> 类实现 LINQ 定义的 <xref:System.Linq.IQueryable%601> 接口，所以可以针对数据服务公开的源编写 LINQ 查询，客户端库会将其转换为一个查询请求 URI，在执行时将此 URI 发送给数据服务。</span><span class="sxs-lookup"><span data-stu-id="b7a62-110">Because the <xref:System.Data.Services.Client.DataServiceQuery%601> class implements the <xref:System.Linq.IQueryable%601> interface defined by LINQ, you can compose a LINQ query against feeds exposed by the data service, which are translated by the client library into a query request URI that is sent to the data service on execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b7a62-111">可以采用 LINQ 语法表示的查询集大于 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 数据服务使用的 URI 语法所支持的查询集。</span><span class="sxs-lookup"><span data-stu-id="b7a62-111">The set of queries expressible in the LINQ syntax is broader than those enabled in the URI syntax that is used by [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] data services.</span></span> <span data-ttu-id="b7a62-112">如果无法将查询映射到目标数据服务中的 URI，则会引发 <xref:System.NotSupportedException>。</span><span class="sxs-lookup"><span data-stu-id="b7a62-112">A <xref:System.NotSupportedException> is raised when the query cannot be mapped to a URI in the target data service.</span></span> <span data-ttu-id="b7a62-113">有关详细信息，请参阅[不支持的 LINQ 方法](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md#unsupportedMethods)本主题中。</span><span class="sxs-lookup"><span data-stu-id="b7a62-113">For more information, see the [Unsupported LINQ Methods](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md#unsupportedMethods) in this topic.</span></span>  
  
 <span data-ttu-id="b7a62-114">下面的示例是一个 LINQ 查询，它返回运费成本超过 30 美元的 `Orders` 并按装运日期对结果进行排序，最近的装运日期排在最前面：</span><span class="sxs-lookup"><span data-stu-id="b7a62-114">The following example is a LINQ query that returns `Orders` that have a freight cost of more than $30 and sorts the results by the shipping date, starting with the latest ship date:</span></span>  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinqspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinqspecific)]    
  
 <span data-ttu-id="b7a62-115">此 LINQ 查询转换成下面的查询执行针对基于 Northwind 的 URI[快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)数据服务：</span><span class="sxs-lookup"><span data-stu-id="b7a62-115">This LINQ query is translated into the following query URI that is executed against the Northwind-based [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) data service:</span></span>  
  
```  
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
 <span data-ttu-id="b7a62-116">有关 LINQ 的更多常规信息，请参阅[LINQ （语言集成查询）](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)。</span><span class="sxs-lookup"><span data-stu-id="b7a62-116">For more general information about LINQ, see [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span></span>  
  
 <span data-ttu-id="b7a62-117">LINQ 允许使用语言特定声明查询语法（如上例所示）和一组称为标准查询运算符的查询方法编写查询。</span><span class="sxs-lookup"><span data-stu-id="b7a62-117">LINQ enables you to compose queries by using both the language-specific declarative query syntax, shown in the previous example, as well as a set of query methods known as standard query operators.</span></span> <span data-ttu-id="b7a62-118">通过仅使用基于方法的语法可以编写与上例等效的查询，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="b7a62-118">An equivalent query to the previous example can be composed by using only the method-based syntax, as shown the following example:</span></span>  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinqexpressionspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinqexpressionspecific)]    
  
 <span data-ttu-id="b7a62-119">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]客户端能够将用这两种方式编写的查询转换为查询 URI，并且可以通过向查询表达式追加查询方法来扩展 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="b7a62-119">The [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client is able to translate both kinds of composed queries into a query URI, and you can extend a LINQ query by appending query methods to a query expression.</span></span> <span data-ttu-id="b7a62-120">通过向查询表达式或 <xref:System.Data.Services.Client.DataServiceQuery%601> 追加方法语法来编写 LINQ 查询时，运算将按照方法的调用顺序添加到查询 URI 中。</span><span class="sxs-lookup"><span data-stu-id="b7a62-120">When you compose LINQ queries by appending method syntax to a query expression or a <xref:System.Data.Services.Client.DataServiceQuery%601>, the operations are added to the query URI in the order in which methods are called.</span></span> <span data-ttu-id="b7a62-121">这等效于调用 <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> 方法将每个查询选项添加到查询 URI 中。</span><span class="sxs-lookup"><span data-stu-id="b7a62-121">This is equivalent to calling the <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> method to add each query option to the query URI.</span></span>  
  
## <a name="executing-linq-queries"></a><span data-ttu-id="b7a62-122">执行 LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="b7a62-122">Executing LINQ Queries</span></span>  
 <span data-ttu-id="b7a62-123">某些 LINQ 查询方法（如 <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 或 <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>）在追加到查询中时会导致执行查询。</span><span class="sxs-lookup"><span data-stu-id="b7a62-123">Certain LINQ query methods, such as <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> or <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>, when appended to the query, cause the query to be executed.</span></span> <span data-ttu-id="b7a62-124">在隐式枚举结果时也会执行查询，例如在 `foreach` 循环过程中或将查询分配给一个 `List` 集合时。</span><span class="sxs-lookup"><span data-stu-id="b7a62-124">A query is also executed when results are enumerated implicitly, such as during a `foreach` loop or when the query is assigned to a `List` collection.</span></span> <span data-ttu-id="b7a62-125">有关详细信息，请参阅[查询数据服务](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="b7a62-125">For more information, see [Querying the Data Service](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="b7a62-126">客户端分两个部分来执行 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="b7a62-126">The client executes a LINQ query in two parts.</span></span> <span data-ttu-id="b7a62-127">只要有可能，将首先在客户端上计算查询中的 LINQ 表达式，然后生成基于 URI 的查询并将其发送至数据服务，以针对服务中的数据进行计算。</span><span class="sxs-lookup"><span data-stu-id="b7a62-127">Whenever possible, LINQ expressions in a query are first evaluated on the client, and then a URI-based query is generated and sent to the data service for evaluation against data in the service.</span></span> <span data-ttu-id="b7a62-128">有关详细信息，请参阅明[客户端与服务器执行](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md#executingQueries)中[查询数据服务](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="b7a62-128">For more information, see the section [Client versus Server Execution](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md#executingQueries) in [Querying the Data Service](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="b7a62-129">如果 LINQ 查询无法在 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 兼容的查询 URI 中进行转换，则尝试执行时将引发异常。</span><span class="sxs-lookup"><span data-stu-id="b7a62-129">When a LINQ query cannot be translated in an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-compliant query URI, an exception is raised when execution is attempted.</span></span> <span data-ttu-id="b7a62-130">有关详细信息，请参阅[查询数据服务](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="b7a62-130">For more information, see [Querying the Data Service](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).</span></span>  
  
## <a name="linq-query-examples"></a><span data-ttu-id="b7a62-131">LINQ 查询示例</span><span class="sxs-lookup"><span data-stu-id="b7a62-131">LINQ Query Examples</span></span>  
 <span data-ttu-id="b7a62-132">以下各小节中的示例揭示了可针对 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 服务执行的 LINQ 查询的种类。</span><span class="sxs-lookup"><span data-stu-id="b7a62-132">The examples in the following sections demonstrate the kinds of LINQ queries that can be executed against an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] service.</span></span>  
  
<a name="filtering"></a>   
### <a name="filtering"></a><span data-ttu-id="b7a62-133">筛选</span><span class="sxs-lookup"><span data-stu-id="b7a62-133">Filtering</span></span>  
 <span data-ttu-id="b7a62-134">本小节中的 LINQ 查询示例将筛选由服务返回的源中的数据。</span><span class="sxs-lookup"><span data-stu-id="b7a62-134">The LINQ query examples in this section filter data in the feed returned by the service.</span></span>  
  
 <span data-ttu-id="b7a62-135">下面这些示例是等效的查询，它们将筛选返回的 `Orders` 实体并仅返回运费成本高于 30 美元的订单：</span><span class="sxs-lookup"><span data-stu-id="b7a62-135">The following examples are equivalent queries that filter the returned `Orders` entities so that only orders with a freight cost greater than $30 are returned:</span></span>  
  
-   <span data-ttu-id="b7a62-136">使用 LINQ 查询语法：</span><span class="sxs-lookup"><span data-stu-id="b7a62-136">Using LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqwhereclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqwhereclausespecific)]     
  
-   <span data-ttu-id="b7a62-137">使用 LINQ 查询方法：</span><span class="sxs-lookup"><span data-stu-id="b7a62-137">Using LINQ query methods:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqwheremethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqwheremethodspecific)]       
  
-   <span data-ttu-id="b7a62-138">URI 查询字符串 `$filter` 选项：</span><span class="sxs-lookup"><span data-stu-id="b7a62-138">The URI query string `$filter` option:</span></span>  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#explicitquerywheremethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#explicitquerywheremethodspecific)]       
  
 <span data-ttu-id="b7a62-139">前面的所有示例都将转换为查询 URI：`http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`。</span><span class="sxs-lookup"><span data-stu-id="b7a62-139">All of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`.</span></span>  
  
<a name="sorting"></a>   
### <a name="sorting"></a><span data-ttu-id="b7a62-140">排序</span><span class="sxs-lookup"><span data-stu-id="b7a62-140">Sorting</span></span>  
 <span data-ttu-id="b7a62-141">下面的示例显示了按公司名称和邮政编码降序排序返回的数据的等效查询：</span><span class="sxs-lookup"><span data-stu-id="b7a62-141">The following examples show equivalent queries that sort returned data both by the company name and by postal code, descending:</span></span>  
  
-   <span data-ttu-id="b7a62-142">使用 LINQ 查询语法：</span><span class="sxs-lookup"><span data-stu-id="b7a62-142">Using LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqorderbyclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqorderbyclausespecific)]        
  
-   <span data-ttu-id="b7a62-143">使用 LINQ 查询方法：</span><span class="sxs-lookup"><span data-stu-id="b7a62-143">Using LINQ query methods:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqorderbymethodspecific)]        
  
-   <span data-ttu-id="b7a62-144">URI 查询字符串 `$orderby` 选项：</span><span class="sxs-lookup"><span data-stu-id="b7a62-144">URI query string `$orderby` option):</span></span>  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#explicitqueryorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#explicitqueryorderbymethodspecific)]         
  
 <span data-ttu-id="b7a62-145">前面的所有示例都将转换为查询 URI：`http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`。</span><span class="sxs-lookup"><span data-stu-id="b7a62-145">All of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`.</span></span>  
  
<a name="projection"></a>   
### <a name="projection"></a><span data-ttu-id="b7a62-146">投影</span><span class="sxs-lookup"><span data-stu-id="b7a62-146">Projection</span></span>  
 <span data-ttu-id="b7a62-147">下面的示例显示了将返回的数据投影到较窄的 `CustomerAddress` 类型的等效查询：</span><span class="sxs-lookup"><span data-stu-id="b7a62-147">The following examples show equivalent queries that project returned data into the narrower `CustomerAddress` type:</span></span>  
  
-   <span data-ttu-id="b7a62-148">使用 LINQ 查询语法：</span><span class="sxs-lookup"><span data-stu-id="b7a62-148">Using LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqselectclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqselectclausespecific)]         
  
-   <span data-ttu-id="b7a62-149">使用 LINQ 查询方法：</span><span class="sxs-lookup"><span data-stu-id="b7a62-149">Using LINQ query methods:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqselectmethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqselectmethodspecific)]         
 
  
> [!NOTE]
>  <span data-ttu-id="b7a62-150">不能使用 `$select` 方法将 <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> 查询选项添加到查询 URI 中。</span><span class="sxs-lookup"><span data-stu-id="b7a62-150">The `$select` query option cannot be added to a query URI by using the <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> method.</span></span> <span data-ttu-id="b7a62-151">我们建议使用 LINQ <xref:System.Linq.Enumerable.Select%2A> 方法，让客户端在请求 URI 中生成 `$select` 查询选项。</span><span class="sxs-lookup"><span data-stu-id="b7a62-151">We recommend that you use the LINQ <xref:System.Linq.Enumerable.Select%2A> method to have the client generate the `$select` query option in the request URI.</span></span>  
  
 <span data-ttu-id="b7a62-152">前面的两个示例都将转换为查询 URI：`"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`。</span><span class="sxs-lookup"><span data-stu-id="b7a62-152">Both of the previous examples are translated to the query URI: `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`.</span></span>  
  
<a name="paging"></a>   
### <a name="client-paging"></a><span data-ttu-id="b7a62-153">客户端分页</span><span class="sxs-lookup"><span data-stu-id="b7a62-153">Client Paging</span></span>  
 <span data-ttu-id="b7a62-154">下面所示的等效查询示例将请求返回一页包含 25 个订单的排序订单实体，并跳过前 50 个订单：</span><span class="sxs-lookup"><span data-stu-id="b7a62-154">The following examples show equivalent queries that request a page of sorted order entities that includes 25 orders, skipping the first 50 orders:</span></span>  
  
-   <span data-ttu-id="b7a62-155">为 LINQ 查询应用查询方法：</span><span class="sxs-lookup"><span data-stu-id="b7a62-155">Applying query methods to a LINQ query:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqskiptakemethodspecific)]     
  
-   <span data-ttu-id="b7a62-156">URI 查询字符串 `$skip` 和 `$top` 选项：</span><span class="sxs-lookup"><span data-stu-id="b7a62-156">URI query string `$skip` and `$top` options):</span></span>  
  
[!code-csharp[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#explicitqueryskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#explicitqueryskiptakemethodspecific)]     
  
 <span data-ttu-id="b7a62-157">前面的两个示例都将转换为查询 URI：`http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`。</span><span class="sxs-lookup"><span data-stu-id="b7a62-157">Both of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`.</span></span>  
  
<a name="expand"></a>   
### <a name="expand"></a><span data-ttu-id="b7a62-158">展开</span><span class="sxs-lookup"><span data-stu-id="b7a62-158">Expand</span></span>  
 <span data-ttu-id="b7a62-159">查询 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 数据服务时，可以请求在返回的源中包含与查询的目标实体相关的实体。</span><span class="sxs-lookup"><span data-stu-id="b7a62-159">When you query an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] data service, you can request that entities related to the entity targeted by the query be included the returned feed.</span></span> <span data-ttu-id="b7a62-160">针对 LINQ 查询的目标实体集调用 <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> 的 <xref:System.Data.Services.Client.DataServiceQuery%601> 方法，相关实体集名称作为 `path` 参数提供。</span><span class="sxs-lookup"><span data-stu-id="b7a62-160">The <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> method is called on the <xref:System.Data.Services.Client.DataServiceQuery%601> for the entity set targeted by the LINQ query, with the related entity set name supplied as the `path` parameter.</span></span> <span data-ttu-id="b7a62-161">有关详细信息，请参阅[加载延迟的内容](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="b7a62-161">For more information, see [Loading Deferred Content](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="b7a62-162">下面的示例显示了在查询中使用 <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> 方法的等效方式：</span><span class="sxs-lookup"><span data-stu-id="b7a62-162">The following examples show equivalent ways to use the <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> method in a query:</span></span>  
  
-   <span data-ttu-id="b7a62-163">在 LINQ 查询语法中：</span><span class="sxs-lookup"><span data-stu-id="b7a62-163">In LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqqueryexpandspecific)]      
[!code-vb[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqqueryexpandspecific)]  
  
-   <span data-ttu-id="b7a62-164">使用 LINQ 查询方法：</span><span class="sxs-lookup"><span data-stu-id="b7a62-164">With LINQ query methods:</span></span>  

[!code-csharp[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#linqqueryexpandmethodspecific)]       
[!code-vb[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#linqqueryexpandmethodspecific)]       
  
  
 <span data-ttu-id="b7a62-165">前面的两个示例都将转换为查询 URI：`http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`。</span><span class="sxs-lookup"><span data-stu-id="b7a62-165">Both of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`.</span></span>  
  
<a name="unsupportedMethods"></a>   
## <a name="unsupported-linq-methods"></a><span data-ttu-id="b7a62-166">不支持的 LINQ 方法</span><span class="sxs-lookup"><span data-stu-id="b7a62-166">Unsupported LINQ Methods</span></span>  
 <span data-ttu-id="b7a62-167">下表所列的 LINQ 方法的类不受支持，不能包含在针对 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 服务执行的查询中：</span><span class="sxs-lookup"><span data-stu-id="b7a62-167">The following table contains the classes of LINQ methods are not supported and cannot be included in a query executed against an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] service:</span></span>  
  
|<span data-ttu-id="b7a62-168">运算类型</span><span class="sxs-lookup"><span data-stu-id="b7a62-168">Operation Type</span></span>|<span data-ttu-id="b7a62-169">不支持的方法</span><span class="sxs-lookup"><span data-stu-id="b7a62-169">Unsupported Method</span></span>|  
|--------------------|------------------------|  
|<span data-ttu-id="b7a62-170">集合运算符</span><span class="sxs-lookup"><span data-stu-id="b7a62-170">Set operators</span></span>|<span data-ttu-id="b7a62-171">所有集合运算符都不能用于 <xref:System.Data.Services.Client.DataServiceQuery%601>，其中包括：</span><span class="sxs-lookup"><span data-stu-id="b7a62-171">All set operators are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>, which included the following:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.All%2A><br />-   <xref:System.Linq.Enumerable.Any%2A><br />-   <xref:System.Linq.Enumerable.Concat%2A><br />-   <xref:System.Linq.Enumerable.DefaultIfEmpty%2A><br />-   <xref:System.Linq.Enumerable.Distinct%2A><br />-   <xref:System.Linq.Enumerable.Except%2A><br />-   <xref:System.Linq.Enumerable.Intersect%2A><br />-   <xref:System.Linq.Enumerable.Union%2A><br />-   <xref:System.Linq.Enumerable.Zip%2A>|  
|<span data-ttu-id="b7a62-172">排序运算符</span><span class="sxs-lookup"><span data-stu-id="b7a62-172">Ordering operators</span></span>|<span data-ttu-id="b7a62-173">要求 <xref:System.Collections.Generic.IComparer%601> 的以下排序运算符不能用于 <xref:System.Data.Services.Client.DataServiceQuery%601>：</span><span class="sxs-lookup"><span data-stu-id="b7a62-173">The following ordering operators that require <xref:System.Collections.Generic.IComparer%601> are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29>|  
|<span data-ttu-id="b7a62-174">投影和筛选运算符</span><span class="sxs-lookup"><span data-stu-id="b7a62-174">Projection and filtering operators</span></span>|<span data-ttu-id="b7a62-175">以下接受位置参数的投影和筛选运算符不能用于 <xref:System.Data.Services.Client.DataServiceQuery%601>：</span><span class="sxs-lookup"><span data-stu-id="b7a62-175">The following projection and filtering operators that accept a positional argument are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2C%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29>|  
|<span data-ttu-id="b7a62-176">分组运算符</span><span class="sxs-lookup"><span data-stu-id="b7a62-176">Grouping operators</span></span>|<span data-ttu-id="b7a62-177">所有分组运算符都不能用于 <xref:System.Data.Services.Client.DataServiceQuery%601>，其中包括：</span><span class="sxs-lookup"><span data-stu-id="b7a62-177">All grouping operators are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>, including the following:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.GroupBy%2A><br />-   <xref:System.Linq.Enumerable.GroupJoin%2A><br /><br /> <span data-ttu-id="b7a62-178">分组运算符必须在客户端上执行。</span><span class="sxs-lookup"><span data-stu-id="b7a62-178">Grouping operations must be performed on the client.</span></span>|  
|<span data-ttu-id="b7a62-179">聚合运算符</span><span class="sxs-lookup"><span data-stu-id="b7a62-179">Aggregate operators</span></span>|<span data-ttu-id="b7a62-180">所有聚合运算符都不能用于 <xref:System.Data.Services.Client.DataServiceQuery%601>，其中包括：</span><span class="sxs-lookup"><span data-stu-id="b7a62-180">All aggregate operations are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>, including the following:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.Aggregate%2A><br />-   <xref:System.Linq.Enumerable.Average%2A><br />-   <xref:System.Linq.Enumerable.Count%2A><br />-   <xref:System.Linq.Enumerable.LongCount%2A><br />-   <xref:System.Linq.Enumerable.Max%2A><br />-   <xref:System.Linq.Enumerable.Min%2A><br />-   <xref:System.Linq.Enumerable.Sum%2A><br /><br /> <span data-ttu-id="b7a62-181">聚合运算符必须在客户端上执行或由服务操作封装。</span><span class="sxs-lookup"><span data-stu-id="b7a62-181">Aggregate operations must either be performed on the client or be encapsulated by a service operation.</span></span>|  
|<span data-ttu-id="b7a62-182">分页运算符</span><span class="sxs-lookup"><span data-stu-id="b7a62-182">Paging operators</span></span>|<span data-ttu-id="b7a62-183">以下分页运算符不能用于 <xref:System.Data.Services.Client.DataServiceQuery%601>：</span><span class="sxs-lookup"><span data-stu-id="b7a62-183">The following paging operators are not supported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.ElementAt%2A><br />-   <xref:System.Linq.Enumerable.Last%2A><br />-   <xref:System.Linq.Enumerable.LastOrDefault%2A><br />-   <xref:System.Linq.Enumerable.SkipWhile%2A><br /><span data-ttu-id="b7a62-184">-   <xref:System.Linq.Enumerable.TakeWhile%2A> **注意：** 对空序列执行的分页运算符将返回 null。</span><span class="sxs-lookup"><span data-stu-id="b7a62-184">-   <xref:System.Linq.Enumerable.TakeWhile%2A> **Note:**  Paging operators that are executed on an empty sequence return null.</span></span>|  
|<span data-ttu-id="b7a62-185">其他运算符</span><span class="sxs-lookup"><span data-stu-id="b7a62-185">Other operators</span></span>|<span data-ttu-id="b7a62-186">以下其他运算符不能用于 <xref:System.Data.Services.Client.DataServiceQuery%601>：</span><span class="sxs-lookup"><span data-stu-id="b7a62-186">The following other operators are not supported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> <span data-ttu-id="b7a62-187">1.  <xref:System.Linq.Enumerable.Empty%2A></span><span class="sxs-lookup"><span data-stu-id="b7a62-187">1.  <xref:System.Linq.Enumerable.Empty%2A></span></span><br /><span data-ttu-id="b7a62-188">2.  <xref:System.Linq.Enumerable.Range%2A></span><span class="sxs-lookup"><span data-stu-id="b7a62-188">2.  <xref:System.Linq.Enumerable.Range%2A></span></span><br /><span data-ttu-id="b7a62-189">3.  <xref:System.Linq.Enumerable.Repeat%2A></span><span class="sxs-lookup"><span data-stu-id="b7a62-189">3.  <xref:System.Linq.Enumerable.Repeat%2A></span></span><br /><span data-ttu-id="b7a62-190">4.  <xref:System.Linq.Enumerable.ToDictionary%2A></span><span class="sxs-lookup"><span data-stu-id="b7a62-190">4.  <xref:System.Linq.Enumerable.ToDictionary%2A></span></span><br /><span data-ttu-id="b7a62-191">5.  <xref:System.Linq.Enumerable.ToLookup%2A></span><span class="sxs-lookup"><span data-stu-id="b7a62-191">5.  <xref:System.Linq.Enumerable.ToLookup%2A></span></span>|  
  
<a name="supportedExpressions"></a>   
## <a name="supported-expression-functions"></a><span data-ttu-id="b7a62-192">支持的表达式函数</span><span class="sxs-lookup"><span data-stu-id="b7a62-192">Supported Expression Functions</span></span>  
 <span data-ttu-id="b7a62-193">支持以下公共语言运行时 (CLR) 方法和属性，因为它们可以在查询表达式中进行转换以包含在 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 服务的请求 URI 中：</span><span class="sxs-lookup"><span data-stu-id="b7a62-193">The following common-language runtime (CLR) methods and properties are supported because they can be translated in a query expression for inclusion in the request URI to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] service:</span></span>  
  
|<span data-ttu-id="b7a62-194"><xref:System.String> 成员</span><span class="sxs-lookup"><span data-stu-id="b7a62-194"><xref:System.String> Member</span></span>|<span data-ttu-id="b7a62-195">支持的 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 函数</span><span class="sxs-lookup"><span data-stu-id="b7a62-195">Supported [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Function</span></span>|  
|-----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.String.Concat%28System.String%2CSystem.String%29>|`string concat(string p0, string p1)`|  
|<xref:System.String.Contains%28System.String%29>|`bool substringof(string p0, string p1)`|  
|<xref:System.String.EndsWith%28System.String%29>|`bool endswith(string p0, string p1)`|  
|<xref:System.String.IndexOf%28System.String%2CSystem.Int32%29>|`int indexof(string p0, string p1)`|  
|<xref:System.String.Length>|`int length(string p0)`|  
|<xref:System.String.Replace%28System.String%2CSystem.String%29>|`string replace(string p0, string find, string replace)`|  
|<xref:System.String.Substring%28System.Int32%29>|`string substring(string p0, int pos)`|  
|<xref:System.String.Substring%28System.Int32%2CSystem.Int32%29>|`string substring(string p0, int pos, int length)`|  
|<xref:System.String.ToLower>|`string tolower(string p0)`|  
|<xref:System.String.ToUpper>|`string toupper(string p0)`|  
|<xref:System.String.Trim>|`string trim(string p0)`|  
  
|<span data-ttu-id="b7a62-196"><xref:System.DateTime> 成员<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b7a62-196"><xref:System.DateTime> Member<sup>1</sup></span></span>|<span data-ttu-id="b7a62-197">支持的 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 函数</span><span class="sxs-lookup"><span data-stu-id="b7a62-197">Supported [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Function</span></span>|  
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Day>|`int day(DateTime p0)`|  
|<xref:System.DateTime.Hour>|`int hour(DateTime p0)`|  
|<xref:System.DateTime.Minute>|`int minute(DateTime p0)`|  
|<xref:System.DateTime.Month>|`int month(DateTime p0)`|  
|<xref:System.DateTime.Second>|`int second(DateTime p0)`|  
|<xref:System.DateTime.Year>|`int year(DateTime p0)`|  
  
 <span data-ttu-id="b7a62-198"><sup>1</sup>等效的日期和时间属性<xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType>，并将<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>还支持在 Visual Basic 中的方法。</span><span class="sxs-lookup"><span data-stu-id="b7a62-198"><sup>1</sup>The equivalent date and time properties of <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType>, as well as the <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> method in Visual Basic are also supported.</span></span>  
  
|<span data-ttu-id="b7a62-199"><xref:System.Math> 成员</span><span class="sxs-lookup"><span data-stu-id="b7a62-199"><xref:System.Math> Member</span></span>|<span data-ttu-id="b7a62-200">支持的 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 函数</span><span class="sxs-lookup"><span data-stu-id="b7a62-200">Supported [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Function</span></span>|  
|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Math.Ceiling%28System.Decimal%29>|`decimal ceiling(decimal p0)`|  
|<xref:System.Math.Ceiling%28System.Double%29>|`double ceiling(double p0)`|  
|<xref:System.Math.Floor%28System.Decimal%29>|`decimal floor(decimal p0)`|  
|<xref:System.Math.Floor%28System.Double%29>|`double floor(double p0)`|  
|<xref:System.Math.Round%28System.Decimal%29>|`decimal round(decimal p0)`|  
|<xref:System.Math.Round%28System.Double%29>|`double round(double p0)`|  
  
|<span data-ttu-id="b7a62-201"><xref:System.Linq.Expressions.Expression> 成员</span><span class="sxs-lookup"><span data-stu-id="b7a62-201"><xref:System.Linq.Expressions.Expression> Member</span></span>|<span data-ttu-id="b7a62-202">支持的 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 函数</span><span class="sxs-lookup"><span data-stu-id="b7a62-202">Supported [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Function</span></span>|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Linq.Expressions.Expression.TypeIs%28System.Linq.Expressions.Expression%2CSystem.Type%29>|`bool isof(type p0)`|  
  
 <span data-ttu-id="b7a62-203">客户端或许还可以在客户端上计算其他 CLR 函数。</span><span class="sxs-lookup"><span data-stu-id="b7a62-203">The client may also be able to evaluate additional CLR functions on the client.</span></span> <span data-ttu-id="b7a62-204">对于无法在客户端上计算以及无法转换为有效请求 URI 以便在服务器上计算的任何表达式，将引发 <xref:System.NotSupportedException>。</span><span class="sxs-lookup"><span data-stu-id="b7a62-204">A <xref:System.NotSupportedException> is raised for any expression that cannot be evaluated on the client and cannot be translated into a valid request URI for evaluation on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a62-205">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7a62-205">See Also</span></span>  
 [<span data-ttu-id="b7a62-206">查询数据服务</span><span class="sxs-lookup"><span data-stu-id="b7a62-206">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 [<span data-ttu-id="b7a62-207">查询投影</span><span class="sxs-lookup"><span data-stu-id="b7a62-207">Query Projections</span></span>](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md)  
 [<span data-ttu-id="b7a62-208">对象具体化</span><span class="sxs-lookup"><span data-stu-id="b7a62-208">Object Materialization</span></span>](../../../../docs/framework/data/wcf/object-materialization-wcf-data-services.md)  
 [<span data-ttu-id="b7a62-209">OData: URI 约定</span><span class="sxs-lookup"><span data-stu-id="b7a62-209">OData: URI Conventions</span></span>](https://go.microsoft.com/fwlink/?LinkID=185564)
