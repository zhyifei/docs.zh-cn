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
ms.openlocfilehash: c9799037ae0ea8b29b5e989859aff29c310593d4
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568970"
---
# <a name="interceptors-wcf-data-services"></a><span data-ttu-id="3809a-102">拦截器（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="3809a-102">Interceptors (WCF Data Services)</span></span>
<span data-ttu-id="3809a-103">WCF 数据服务使应用程序能够截获请求消息，以便可以向操作添加自定义逻辑。</span><span class="sxs-lookup"><span data-stu-id="3809a-103">WCF Data Services enables an application to intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="3809a-104">您可以使用此自定义逻辑来验证传入消息中的数据。</span><span class="sxs-lookup"><span data-stu-id="3809a-104">You can use this custom logic to validate data in incoming messages.</span></span> <span data-ttu-id="3809a-105">还可以使用它进一步限制查询请求的范围，以便基于每个请求插入自定义授权策略。</span><span class="sxs-lookup"><span data-stu-id="3809a-105">You can also use it to further restrict the scope of a query request, such as to insert a custom authorization policy on a per request basis.</span></span>  
  
 <span data-ttu-id="3809a-106">侦听由数据服务中具有特殊特性的方法执行。</span><span class="sxs-lookup"><span data-stu-id="3809a-106">Interception is performed by specially attributed methods in the data service.</span></span> <span data-ttu-id="3809a-107">WCF 数据服务在消息处理中的相应点调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="3809a-107">These methods are called by WCF Data Services at the appropriate point in message processing.</span></span> <span data-ttu-id="3809a-108">拦截程序是根据每个实体集定义的，侦听器方法不能接受来自服务操作可能这样的请求的参数。</span><span class="sxs-lookup"><span data-stu-id="3809a-108">Interceptors are defined on a per-entity set basis, and interceptor methods cannot accept parameters from the request like service operations can.</span></span> <span data-ttu-id="3809a-109">在处理 HTTP GET 请求时调用的查询侦听器方法必须返回一个 lambda 表达式，该表达式确定是否应由查询结果返回侦听器的实体集的实例。</span><span class="sxs-lookup"><span data-stu-id="3809a-109">Query interceptor methods, which are called when processing an HTTP GET request, must return a lambda expression that determines whether an instance of the interceptor's entity set should be returned by the query results.</span></span> <span data-ttu-id="3809a-110">数据服务使用此表达式来进一步优化请求的操作。</span><span class="sxs-lookup"><span data-stu-id="3809a-110">This expression is used by the data service to further refine the requested operation.</span></span> <span data-ttu-id="3809a-111">下面是查询侦听器的定义示例。</span><span class="sxs-lookup"><span data-stu-id="3809a-111">The following is an example definition of a query interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 <span data-ttu-id="3809a-112">有关详细信息，请参阅[如何：截获数据服务消息](how-to-intercept-data-service-messages-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3809a-112">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="3809a-113">在处理非查询操作时调用的变更侦听器必须返回 `void`（在 Visual Basic 中为 `Nothing`）。</span><span class="sxs-lookup"><span data-stu-id="3809a-113">Change interceptors, which are called when processing non-query operations, must return `void` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="3809a-114">变更侦听器方法必须接受以下两个参数：</span><span class="sxs-lookup"><span data-stu-id="3809a-114">Change interceptor methods must accept the following two parameters:</span></span>  
  
1. <span data-ttu-id="3809a-115">一个与实体集的实体类型相兼容的类型的参数。</span><span class="sxs-lookup"><span data-stu-id="3809a-115">A parameter of a type that is compatible with the entity type of the entity set.</span></span> <span data-ttu-id="3809a-116">数据服务调用变更侦听器时，此参数的值将反映请求发送的实体信息。</span><span class="sxs-lookup"><span data-stu-id="3809a-116">When the data service invokes the change interceptor, the value of this parameter will reflect the entity information that is sent by the request.</span></span>  
  
2. <span data-ttu-id="3809a-117">一个 <xref:System.Data.Services.UpdateOperations> 类型的参数。</span><span class="sxs-lookup"><span data-stu-id="3809a-117">A parameter of type <xref:System.Data.Services.UpdateOperations>.</span></span> <span data-ttu-id="3809a-118">数据服务调用变更侦听器时，此参数的值将反映请求试图执行的操作。</span><span class="sxs-lookup"><span data-stu-id="3809a-118">When the data service invokes the change interceptor, the value of this parameter will reflect the operation that the request is trying to perform.</span></span>  
  
 <span data-ttu-id="3809a-119">下面是变更侦听器的定义示例。</span><span class="sxs-lookup"><span data-stu-id="3809a-119">The following is an example definition of a change interceptor.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 <span data-ttu-id="3809a-120">有关详细信息，请参阅[如何：截获数据服务消息](how-to-intercept-data-service-messages-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3809a-120">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="3809a-121">支持使用以下特性进行侦听。</span><span class="sxs-lookup"><span data-stu-id="3809a-121">The following attributes are supported for interception.</span></span>  
  
 <span data-ttu-id="3809a-122">**[QueryInterceptor （** *EntitySetName* **）]**</span><span class="sxs-lookup"><span data-stu-id="3809a-122">**[QueryInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="3809a-123">当收到了针对目标实体集资源的 HTTP GET 请求时，将调用应用了 <xref:System.Data.Services.QueryInterceptorAttribute> 特性的方法。</span><span class="sxs-lookup"><span data-stu-id="3809a-123">Methods with the <xref:System.Data.Services.QueryInterceptorAttribute> attribute applied are called when an HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="3809a-124">这些方法必须始终返回一个 `Expression<Func<T,bool>>` 形式的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="3809a-124">These methods must always return a lambda expression in the form of `Expression<Func<T,bool>>`.</span></span>  
  
 <span data-ttu-id="3809a-125">**[ChangeInterceptor （** *EntitySetName* **）]**</span><span class="sxs-lookup"><span data-stu-id="3809a-125">**[ChangeInterceptor(** *EntitySetName* **)]**</span></span>  
 <span data-ttu-id="3809a-126">当收到了针对目标实体集资源的 HTTP GET 请求以外的 HTTP 请求时，将调用应用了 <xref:System.Data.Services.ChangeInterceptorAttribute> 特性的方法。</span><span class="sxs-lookup"><span data-stu-id="3809a-126">Methods with the <xref:System.Data.Services.ChangeInterceptorAttribute> attribute applied are called when an HTTP request other than HTTP GET request is received for the targeted entity set resource.</span></span> <span data-ttu-id="3809a-127">这些方法必须始终返回 `void`（在 Visual Basic 中为 `Nothing`）。</span><span class="sxs-lookup"><span data-stu-id="3809a-127">These methods must always return `void` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="3809a-128">有关详细信息，请参阅[如何：截获数据服务消息](how-to-intercept-data-service-messages-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3809a-128">For more information, see [How to: Intercept Data Service Messages](how-to-intercept-data-service-messages-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3809a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3809a-129">See also</span></span>

- [<span data-ttu-id="3809a-130">服务操作</span><span class="sxs-lookup"><span data-stu-id="3809a-130">Service Operations</span></span>](service-operations-wcf-data-services.md)
