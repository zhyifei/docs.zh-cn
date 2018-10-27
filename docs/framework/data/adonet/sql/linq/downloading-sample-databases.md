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
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="01b58-103">获取示例数据库的 ADO.NET 代码示例</span><span class="sxs-lookup"><span data-stu-id="01b58-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="01b58-104">示例和演练中的大量[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档使用示例数据库和 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="01b58-104">A number of samples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample databases and SQL Server Express.</span></span> <span data-ttu-id="01b58-105">可从 Microsoft 下载这些免费的产品。</span><span class="sxs-lookup"><span data-stu-id="01b58-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database"></a><span data-ttu-id="01b58-106">获取 Northwind 示例数据库</span><span class="sxs-lookup"><span data-stu-id="01b58-106">Get the Northwind sample database</span></span>

<span data-ttu-id="01b58-107">从 Microsoft 下载中心中的以下页面下载 Northwind 示例数据库：</span><span class="sxs-lookup"><span data-stu-id="01b58-107">Download the Northwind sample database from the following page in the Microsoft Download Center:</span></span>

[<span data-ttu-id="01b58-108">Northwind 和 Pubs 示例数据库</span><span class="sxs-lookup"><span data-stu-id="01b58-108">Northwind and Pubs Sample Databases</span></span>](https://go.microsoft.com/fwlink?linkid=64296)

<span data-ttu-id="01b58-109">下载文件后，双击文件以提取数据库和脚本。</span><span class="sxs-lookup"><span data-stu-id="01b58-109">After the file has downloaded, double-click the file to extract the databases and scripts.</span></span> <span data-ttu-id="01b58-110">默认情况下，文件安装在文件夹中`<drive>:\SQL Server 2000 Sample Databases`。</span><span class="sxs-lookup"><span data-stu-id="01b58-110">By default, the files are installed in the folder `<drive>:\SQL Server 2000 Sample Databases`.</span></span>

<span data-ttu-id="01b58-111">可以使用 Northwind 数据库之前，必须使用重新创建的 SQL Server 实例上的数据库[SQL Server Management Studio](#get_ssms)或类似的工具运行`instnwnd.sql`安装文件夹中的脚本文件。</span><span class="sxs-lookup"><span data-stu-id="01b58-111">Before you can use the Northwind database, you have to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool to run the `instnwnd.sql` script file in the installation folder.</span></span>

## <a name="get-the-adventureworks-sample-database"></a><span data-ttu-id="01b58-112">获取 AdventureWorks 示例数据库</span><span class="sxs-lookup"><span data-stu-id="01b58-112">Get the AdventureWorks sample database</span></span>

<span data-ttu-id="01b58-113">从以下 GitHub 存储库下载 AdventureWorks 示例数据库：</span><span class="sxs-lookup"><span data-stu-id="01b58-113">Download the AdventureWorks sample database from the following GitHub repository:</span></span>

[<span data-ttu-id="01b58-114">AdventureWorks 示例数据库</span><span class="sxs-lookup"><span data-stu-id="01b58-114">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="01b58-115">下载一个数据库备份后 (\*.bak) 文件，将备份还原到的 SQL Server 实例使用 SQL Server Management Studio (SSMS)。</span><span class="sxs-lookup"><span data-stu-id="01b58-115">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="01b58-116">请参阅[获取 SQL Server Management Studio](#get_ssms)。</span><span class="sxs-lookup"><span data-stu-id="01b58-116">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_sql"></a> <span data-ttu-id="01b58-117">获取 SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="01b58-117">Get SQL Server Express</span></span>

<span data-ttu-id="01b58-118">SQL Server Express 是免费的入门级版本可以与应用程序重新发布的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="01b58-118">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="01b58-119">下载 SQL Server Express 的以下页面：</span><span class="sxs-lookup"><span data-stu-id="01b58-119">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="01b58-120">SQL Server Express 版本</span><span class="sxs-lookup"><span data-stu-id="01b58-120">SQL Server Express Editions</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="01b58-121">如果您使用的[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)，在免费的社区版和专业和更高版本包括 SQL Server Express LocalDB。</span><span class="sxs-lookup"><span data-stu-id="01b58-121">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition as well as the Professional and higher editions.</span></span>  

## <a name="get_ssms"></a> <span data-ttu-id="01b58-122">获取 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="01b58-122">Get SQL Server Management Studio</span></span>
<span data-ttu-id="01b58-123">如果你想要查看或修改已下载的数据库，可以使用 SQL Server Management Studio (SSMS)。</span><span class="sxs-lookup"><span data-stu-id="01b58-123">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="01b58-124">从以下页面下载 SSMS:</span><span class="sxs-lookup"><span data-stu-id="01b58-124">Download SSMS from the following page:</span></span>

[<span data-ttu-id="01b58-125">下载 SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="01b58-125">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="01b58-126">您还可以查看和管理 Visual Studio 集成的开发环境 (IDE) 中的数据库。</span><span class="sxs-lookup"><span data-stu-id="01b58-126">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="01b58-127">在中[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)，连接到从数据库**SQL Server 对象资源管理器**，或创建到数据库中的数据连接**服务器资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="01b58-127">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="01b58-128">打开从这些资源管理器窗格**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="01b58-128">Open these explorer panes from the **View** menu.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="01b58-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="01b58-129">See also</span></span>

- [<span data-ttu-id="01b58-130">入门</span><span class="sxs-lookup"><span data-stu-id="01b58-130">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
