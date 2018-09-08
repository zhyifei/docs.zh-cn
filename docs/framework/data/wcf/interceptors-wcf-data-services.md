---
title: 拦截器（WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: c2086d451af72157785796052af123cd210ee036
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44194937"
---
# <a name="interceptors-wcf-data-services"></a><span data-ttu-id="16033-102">拦截器（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="16033-102">Interceptors (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="16033-103"> 使应用程序能够截获请求消息，以便可以向操作添加自定义逻辑。</span><span class="sxs-lookup"><span data-stu-id="16033-103"> enables an application to intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="16033-104">可以使用此自定义逻辑来验证传入消息中的数据。</span><span class="sxs-lookup"><span data-stu-id="16033-104">You can use this custom logic to validate data in incoming messages.</span></span> <span data-ttu-id="16033-105">还可以使用它进一步限制查询请求的范围，以便基于每个请求插入自定义授权策略。</span><span class="sxs-lookup"><span data-stu-id="16033-105">You can also use it to further restrict the scope of a query request, such as to insert a custom authorization policy on a per request basis.</span></span>  
  
 <span data-ttu-id="16033-106">侦听由数据服务中具有特殊特性的方法执行。</span><span class="sxs-lookup"><span data-stu-id="16033-106">Interception is performed by specially attributed methods in the data service.</span></span> <span data-ttu-id="16033-107">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 在消息处理过程中的适当时刻调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="16033-107">These methods are called by [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] at the appropriate point in message processing.</span></span> <span data-ttu-id="16033-108">对于每个实体集，定义侦听器，侦听器方法无法像服务操作那样接受请求中的参数。</span><span class="sxs-lookup"><span data-stu-id="16033-108">Interceptors are defined on a per-entity set basis, and interceptor methods cannot accept parameters from the request like service operations can.</span></span> <span data-ttu-id="16033-109">处理 HTTP GET 请求时调用的查询侦听器方法必须返回查询结果时应返回 lambda 表达式，用于确定是否设置侦听器的实体的实例。</span><span class="sxs-lookup"><span data-stu-id="16033-109">Query interceptor methods, which are called when processing an HTTP GET request, must return a lambda expression that determines whether an instance of the interceptor's entity set should be returned by the query results.</span></span> <span data-ttu-id="16033-110">数据服务使用此表达式来进一步优化请求的操作。</span><span class="sxs-lookup"><span data-stu-id="16033-110">This expression is used by the data service to further refine the requested operation.</span></span> <span data-ttu-id="16033-111">下面是查询侦听器的定义示例。</span><span class="sxs-lookup"><span data-stu-id="16033-111">The following is an example definition of a query interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 <span data-ttu-id="16033-112">有关详细信息，请参阅[如何： 截获数据服务消息](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="16033-112">For more information, see [How to: Intercept Data Service Messages](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="16033-113">在处理非查询操作时调用的变更侦听器必须返回 `void`（在 Visual Basic 中为 `Nothing`）。</span><span class="sxs-lookup"><span data-stu-id="16033-113">Change interceptors, which are called when processing non-query operations, must return `void` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="16033-114">变更侦听器方法必须接受以下两个参数：</span><span class="sxs-lookup"><span data-stu-id="16033-114">Change interceptor methods must accept the following two parameters:</span></span>  
  
1.  <span data-ttu-id="16033-115">一个与实体集的实体类型相兼容的类型的参数。</span><span class="sxs-lookup"><span data-stu-id="16033-115">A parameter of a type that is compatible with the entity type of the entity set.</span></span> <span data-ttu-id="16033-116">数据服务调用变更侦听器时，此参数的值将反映请求发送的实体信息。</span><span class="sxs-lookup"><span data-stu-id="16033-116">When the data service invokes the change interceptor, the value of this parameter will reflect the entity information that is sent by the request.</span></span>  
  
2.  <span data-ttu-id="16033-117">一个 <xref:System.Data.Services.UpdateOperations> 类型的参数。</span><span class="sxs-lookup"><span data-stu-id="16033-117">A parameter of type <xref:System.Data.Services.UpdateOperations>.</span></span> <span data-ttu-id="16033-118">数据服务调用变更侦听器时，此参数的值将反映请求试图执行的操作。</span><span class="sxs-lookup"><span data-stu-id="16033-118">When the data service invokes the change interceptor, the value of this parameter will reflect the operation that the request is trying to perform.</span></span>  
  
 <span data-ttu-id="16033-119">下面是变更侦听器的定义示例。</span><span class="sxs-lookup"><span data-stu-id="16033-119">The following is an example definition of a change interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 <span data-ttu-id="16033-120">有关详细信息，请参阅[如何： 截获数据服务消息](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="16033-120">For more information, see [How to: Intercept Data Service Messages](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="16033-121">支持使用以下特性进行侦听。</span><span class="sxs-lookup"><span data-stu-id="16033-121">The following attributes are supported for interception.</span></span>  
  
 <span data-ttu-id="16033-122">**[QueryInterceptor (** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="16033-122">**[QueryInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="16033-123">当收到了针对目标实体集资源的 HTTP GET 请求时，将调用应用了 <xref:System.Data.Services.QueryInterceptorAttribute> 特性的方法。</span><span class="sxs-lookup"><span data-stu-id="16033-123">Methods with the <xref:System.Data.Services.QueryInterceptorAttribute> attribute applied are called when an HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="16033-124">这些方法必须始终返回一个 `Expression<Func<T,bool>>` 形式的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="16033-124">These methods must always return a lambda expression in the form of `Expression<Func<T,bool>>`.</span></span>  
  
 <span data-ttu-id="16033-125">**[ChangeInterceptor (** *EntitySetName* **)]**</span><span class="sxs-lookup"><span data-stu-id="16033-125">**[ChangeInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="16033-126">当收到了针对目标实体集资源的 HTTP GET 请求以外的 HTTP 请求时，将调用应用了 <xref:System.Data.Services.ChangeInterceptorAttribute> 特性的方法。</span><span class="sxs-lookup"><span data-stu-id="16033-126">Methods with the <xref:System.Data.Services.ChangeInterceptorAttribute> attribute applied are called when an HTTP request other than HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="16033-127">这些方法必须始终返回 `void`（在 Visual Basic 中为 `Nothing`）。</span><span class="sxs-lookup"><span data-stu-id="16033-127">These methods must always return `void` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="16033-128">有关详细信息，请参阅[如何： 截获数据服务消息](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="16033-128">For more information, see [How to: Intercept Data Service Messages](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16033-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="16033-129">See Also</span></span>  
 [<span data-ttu-id="16033-130">服务操作</span><span class="sxs-lookup"><span data-stu-id="16033-130">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)
