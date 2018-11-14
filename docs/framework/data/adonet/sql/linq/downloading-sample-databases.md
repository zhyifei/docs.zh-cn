---
title: 获取示例数据库的 ADO.NET 代码示例
description: 下载 ADO.NET 文档以及 SQL Server 和管理工具中的代码示例中使用的示例数据库
ms.date: 10/18/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 9779300288135cb9332a028d547ce55a07e89471
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188386"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>获取示例数据库的 ADO.NET 代码示例

示例和演练中的大量[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档使用示例数据库和 SQL Server Express。 可从 Microsoft 下载这些免费的产品。

## <a name="get-the-northwind-sample-database"></a>获取 Northwind 示例数据库

从 Microsoft 下载中心中的以下页面下载 Northwind 示例数据库：

[Northwind 和 Pubs 示例数据库](https://go.microsoft.com/fwlink?linkid=64296)

下载文件后，双击文件以提取数据库和脚本。 默认情况下，文件安装在文件夹中`<drive>:\SQL Server 2000 Sample Databases`。

可以使用 Northwind 数据库之前，必须使用重新创建的 SQL Server 实例上的数据库[SQL Server Management Studio](#get_ssms)或类似的工具运行`instnwnd.sql`安装文件夹中的脚本文件。

## <a name="get-the-adventureworks-sample-database"></a>获取 AdventureWorks 示例数据库

从以下 GitHub 存储库下载 AdventureWorks 示例数据库：

[AdventureWorks 示例数据库](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

下载一个数据库备份后 (\*.bak) 文件，将备份还原到的 SQL Server 实例使用 SQL Server Management Studio (SSMS)。 请参阅[获取 SQL Server Management Studio](#get_ssms)。

## <a name="get_sql"></a> 获取 SQL Server Express

SQL Server Express 是免费的入门级版本可以与应用程序重新发布的 SQL Server。 下载 SQL Server Express 的以下页面：
  
[SQL Server Express 版本](https://www.microsoft.com/sql-server/sql-server-editions-express)

如果您使用的[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)，在免费的社区版和专业和更高版本包括 SQL Server Express LocalDB。  

## <a name="get_ssms"></a> 获取 SQL Server Management Studio
如果你想要查看或修改已下载的数据库，可以使用 SQL Server Management Studio (SSMS)。 从以下页面下载 SSMS:

[下载 SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) 

您还可以查看和管理 Visual Studio 集成的开发环境 (IDE) 中的数据库。 在中[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)，连接到从数据库**SQL Server 对象资源管理器**，或创建到数据库中的数据连接**服务器资源管理器**。 打开从这些资源管理器窗格**视图**菜单。
  
## <a name="see-also"></a>请参阅

- [入门](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
