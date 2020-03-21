---
title: 获取ADO.NET代码示例的示例 SQL Server 数据库
description: 下载ADO.NET文档中代码示例中使用的示例 SQL Server 数据库，以及 SQL Server 和管理工具
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 19d659cbe8f39d27b71dc59c738355f12fce92a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148382"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="1e616-103">获取ADO.NET代码示例的示例数据库</span><span class="sxs-lookup"><span data-stu-id="1e616-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="1e616-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档中的一些示例和演练使用示例 SQL Server 数据库和 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="1e616-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="1e616-105">你可以从微软免费下载这些产品。</span><span class="sxs-lookup"><span data-stu-id="1e616-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="1e616-106">获取 SQL Server 的北风示例数据库</span><span class="sxs-lookup"><span data-stu-id="1e616-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="1e616-107">从以下`instnwnd.sql`GitHub 存储库下载脚本，以创建并加载 SQL Server 的北风示例数据库：</span><span class="sxs-lookup"><span data-stu-id="1e616-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="1e616-108">Northwind 和 pubs 示例数据库为 Microsoft SQL 服务器</span><span class="sxs-lookup"><span data-stu-id="1e616-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="1e616-109">在使用 Northwind 数据库之前，必须运行下载的`instnwnd.sql`脚本文件，以便使用 SQL Server[管理工作室](#get_ssms)或类似工具在 SQL Server 实例上重新创建数据库。</span><span class="sxs-lookup"><span data-stu-id="1e616-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="1e616-110">按照存储库中的 Readme 文件中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="1e616-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="1e616-111">如果您正在寻找适用于 Microsoft Access 的北风数据库，请参阅[安装 Microsoft Access 的北风示例数据库](#northwind_access)。</span><span class="sxs-lookup"><span data-stu-id="1e616-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a><span data-ttu-id="1e616-112">获取适用于 Microsoft 访问的北风示例数据库</span><span class="sxs-lookup"><span data-stu-id="1e616-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="1e616-113">微软访问的北风示例数据库在 Microsoft 下载中心不可用。</span><span class="sxs-lookup"><span data-stu-id="1e616-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="1e616-114">要直接从 Access 内部安装北风，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1e616-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="1e616-115">打开访问。</span><span class="sxs-lookup"><span data-stu-id="1e616-115">Open Access.</span></span>

1. <span data-ttu-id="1e616-116">在 **"搜索联机模板"** 框中输入**北风**，然后选择"**输入**"。</span><span class="sxs-lookup"><span data-stu-id="1e616-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="1e616-117">在结果屏幕上，选择**北风**。</span><span class="sxs-lookup"><span data-stu-id="1e616-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="1e616-118">将打开一个新窗口，其中说明北风数据库。</span><span class="sxs-lookup"><span data-stu-id="1e616-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="1e616-119">在新窗口中，在 **"文件名**"文本框中，为北风数据库的副本提供文件名。</span><span class="sxs-lookup"><span data-stu-id="1e616-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="1e616-120">选择 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="1e616-120">Select **Create**.</span></span> <span data-ttu-id="1e616-121">访问下载北风数据库并准备文件。</span><span class="sxs-lookup"><span data-stu-id="1e616-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="1e616-122">此过程完成后，数据库将打开，并带有"欢迎"屏幕。</span><span class="sxs-lookup"><span data-stu-id="1e616-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="1e616-123">获取 SQL Server 的 AdventureWorks 示例数据库</span><span class="sxs-lookup"><span data-stu-id="1e616-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="1e616-124">从以下 GitHub 存储库下载 SQL Server 的 AdventureWorks 示例数据库：</span><span class="sxs-lookup"><span data-stu-id="1e616-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

<span data-ttu-id="1e616-125">[AdventureWorks sample databases](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)（AdventureWorks 示例数据库）</span><span class="sxs-lookup"><span data-stu-id="1e616-125">[AdventureWorks sample databases](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)</span></span>

<span data-ttu-id="1e616-126">下载其中一个数据库备份 （.bak）\*文件后，请使用 SQL Server 管理工作室 （SSMS） 将备份还原到 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="1e616-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="1e616-127">请参阅[获取 SQL 服务器管理工作室](#get_ssms)。</span><span class="sxs-lookup"><span data-stu-id="1e616-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a><span data-ttu-id="1e616-128">获取 SQL 服务器管理工作室</span><span class="sxs-lookup"><span data-stu-id="1e616-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="1e616-129">如果要查看或修改已下载的数据库，可以使用 SQL 服务器管理工作室 （SSMS）。</span><span class="sxs-lookup"><span data-stu-id="1e616-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="1e616-130">从以下页面下载 SSMS：</span><span class="sxs-lookup"><span data-stu-id="1e616-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="1e616-131">下载 SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="1e616-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="1e616-132">您还可以在可视化工作室集成开发环境 （IDE） 中查看和管理数据库。</span><span class="sxs-lookup"><span data-stu-id="1e616-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="1e616-133">在[可视化工作室](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)中，从 SQL**服务器对象资源管理器**连接到数据库，或在**服务器资源管理器**中创建到数据库的数据连接。</span><span class="sxs-lookup"><span data-stu-id="1e616-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="1e616-134">从 **"视图"** 菜单打开这些资源管理器窗格。</span><span class="sxs-lookup"><span data-stu-id="1e616-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a><span data-ttu-id="1e616-135">获取 SQL 服务器快速</span><span class="sxs-lookup"><span data-stu-id="1e616-135">Get SQL Server Express</span></span>

<span data-ttu-id="1e616-136">SQL Server Express 是一个免费的入门级 SQL Server 版本，您可以使用应用程序重新分发。</span><span class="sxs-lookup"><span data-stu-id="1e616-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="1e616-137">从以下页面下载 SQL 服务器快速服务：</span><span class="sxs-lookup"><span data-stu-id="1e616-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="1e616-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="1e616-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="1e616-139">如果您使用的是[Visual Studio，SQL](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)Server Express 本地DB 包含在 Visual Studio 的免费社区版以及专业版和更高版本中。</span><span class="sxs-lookup"><span data-stu-id="1e616-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1e616-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e616-140">See also</span></span>

- [<span data-ttu-id="1e616-141">入门</span><span class="sxs-lookup"><span data-stu-id="1e616-141">Getting Started</span></span>](getting-started.md)
