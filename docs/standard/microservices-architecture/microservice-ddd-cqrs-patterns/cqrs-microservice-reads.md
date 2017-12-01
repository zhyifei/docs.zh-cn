---
title: "在 CQRS 微服务中实现读取/查询"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |在 CQRS 微服务中实现读取/查询"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e017aaaa701d8033110be8d6244d3e1120fc4fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-readsqueries-in-a-cqrs-microservice"></a>在 CQRS 微服务中实现读取/查询

对于读取/查询，排序的微服务构成从 eShopOnContainers 引用应用程序实现独立于 DDD 模型和事务的区域的查询。 这样做的主要原因和事务的查询的需求较大不相同。 写入执行必须符合域逻辑的事务。 另一方面，查询是幂等的和可以分隔开来域规则。

这种方法很简单，如图 9-3 中所示。 API 接口实现的 Web API 控制器使用任何基础结构 （如微 ORM 如 Dapper） 并返回动态 Viewmodel 具体取决于 UI 应用程序的需求。

![](./media/image3.png)

**图 9-3**。 CQRS 微服务中查询的最简单的方法

这是最简单的可能的方法的查询。 查询定义查询数据库，并返回每个查询动态生成动态视图模型。 由于查询是幂等的它们不会更改数据，而无论多少次运行查询。 因此，不需要通过事务端，如聚合和其他模式中使用任何 DDD 模式进行限制，并且正因如此，从事务区域分隔查询。 你只需查询数据库中的用户界面需要的数据，并返回不需要被静态地动态 ViewModel 随处 （用于 Viewmodel 任何类） 除外中定义自己的 SQL 语句。

由于这是一种简单方法，代码所需的查询端 (如代码使用 ORM 喜欢 micro [Dapper](https://github.com/StackExchange/Dapper)) 可以实现[同一 Web API 项目中](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs)。 图 9-4 演示了此过程。 在中定义查询**Ordering.API** eShopOnContainers 解决方案中的微服务项目。

![](./media/image4.png)

**图 9-4**。 在 eShopOnContainers 排序微服务中的查询

## <a name="using-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a>使用 Viewmodel 专门供客户端应用，独立于域模型约束

由于执行查询以获取客户端应用程序所需的数据，则返回的类型可以专门进行对于客户端，在基于由查询返回的数据。 这些模型或数据传输对象 (Dto)，称为 Viewmodel。

返回的数据 (ViewModel) 可以联接来自多个实体或表的数据，在数据库中，或甚至可跨多个事务的区域的域模型中定义的聚合的结果。 在这种情况下，由于你要创建查询独立的域模型，完全忽略聚合边界和约束，并且你是可用来查询任何表和列可能需要。 此方法为开发人员创建或更新查询提供极大的灵活性和工作效率。

Viewmodel 可以是在类中定义的静态类型。 或者可以创建动态基于查询执行 （如在排序的微服务中实现），这是非常灵活的开发人员。

## <a name="using-dapper-as-a-micro-orm-to-perform-queries"></a>使用 Dapper 作为微型 ORM 执行查询 

用于查询，可以使用任何微型 ORM、 实体框架核心或甚至纯 ADO.NET。 在示例应用程序，我们将选择 Dapper 中常用的微型 ORM 一个很好示例作为 eShopOnContainers 排序微服务构成的。 它可以具有卓越性能，运行纯 SQL 查询，因为它是一个非常轻量的框架。 使用 Dapper，你可以编写可访问和联接多个表的 SQL 查询。

Dapper 是开放源代码项目 （由 Sam Saffron 创建的原始），并且是在中使用的构建基块的一部分[堆栈溢出](https://stackoverflow.com/)。 若要使用 Dapper，只需将其通过安装[Dapper NuGet 包](https://www.nuget.org/packages/Dapper)下, 图中所示。

![](./media/image5.png)

你还需要添加 using 语句，使你的代码有权访问 Dapper 扩展方法。

在代码中使用 Dapper 时，你将直接使用 SqlClient 类 System.Data.SqlClient 命名空间中提供。 通过 QueryAsync 方法和其他扩展方法，它 SqlClient 类进行扩展，你只需直观且高性能的方式运行查询。

## <a name="dynamic-and-static-viewmodels"></a>动态和静态 Viewmodel

大部分由查询返回 Viewmodel 排序微服务构成从下面的代码中所示，作为实现*动态*。 这意味着要返回的属性的子集基于查询本身。 如果你将新列添加到查询或联接时，该数据是动态添加到返回视图模型。 此方法可以降低需要在更新部署到基础数据模型，更加灵活和容错的将来的更改进行此设计方法响应修改查询。

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
    public async Task<IEnumerable<dynamic>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<dynamic>(
@"SELECT o.[Id] as ordernumber,
o.[OrderDate] as [date],os.[Name] as [status],
SUM(oi.units*oi.unitprice) as total
FROM [ordering].[Orders] o
LEFT JOIN[ordering].[orderitems] oi ON o.Id = oi.orderid
LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
GROUP BY o.[Id], o.[OrderDate], os.[Name]");
        }
  }
}
```

重要的一点是，通过使用动态类型，则返回的集合的数据将被动态组装为视图模型。

对于大多数查询，你不需要预定义 DTO 或 ViewModel 类，这使对其进行编码简单和高效。 但是，如果你想要作为协定的更受限制定义 Viewmodel 可以预定义 Viewmodel （如预定义 Dto)。

#### <a name="additional-resources"></a>其他资源

-   **Dapper**
    [*https://github.com/StackExchange/dapper-dot-net*](https://github.com/StackExchange/dapper-dot-net)

-   **Julie Lerman。数据点-Dapper、 实体框架和混合应用程序 （MSDN Mag.文章）**

    *https://msdn.microsoft.com/en-us/magazine/mt703432.aspx*


>[!div class="step-by-step"]
[以前](eshoponcontainers-cqrs-ddd-microservice.md) [下一步] (ddd-面向-microservice.md)
