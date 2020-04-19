---
title: 获取ADO.NET代码示例的示例 SQL Server 数据库
description: 下载ADO.NET文档中代码示例中使用的示例 SQL Server 数据库，以及 SQL Server 和管理工具
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 3449f502834f449f5023bd52457d45ffaf9b0fa1
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607979"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>获取ADO.NET代码示例的示例数据库

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档中的一些示例和演练使用示例 SQL Server 数据库和 SQL Server Express。 你可以从微软免费下载这些产品。

## <a name="get-the-northwind-sample-database-for-sql-server"></a>获取 SQL Server 的北风示例数据库

从以下`instnwnd.sql`GitHub 存储库下载脚本，以创建并加载 SQL Server 的北风示例数据库：

[Northwind 和 pubs 示例数据库为 Microsoft SQL 服务器](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

在使用 Northwind 数据库之前，必须运行下载的`instnwnd.sql`脚本文件，以便使用 SQL Server[管理工作室](#get_ssms)或类似工具在 SQL Server 实例上重新创建数据库。 按照存储库中的 Readme 文件中的说明进行操作。

> [!TIP]
> 如果您正在寻找适用于 Microsoft Access 的北风数据库，请参阅[安装 Microsoft Access 的北风示例数据库](#northwind_access)。

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a>获取适用于 Microsoft 访问的北风示例数据库

微软访问的北风示例数据库在 Microsoft 下载中心不可用。 要直接从 Access 内部安装北风，请执行以下操作：

1. 打开访问。

1. 在 **"搜索联机模板"** 框中输入**北风**，然后选择"**输入**"。

1. 在结果屏幕上，选择**北风**。 将打开一个新窗口，其中说明北风数据库。

1. 在新窗口中，在 **"文件名**"文本框中，为北风数据库的副本提供文件名。

1. 选择“创建”  。 访问下载北风数据库并准备文件。

1. 此过程完成后，数据库将打开，并带有"欢迎"屏幕。

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>获取 SQL Server 的 AdventureWorks 示例数据库

从以下 GitHub 存储库下载 SQL Server 的 AdventureWorks 示例数据库：

[AdventureWorks sample databases](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)（AdventureWorks 示例数据库）

下载其中一个数据库备份 （.bak）\*文件后，请使用 SQL Server 管理工作室 （SSMS） 将备份还原到 SQL Server 实例。 请参阅[获取 SQL 服务器管理工作室](#get_ssms)。

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a>获取 SQL 服务器管理工作室
如果要查看或修改已下载的数据库，可以使用 SQL 服务器管理工作室 （SSMS）。 从以下页面下载 SSMS：

[下载 SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms)

您还可以在可视化工作室集成开发环境 （IDE） 中查看和管理数据库。 在[可视化工作室](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)中，从 SQL**服务器对象资源管理器**连接到数据库，或在**服务器资源管理器**中创建到数据库的数据连接。 从 **"视图"** 菜单打开这些资源管理器窗格。

## <a name="get-sql-server-express"></a><a name="get_sql"></a>获取 SQL 服务器快速

SQL Server Express 是一个免费的入门级 SQL Server 版本，您可以使用应用程序重新分发。 从以下页面下载 SQL 服务器快速服务：
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

如果您使用的是[Visual Studio，SQL](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)Server Express 本地DB 包含在 Visual Studio 的免费社区版以及专业版和更高版本中。  

## <a name="see-also"></a>请参阅

- [入门](getting-started.md)
