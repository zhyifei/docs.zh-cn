---
title: 快速入门（WCF 数据服务）
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: d0002182c5ae519c36348acdd2587bca499fe72e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975139"
---
# <a name="quickstart-wcf-data-services"></a>快速入门（WCF 数据服务）

本快速入门通过一系列支持[入门](getting-started-with-wcf-data-services.md)中的主题的任务，帮助你熟悉 WCF 数据服务和 Open Data Protocol （OData）。

## <a name="what-youll-learn"></a>你将学习的内容

本快速入门中的第一项任务介绍如何创建数据服务以公开 Northwind 示例数据库中的 OData 数据源。 在后面的主题中，你将使用 Web 浏览器访问 OData 源，并创建使用客户端库使用 OData 源的 Windows Presentation Foundation （WPF）客户端应用程序。

## <a name="prerequisites"></a>Prerequisites

为了完成本快速入门，必须安装以下组件：

- Visual Studio

- SQL Server 的实例。 这包括 SQL Server Express （Visual Studio 2015 的默认安装中提供），或者作为 Visual Studio 2017 中的**数据存储和处理**工作负荷的一部分。

- Northwind 示例数据库。 若要下载此示例数据库，请访问 [SQL Server 的示例数据库](https://go.microsoft.com/fwlink/?linkid=24758)下载页。

## <a name="wcf-data-services-quickstart-tasks"></a>WCF 数据服务快速入门任务

 [创建数据服务](creating-the-data-service.md)

 定义 ASP.NET 应用程序，定义数据模型，创建数据服务，并启用对资源的访问。

 [从 Web 浏览器访问服务](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 通过 Visual Studio 启动服务，并通过 Web 浏览器向公开的源提交 HTTP GET 请求以访问该服务。

 [创建 .NET Framework 客户端应用程序](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 创建一个使用 OData 源的 WPF 应用程序，将数据绑定到 Windows 控件，在绑定控件中更改数据，然后将更改发送回数据服务。

> [!NOTE]
> 已完成版本的快速入门中的项目文件可从 [WCF 数据服务文档示例](https://go.microsoft.com/fwlink/?LinkId=179994) 网页下载。

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [启动快速入门](creating-the-data-service.md)

## <a name="see-also"></a>请参阅

- [ADO.NET 实体框架](../adonet/ef/index.md)
