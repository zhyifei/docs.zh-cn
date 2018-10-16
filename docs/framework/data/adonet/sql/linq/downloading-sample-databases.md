---
title: 获取示例数据库的 ADO.NET 代码示例
description: 下载 ADO.NET 文档以及 SQL Server 和管理工具中的代码示例中使用的示例数据库
ms.date: 10/12/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 75ae1895d683b669f51b33130fc2f47010e39814
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347492"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="1aa63-103">获取示例数据库的 ADO.NET 代码示例</span><span class="sxs-lookup"><span data-stu-id="1aa63-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="1aa63-104">示例和演练中的大量[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档使用示例数据库和 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="1aa63-104">A number of samples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample databases and SQL Server Express.</span></span> <span data-ttu-id="1aa63-105">可从 Microsoft 下载这些免费的产品。</span><span class="sxs-lookup"><span data-stu-id="1aa63-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-adventureworks-sample-database"></a><span data-ttu-id="1aa63-106">获取 AdventureWorks 示例数据库</span><span class="sxs-lookup"><span data-stu-id="1aa63-106">Get the AdventureWorks sample database</span></span>

<span data-ttu-id="1aa63-107">从以下 GitHub 存储库下载 AdventureWorks 示例数据库：</span><span class="sxs-lookup"><span data-stu-id="1aa63-107">Download the AdventureWorks sample database from the following GitHub repository:</span></span>

[<span data-ttu-id="1aa63-108">AdventureWorks 示例数据库</span><span class="sxs-lookup"><span data-stu-id="1aa63-108">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="1aa63-109">下载一个数据库备份后 (\*.bak) 文件，将备份还原到的 SQL Server 实例使用 SQL Server Management Studio (SSMS)。</span><span class="sxs-lookup"><span data-stu-id="1aa63-109">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="1aa63-110">请参阅[获取 SQL Server Management Studio](#get_ssms)。</span><span class="sxs-lookup"><span data-stu-id="1aa63-110">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-the-northwind-sample-database"></a><span data-ttu-id="1aa63-111">获取 Northwind 示例数据库</span><span class="sxs-lookup"><span data-stu-id="1aa63-111">Get the Northwind sample database</span></span>

<span data-ttu-id="1aa63-112">从 Microsoft 下载中心中的以下页面下载 Northwind 示例数据库：</span><span class="sxs-lookup"><span data-stu-id="1aa63-112">Download the Northwind sample database from the following page in the Microsoft Download Center:</span></span>

[<span data-ttu-id="1aa63-113">Northwind 和 Pubs 示例数据库</span><span class="sxs-lookup"><span data-stu-id="1aa63-113">Northwind and Pubs Sample Databases</span></span>](https://go.microsoft.com/fwlink?linkid=64296)

<span data-ttu-id="1aa63-114">下载文件后，双击文件以提取数据库和脚本。</span><span class="sxs-lookup"><span data-stu-id="1aa63-114">After the file has downloaded, double-click the file to extract the databases and scripts.</span></span> <span data-ttu-id="1aa63-115">默认情况下，文件安装在文件夹中`<drive>:\SQL Server 2000 Sample Databases`。</span><span class="sxs-lookup"><span data-stu-id="1aa63-115">By default, the files are installed in the folder `<drive>:\SQL Server 2000 Sample Databases`.</span></span>

<span data-ttu-id="1aa63-116">可以使用 Northwind 数据库之前，必须执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="1aa63-116">Before you can use the Northwind database, you have to do one of the following things:</span></span>

- <span data-ttu-id="1aa63-117">通过运行重新创建的 SQL Server 实例上数据库`instnwnd.sql`安装文件夹中的脚本文件。</span><span class="sxs-lookup"><span data-stu-id="1aa63-117">Recreate the database on an instance of SQL Server by running the `instnwnd.sql` script file in the installation folder.</span></span>

- <span data-ttu-id="1aa63-118">附加`northwnd.mdf`与其对应的文件`*.ldf`到的 SQL Server 实例的日志文件。</span><span class="sxs-lookup"><span data-stu-id="1aa63-118">Attach the `northwnd.mdf` file with its corresponding `*.ldf` log file to an instance of SQL Server.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="1aa63-119">获取 SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="1aa63-119">Get SQL Server Express</span></span>

<span data-ttu-id="1aa63-120">SQL Server Express 是免费的入门级版本可以与应用程序重新发布的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="1aa63-120">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="1aa63-121">下载 SQL Server Express 的以下页面：</span><span class="sxs-lookup"><span data-stu-id="1aa63-121">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="1aa63-122">SQL Server Express 版本</span><span class="sxs-lookup"><span data-stu-id="1aa63-122">SQL Server Express Editions</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="1aa63-123">如果您使用的[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)，在社区版和专业和更高版本包括 SQL Server Express LocalDB。</span><span class="sxs-lookup"><span data-stu-id="1aa63-123">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the Community edition as well as the Professional and higher editions.</span></span>  

## <a name="get_ssms"></a> <span data-ttu-id="1aa63-124">获取 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1aa63-124">Get SQL Server Management Studio</span></span>
<span data-ttu-id="1aa63-125">如果你想要查看或修改已下载的数据库，可以使用 SQL Server Management Studio (SSMS)。</span><span class="sxs-lookup"><span data-stu-id="1aa63-125">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="1aa63-126">从以下页面下载 SSMS:</span><span class="sxs-lookup"><span data-stu-id="1aa63-126">Download SSMS from the following page:</span></span>

[<span data-ttu-id="1aa63-127">下载 SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="1aa63-127">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="1aa63-128">您还可以查看和管理 Visual Studio 集成的开发环境 (IDE) 中的数据库。</span><span class="sxs-lookup"><span data-stu-id="1aa63-128">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="1aa63-129">在中[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)，连接到从数据库**SQL Server 对象资源管理器**，或创建到数据库中的数据连接**服务器资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="1aa63-129">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="1aa63-130">打开从这些资源管理器窗格**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="1aa63-130">Open these explorer panes from the **View** menu.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1aa63-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="1aa63-131">See also</span></span>

- [<span data-ttu-id="1aa63-132">入门</span><span class="sxs-lookup"><span data-stu-id="1aa63-132">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
