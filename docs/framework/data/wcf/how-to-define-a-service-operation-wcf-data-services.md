---
title: 如何：定义服务操作 （WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: fffc0efaea200a7b0aa26b0f273b3c0d99338bfb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586548"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a><span data-ttu-id="d62e8-102">如何：定义服务操作 （WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="d62e8-102">How to: Define a Service Operation (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="d62e8-103">公开在服务器上作为服务操作定义的方法。</span><span class="sxs-lookup"><span data-stu-id="d62e8-103">expose methods that are defined on the server as service operations.</span></span> <span data-ttu-id="d62e8-104">服务操作允许数据服务以提供通过在服务器上定义的方法的 URI 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d62e8-104">Service operations allow a data service to provide access through a URI to a method that is defined on the server.</span></span> <span data-ttu-id="d62e8-105">若要定义服务操作，应用 [`WebGet]`或`[WebInvoke]`属性为该方法。</span><span class="sxs-lookup"><span data-stu-id="d62e8-105">To define a service operation, apply the [`WebGet]` or `[WebInvoke]` attribute to the method.</span></span> <span data-ttu-id="d62e8-106">若要支持查询运算符，服务操作必须返回<xref:System.Linq.IQueryable%601>实例。</span><span class="sxs-lookup"><span data-stu-id="d62e8-106">To support query operators, the service operation must return an <xref:System.Linq.IQueryable%601> instance.</span></span> <span data-ttu-id="d62e8-107">服务操作可以通过 <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> 的 <xref:System.Data.Services.DataService%601> 属性访问基础数据源。</span><span class="sxs-lookup"><span data-stu-id="d62e8-107">Service operations may access the underlying data source through the <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> property on the <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="d62e8-108">有关详细信息，请参阅[服务操作](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d62e8-108">For more information, see [Service Operations](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="d62e8-109">本主题中的示例定义一个名为 `GetOrdersByCity` 的服务操作，该操作返回 <xref:System.Linq.IQueryable%601> 和相关 `Orders` 对象的经筛选后的 `Order_Details` 实例。</span><span class="sxs-lookup"><span data-stu-id="d62e8-109">The example in this topic defines a service operation named `GetOrdersByCity` that returns a filtered <xref:System.Linq.IQueryable%601> instance of `Orders` and related `Order_Details` objects.</span></span> <span data-ttu-id="d62e8-110">该示例访问作为 Northwind 示例数据服务数据源的 <xref:System.Data.Objects.ObjectContext> 实例。</span><span class="sxs-lookup"><span data-stu-id="d62e8-110">The example accesses the <xref:System.Data.Objects.ObjectContext> instance that is the data source for the Northwind sample data service.</span></span> <span data-ttu-id="d62e8-111">此服务创建完成后[WCF Data Services 快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d62e8-111">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a><span data-ttu-id="d62e8-112">在 Northwind 数据服务中定义服务操作</span><span class="sxs-lookup"><span data-stu-id="d62e8-112">To define a service operation in the Northwind data service</span></span>  
  
1.  <span data-ttu-id="d62e8-113">在 Northwind 数据服务项目中，打开 Northwind.svc 文件。</span><span class="sxs-lookup"><span data-stu-id="d62e8-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="d62e8-114">在 `Northwind` 类中，定义一个名为 `GetOrdersByCity` 的服务操作方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d62e8-114">In the `Northwind` class, define a service operation method named `GetOrdersByCity` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3.  <span data-ttu-id="d62e8-115">在 `InitializeService` 类的 `Northwind` 方法中，添加以下代码以支持对服务操作的访问：</span><span class="sxs-lookup"><span data-stu-id="d62e8-115">In the `InitializeService` method of the `Northwind` class, add the following code to enable access to the service operation:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### <a name="to-query-the-getordersbycity-service-operation"></a><span data-ttu-id="d62e8-116">查询 GetOrdersByCity 服务操作</span><span class="sxs-lookup"><span data-stu-id="d62e8-116">To query the GetOrdersByCity service operation</span></span>  
  
-   <span data-ttu-id="d62e8-117">在 Web 浏览器中，输入以下 URI 之一以调用在以下示例中定义的服务操作：</span><span class="sxs-lookup"><span data-stu-id="d62e8-117">In a Web browser, enter one of the following URIs to invoke the service operation that is defined in the following example:</span></span>  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## <a name="example"></a><span data-ttu-id="d62e8-118">示例</span><span class="sxs-lookup"><span data-stu-id="d62e8-118">Example</span></span>  
 <span data-ttu-id="d62e8-119">以下示例对 Northwind 数据服务实现一个名为 `GetOrderByCity` 的服务操作。</span><span class="sxs-lookup"><span data-stu-id="d62e8-119">The following example implements a service operation named `GetOrderByCity` on the Northwind data service.</span></span> <span data-ttu-id="d62e8-120">此操作根据提供的城市名称使用 ADO.NET 实体框架返回一组 `Orders` 和相关 `Order_Details` 对象，以作为 <xref:System.Linq.IQueryable%601> 实例。</span><span class="sxs-lookup"><span data-stu-id="d62e8-120">This operation uses the ADO.NET Entity Framework to return a set of `Orders` and related `Order_Details` objects as an <xref:System.Linq.IQueryable%601> instance based on the provided city name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d62e8-121">由于此方法返回了一个 <xref:System.Linq.IQueryable%601> 实例，因此该服务操作终结点支持查询运算符。</span><span class="sxs-lookup"><span data-stu-id="d62e8-121">Query operators are supported on this service operation endpoint because the method returns an <xref:System.Linq.IQueryable%601> instance.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## <a name="see-also"></a><span data-ttu-id="d62e8-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d62e8-122">See also</span></span>
- [<span data-ttu-id="d62e8-123">定义 WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d62e8-123">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
