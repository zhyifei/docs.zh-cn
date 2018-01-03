---
title: "基于方法的查询语法示例：导航关系"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a0bfa4b1-99e5-4dd1-9912-4b825a9dc25c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 239e990c5a02962887e66f1bbc18358835006ac1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="method-based-query-syntax-examples-navigating-relationships"></a><span data-ttu-id="54283-102">基于方法的查询语法示例：导航关系</span><span class="sxs-lookup"><span data-stu-id="54283-102">Method-Based Query Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="54283-103">[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]中的导航属性是快捷方式属性，用于定位位于关联各端的实体。</span><span class="sxs-lookup"><span data-stu-id="54283-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="54283-104">导航属性允许用户通过关联集从一个实体导航到另一个实体或从一个实体导航到多个相关的实体。</span><span class="sxs-lookup"><span data-stu-id="54283-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="54283-105">本主题以基于方法的查询语法提供相关的示例，以介绍如何通过 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 查询中的导航属性来导航关系。</span><span class="sxs-lookup"><span data-stu-id="54283-105">This topic provides examples in method-based query syntax of how to navigate relationships through navigation properties in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="54283-106">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="54283-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="54283-107">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="54283-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="54283-108">示例</span><span class="sxs-lookup"><span data-stu-id="54283-108">Example</span></span>  
 <span data-ttu-id="54283-109">采用基于方法的查询语法的以下示例使用 <xref:System.Linq.Queryable.SelectMany%2A> 方法以获取其姓氏为“Zhou”的联系人的所有订单。</span><span class="sxs-lookup"><span data-stu-id="54283-109">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.SelectMany%2A> method to get all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="54283-110">`Contact.SalesOrderHeader` 导航属性用于获取每个联系人的 `SalesOrderHeader` 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="54283-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders_mq)]  
  
## <a name="example"></a><span data-ttu-id="54283-111">示例</span><span class="sxs-lookup"><span data-stu-id="54283-111">Example</span></span>  
 <span data-ttu-id="54283-112">采用基于方法的查询语法的以下示例使用 <xref:System.Linq.Queryable.Select%2A> 方法以获取所有联系人 ID 和姓氏为“Zhou”的每个联系人的应付款总计。</span><span class="sxs-lookup"><span data-stu-id="54283-112">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="54283-113">`Contact.SalesOrderHeader` 导航属性用于获取每个联系人的 `SalesOrderHeader` 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="54283-113">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="54283-114">`Sum` 方法使用 `Contact.SalesOrderHeader` 导航属性以汇总每个联系人的所有订单的应付款总计。</span><span class="sxs-lookup"><span data-stu-id="54283-114">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2_mq)]  
  
## <a name="example"></a><span data-ttu-id="54283-115">示例</span><span class="sxs-lookup"><span data-stu-id="54283-115">Example</span></span>  
 <span data-ttu-id="54283-116">采用基于方法的查询语法的以下示例获取其姓氏为“Zhou”的联系人的所有订单。</span><span class="sxs-lookup"><span data-stu-id="54283-116">The following example in method-based query syntax gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="54283-117">`Contact.SalesOrderHeader` 导航属性用于获取每个联系人的 `SalesOrderHeader` 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="54283-117">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="54283-118">联系人的姓名和订单以匿名类型返回。</span><span class="sxs-lookup"><span data-stu-id="54283-118">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3_mq)]  
  
## <a name="example"></a><span data-ttu-id="54283-119">示例</span><span class="sxs-lookup"><span data-stu-id="54283-119">Example</span></span>  
 <span data-ttu-id="54283-120">以下示例使用 `SalesOrderHeader.Address` 和 `SalesOrderHeader.Contact` 导航属性以获取与每个订单关联的 `Address` 对象和 `Contact` 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="54283-120">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties to get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="54283-121">Seattle 城市发生的每个订单的联系人姓氏、街道地址、销售订单号和应付款总计将以匿名类型返回。</span><span class="sxs-lookup"><span data-stu-id="54283-121">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships_mq)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships_mq)]  
  
## <a name="example"></a><span data-ttu-id="54283-122">示例</span><span class="sxs-lookup"><span data-stu-id="54283-122">Example</span></span>  
 <span data-ttu-id="54283-123">以下示例使用 `Where` 方法以查找在 2003 年 12 月 1 日之后生成的订单，然后使用 `order.SalesOrderDetail` 导航属性以获取每个订单的详细信息。</span><span class="sxs-lookup"><span data-stu-id="54283-123">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="54283-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="54283-124">See Also</span></span>  
 [<span data-ttu-id="54283-125">导航属性</span><span class="sxs-lookup"><span data-stu-id="54283-125">Navigation Properties</span></span>](http://msdn.microsoft.com/en-us/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
 [<span data-ttu-id="54283-126">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="54283-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
