---
title: WCF 数据服务 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 1ce152b84f17a35982a75f54b5418623ba39210f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975224"
---
# <a name="wcf-data-services-45"></a>WCF 数据服务 4.5

WCF 数据服务（以前称为 "ADO.NET Data Services"）是 .NET Framework 的一个组件，它使你能够使用[具象状态传输（REST）](https://go.microsoft.com/fwlink/?LinkId=113919)的语义创建使用 Open Data Protocol （OData）在 Web 或 intranet 上公开和使用数据的服务。 OData 将数据公开为可通过 URI 进行寻址的资源。 通过使用标准 HTTP 谓词 GET、PUT、POST 和 DELETE 访问和更改数据。 OData 使用[实体数据模型](../adonet/entity-data-model.md)的实体关系约定将资源公开为通过关联相关的实体集。

WCF 数据服务使用 OData 协议对资源进行寻址和更新。 通过这种方式，你可以从支持 OData 的任何客户端访问这些服务。 OData 使你可以通过使用众所周知的传输格式请求数据并将数据写入资源： Atom，一组用于以 XML 格式交换和更新数据的标准，以及 JavaScript 对象表示法（JSON），这是在 AJAX 中广泛使用的基于文本的数据交换格式。应用程序.

WCF 数据服务可以将源自各种源的数据作为 OData 源公开。 Visual Studio 工具通过使用 ADO.NET 实体框架数据模型，使你可以更轻松地创建基于 OData 的服务。 还可以基于公共语言运行时（CLR）类，甚至是后期绑定或未类型化的数据来创建 OData 源。

WCF 数据服务还包括一组客户端库，一个用于一般 .NET Framework 客户端应用程序，另一个专用于基于 Silverlight 的应用程序。 当你从 .NET Framework 和 Silverlight 等环境中访问 OData 源时，这些客户端库提供了基于对象的编程模型。

## <a name="where-should-i-start"></a>从何处开始？

根据你的兴趣，请考虑以下主题之一中的 WCF 数据服务入门。

我希望直接开始使用...

- [快速入门](quickstart-wcf-data-services.md)

- [入门](getting-started-with-wcf-data-services.md)

- [Silverlight 快速入门](https://go.microsoft.com/fwlink/?LinkID=192782)

- [Windows Phone 开发 Silverlight 快速入门](https://go.microsoft.com/fwlink/?LinkID=214535)

只显示一些代码 。

- [快速入门](quickstart-wcf-data-services.md)

- [如何：执行数据服务查询](how-to-execute-data-service-queries-wcf-data-services.md)

- [如何：将数据绑定到 Windows Presentation Foundation 元素](bind-data-to-wpf-elements-wcf-data-services.md)

我想了解有关 OData 的详细信息 。

- [白皮书：OData 简介](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Open Data Protocol 网站](https://go.microsoft.com/fwlink/?LinkID=184554)

- [OData：SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

- [OData：常见问题](https://go.microsoft.com/fwlink/?LinkId=185867)

我想观看一些视频 。

- [WCF Data Services 初学者指南](https://go.microsoft.com/fwlink/?LinkId=220864)

- [WCF Data Services 开发人员视频](https://go.microsoft.com/fwlink/?LinkId=220861)

- [OData：开发人员网站](https://go.microsoft.com/fwlink/?LinkId=185866)

我想要查看端到端示例 。

- [MSDN 示例库上的 WCF Data Services 文档示例](https://go.microsoft.com/fwlink/?LinkID=220865)

- [MSDN 示例库上的其他 WCF Data Services 示例](https://go.microsoft.com/fwlink/?LinkId=220866)

- [OData：SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

它如何与 Visual Studio 集成？

- [生成数据服务客户端库](generating-the-data-service-client-library-wcf-data-services.md)

- [创建数据服务](creating-the-data-service.md)

- [实体框架提供程序](entity-framework-provider-wcf-data-services.md)

我可以对它执行何种操作？

- [概述](wcf-data-services-overview.md)

- [白皮书：OData 简介](https://go.microsoft.com/fwlink/?LinkId=220867)

- [应用程序方案](application-scenarios-wcf-data-services.md)

我想使用 Silverlight 。

- [Silverlight 快速入门](https://go.microsoft.com/fwlink/?LinkID=192782)

- [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)

- [Silverlight 入门](https://go.microsoft.com/fwlink/?LinkId=148366)

我想要使用 LINQ 。

- [查询数据服务](querying-the-data-service-wcf-data-services.md)

- [LINQ 注意事项](linq-considerations-wcf-data-services.md)

- [如何：执行数据服务查询](how-to-execute-data-service-queries-wcf-data-services.md)

我仍然需要了解更多信息 。

- [WCF Data Services Team Blog](https://go.microsoft.com/fwlink/?LinkID=150511)（WCF Data Services 团队博客）

- [资源](wcf-data-services-resources.md)

- [WCF Data Services 开发人员中心](https://go.microsoft.com/fwlink/?LinkId=220868)

- [Open Data Protocol 网站](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a>本节内容

[概述](wcf-data-services-overview.md)

概述 WCF 数据服务中可用的特性和功能。

[WCF 数据服务5.0 的新增功能](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))

介绍 WCF 数据服务的新功能，并支持新的 OData 功能。

[入门](getting-started-with-wcf-data-services.md)

介绍如何使用 WCF 数据服务公开和使用 OData 源。

[定义 WCF Data Services](defining-wcf-data-services.md)

介绍如何创建和配置公开 OData 源的数据服务。

[WCF Data Services 客户端库](wcf-data-services-client-library.md)

介绍如何使用客户端库从 .NET Framework 客户端应用程序中使用 OData 源。

## <a name="see-also"></a>请参阅

- [Representational State Transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)（表述性状态转移 (REST)）
