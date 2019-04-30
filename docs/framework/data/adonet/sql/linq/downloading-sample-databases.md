---
title: 获取示例 SQL Server 数据库的 ADO.NET 代码示例
description: 下载 ADO.NET 文档以及 SQL Server 和管理工具中的代码示例中使用的示例 SQL Server 数据库
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 5580f06f3d28ed6d70f75b619498ac8de7bc3326
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037929"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="3a01b-103">获取示例数据库的 ADO.NET 代码示例</span><span class="sxs-lookup"><span data-stu-id="3a01b-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="3a01b-104">示例和演练中的大量[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档使用示例 SQL Server 数据库和 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="3a01b-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="3a01b-105">可从 Microsoft 下载这些免费的产品。</span><span class="sxs-lookup"><span data-stu-id="3a01b-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="3a01b-106">获取 SQL Server 的 Northwind 示例数据库</span><span class="sxs-lookup"><span data-stu-id="3a01b-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="3a01b-107">下载脚本`instnwnd.sql`从以下 GitHub 存储库，用于创建和加载 SQL Server 的 Northwind 示例数据库：</span><span class="sxs-lookup"><span data-stu-id="3a01b-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="3a01b-108">Microsoft SQL Server 的 Northwind 和 pubs 示例数据库</span><span class="sxs-lookup"><span data-stu-id="3a01b-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="3a01b-109">可以使用 Northwind 数据库之前，必须运行下载`instnwnd.sql`脚本文件以使用重新创建的 SQL Server 实例上的数据库[SQL Server Management Studio](#get_ssms)或类似的工具。</span><span class="sxs-lookup"><span data-stu-id="3a01b-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="3a01b-110">按照存储库中的自述文件中的说明。</span><span class="sxs-lookup"><span data-stu-id="3a01b-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="3a01b-111">如果您正在寻找 Microsoft access Northwind 数据库，请参阅[安装用于 Microsoft Access Northwind 示例数据库](#northwind_access)。</span><span class="sxs-lookup"><span data-stu-id="3a01b-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="northwind_access"></a> <span data-ttu-id="3a01b-112">获取 Microsoft Access Northwind 示例数据库</span><span class="sxs-lookup"><span data-stu-id="3a01b-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="3a01b-113">Microsoft Access Northwind 示例数据库在 Microsoft 下载中心上不可用。</span><span class="sxs-lookup"><span data-stu-id="3a01b-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="3a01b-114">若要安装在 Access 中的直接从 Northwind，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3a01b-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="3a01b-115">打开访问权限。</span><span class="sxs-lookup"><span data-stu-id="3a01b-115">Open Access.</span></span>

1. <span data-ttu-id="3a01b-116">Enter **Northwind**中**搜索联机模板**框，并选择**Enter**。</span><span class="sxs-lookup"><span data-stu-id="3a01b-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="3a01b-117">在结果屏幕上，选择**Northwind**。</span><span class="sxs-lookup"><span data-stu-id="3a01b-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="3a01b-118">使用 Northwind 数据库的说明打开一个新窗口。</span><span class="sxs-lookup"><span data-stu-id="3a01b-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="3a01b-119">在新窗口中，在**文件名**文字框中，Northwind 数据库的副本提供一个文件名。</span><span class="sxs-lookup"><span data-stu-id="3a01b-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="3a01b-120">选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="3a01b-120">Select **Create**.</span></span> <span data-ttu-id="3a01b-121">访问下载 Northwind 数据库，并准备该文件。</span><span class="sxs-lookup"><span data-stu-id="3a01b-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="3a01b-122">此过程完成后，使用欢迎屏幕打开数据库。</span><span class="sxs-lookup"><span data-stu-id="3a01b-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="3a01b-123">获取 AdventureWorks 示例数据库的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a01b-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="3a01b-124">从以下 GitHub 存储库的 SQL server 下载 AdventureWorks 示例数据库：</span><span class="sxs-lookup"><span data-stu-id="3a01b-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="3a01b-125">AdventureWorks 示例数据库</span><span class="sxs-lookup"><span data-stu-id="3a01b-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="3a01b-126">下载一个数据库备份后 (\*.bak) 文件，将备份还原到的 SQL Server 实例使用 SQL Server Management Studio (SSMS)。</span><span class="sxs-lookup"><span data-stu-id="3a01b-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="3a01b-127">请参阅[获取 SQL Server Management Studio](#get_ssms)。</span><span class="sxs-lookup"><span data-stu-id="3a01b-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_ssms"></a> <span data-ttu-id="3a01b-128">获取 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a01b-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="3a01b-129">如果你想要查看或修改已下载的数据库，可以使用 SQL Server Management Studio (SSMS)。</span><span class="sxs-lookup"><span data-stu-id="3a01b-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="3a01b-130">从以下页面下载 SSMS:</span><span class="sxs-lookup"><span data-stu-id="3a01b-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="3a01b-131">下载 SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="3a01b-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="3a01b-132">您还可以查看和管理 Visual Studio 集成的开发环境 (IDE) 中的数据库。</span><span class="sxs-lookup"><span data-stu-id="3a01b-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="3a01b-133">在中[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)，连接到从数据库**SQL Server 对象资源管理器**，或创建到数据库中的数据连接**服务器资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="3a01b-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="3a01b-134">打开从这些资源管理器窗格**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="3a01b-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="3a01b-135">Get SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="3a01b-135">Get SQL Server Express</span></span>

<span data-ttu-id="3a01b-136">SQL Server Express 是免费的入门级版本可以与应用程序重新发布的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="3a01b-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="3a01b-137">下载 SQL Server Express 的以下页面：</span><span class="sxs-lookup"><span data-stu-id="3a01b-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="3a01b-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="3a01b-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="3a01b-139">如果您使用的[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)，在 Visual Studio 的免费的社区版和专业和更高版本包括 SQL Server Express LocalDB。</span><span class="sxs-lookup"><span data-stu-id="3a01b-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3a01b-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a01b-140">See also</span></span>

- [<span data-ttu-id="3a01b-141">入门</span><span class="sxs-lookup"><span data-stu-id="3a01b-141">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
