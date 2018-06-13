---
title: 下载示例数据库 (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: f2488b0e1bfc578679a2a2802c332439f374a341
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763048"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a><span data-ttu-id="81167-102">下载示例数据库 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="81167-102">Downloading Sample Databases (LINQ to DataSet)</span></span>
<span data-ttu-id="81167-103">示例和演练[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]文档使用 AdventureWorks 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="81167-103">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use the AdventureWorks sample database.</span></span> <span data-ttu-id="81167-104">您可以从 Microsoft 下载站点免费下载此产品。</span><span class="sxs-lookup"><span data-stu-id="81167-104">You can download this product free of charge from the Microsoft download site.</span></span> <span data-ttu-id="81167-105">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 文档中的示例和演练使用 SQL Server 作为数据存储区。</span><span class="sxs-lookup"><span data-stu-id="81167-105">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use SQL Server as the data store.</span></span> <span data-ttu-id="81167-106">免费提供的 SQL Server Express Edition 也可代替 SQL Server 用作数据存储区。</span><span class="sxs-lookup"><span data-stu-id="81167-106">SQL Server Express Edition, which is available without charge, can also be used as the data store instead of SQL Server.</span></span>  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a><span data-ttu-id="81167-107">下载并安装 AdventureWorks 数据库</span><span class="sxs-lookup"><span data-stu-id="81167-107">Downloading and Installing the AdventureWorks Database</span></span>  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="81167-108">下载和安装适用于 SQL Server 的 AdventureWorks 示例数据库</span><span class="sxs-lookup"><span data-stu-id="81167-108">To download and install the AdventureWorks sample database for SQL Server</span></span>  
  
1.  <span data-ttu-id="81167-109">打开 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="81167-109">Open Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="81167-110">转到[SQL Server 2005 示例和示例数据库](http://go.microsoft.com/fwlink/?linkid=31046)Web 站点。</span><span class="sxs-lookup"><span data-stu-id="81167-110">Go to the [SQL Server 2005 Samples and Sample Databases](http://go.microsoft.com/fwlink/?linkid=31046) Web site.</span></span>  
  
3.  <span data-ttu-id="81167-111">按照说明下载适用于您的处理器类型的 AdventureWorks 示例数据库（如 AdventureWorksDB.msi）并将该 .MSI 文件保存到您的本地计算机。</span><span class="sxs-lookup"><span data-stu-id="81167-111">Follow the instructions for downloading the AdventureWorks sample database for your processor type (such as AdventureWorksDB.msi), and save the .MSI file to your local computer.</span></span>  
  
4.  <span data-ttu-id="81167-112">如果您通过下载或在 SQL Server 安装过程中安装了先前版本的 AdventureWorks，则在运行 AdventureWorks.msi 之前必须删除该版本。</span><span class="sxs-lookup"><span data-stu-id="81167-112">If you have a previous version of AdventureWorks installed from the download or during the SQL Server setup, you must remove it before running AdventureWorks.msi.</span></span>  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a><span data-ttu-id="81167-113">删除先前下载的 AdventureWorks 示例数据库</span><span class="sxs-lookup"><span data-stu-id="81167-113">To remove a previous download of an AdventureWorks sample database</span></span>  
  
1.  <span data-ttu-id="81167-114">放置 AdventureWorks 或 AdventureWorksDW 数据库。</span><span class="sxs-lookup"><span data-stu-id="81167-114">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2.  <span data-ttu-id="81167-115">从**添加或删除程序**，选择**AdventureWorksDB**或**AdventureWorksBI**单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="81167-115">From **Add or Remove Programs**, select **AdventureWorksDB** or **AdventureWorksBI** and click **Remove**.</span></span>  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a><span data-ttu-id="81167-116">删除先前使用安装程序安装的 AdventureWorks 示例数据库</span><span class="sxs-lookup"><span data-stu-id="81167-116">To remove an AdventureWorks sample database previously installed using Setup</span></span>  
  
1.  <span data-ttu-id="81167-117">放置 AdventureWorks 或 AdventureWorksDW 数据库。</span><span class="sxs-lookup"><span data-stu-id="81167-117">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2.  <span data-ttu-id="81167-118">从**添加或删除程序**，选择**Microsoft SQL Server 2005**单击**更改**。</span><span class="sxs-lookup"><span data-stu-id="81167-118">From **Add or Remove Programs**, select **Microsoft SQL Server 2005** and click **Change**.</span></span>  
  
3.  <span data-ttu-id="81167-119">从**组件选择**，选择**工作站组件**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81167-119">From **Component Selection**, select **Workstation Components** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="81167-120">从**欢迎使用 SQL Server 安装向导**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81167-120">From **Welcome to the SQL Server Installation Wizard**, click **Next**.</span></span>  
  
5.  <span data-ttu-id="81167-121">从**系统配置检查**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="81167-121">From **System Configuration Check**, click **Next**.</span></span>  
  
6.  <span data-ttu-id="81167-122">从**更改或删除实例**，单击**更改已安装的组件**。</span><span class="sxs-lookup"><span data-stu-id="81167-122">From **Change or Remove Instance**, click **Change Installed Components**.</span></span>  
  
7.  <span data-ttu-id="81167-123">从**功能选择**，展开**文档、 示例和示例数据库**节点。</span><span class="sxs-lookup"><span data-stu-id="81167-123">From **Feature Selection**, expand the **Documentation, Samples, and Sample Databases** node.</span></span>  
  
8.  <span data-ttu-id="81167-124">选择**示例代码和应用程序**。</span><span class="sxs-lookup"><span data-stu-id="81167-124">Select **Sample Code and Applications**.</span></span> <span data-ttu-id="81167-125">展开**示例数据库**，选择示例数据库中删除，然后选择**整个功能将不可**。</span><span class="sxs-lookup"><span data-stu-id="81167-125">Expand **Sample Databases**, select the sample database to be removed, and select **Entire feature will be unavailable**.</span></span> <span data-ttu-id="81167-126">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="81167-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="81167-127">单击**安装**并完成安装向导。</span><span class="sxs-lookup"><span data-stu-id="81167-127">Click **Install** and finish the installation wizard.</span></span>  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a><span data-ttu-id="81167-128">将 AdventureWorks 示例数据库文件附加到 SQL Server 的实例</span><span class="sxs-lookup"><span data-stu-id="81167-128">To attach the AdventureWorks sample database files to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="81167-129">已下载文件示例数据库安装程序文件后，双击**AdventureWorksDB.msi**文件 （或你下载的文件） 来安装数据库。</span><span class="sxs-lookup"><span data-stu-id="81167-129">After the file sample database installer file has downloaded, double-click the **AdventureWorksDB.msi** file (or the file you downloaded) to install the database.</span></span> <span data-ttu-id="81167-130">默认情况下，该数据库安装在 c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data 位置。</span><span class="sxs-lookup"><span data-stu-id="81167-130">By default, the database is installed at c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="81167-131">通过执行下面的脚本 SQLCMD 或 SQL Server Management Studio，将 AdventureWorks 数据库文件附加到 SQL Server 的实例：</span><span class="sxs-lookup"><span data-stu-id="81167-131">Attach the AdventureWorks database files to an instance of SQL Server by executing the following script SQLCMD or SQL Server Management Studio:</span></span>  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     <span data-ttu-id="81167-132">如果您已将这些文件安装到其他驱动器或目录，则必须在执行 `sp_attach_db` 存储过程之前适当修改路径。</span><span class="sxs-lookup"><span data-stu-id="81167-132">If you have installed these files to a different drive or directory, you must revise the paths appropriately before you execute the `sp_attach_db` stored procedure.</span></span>  
  
## <a name="downloading-sql-server-express-edition"></a><span data-ttu-id="81167-133">下载 SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="81167-133">Downloading SQL Server Express Edition</span></span>  
 <span data-ttu-id="81167-134">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 一节中的示例和演练使用 SQL Server 2005 作为数据存储区，但也可以修改为使用 SQL Server Express Edition。</span><span class="sxs-lookup"><span data-stu-id="81167-134">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] section use SQL Server 2005 as the data store but can be modified to use SQL Server Express Edition, instead.</span></span> <span data-ttu-id="81167-135">SQL Server Express Edition 免费提供，您可以利用应用程序重新发布它。</span><span class="sxs-lookup"><span data-stu-id="81167-135">SQL Server Express Edition is available without charge, and you can redistribute it with applications.</span></span> <span data-ttu-id="81167-136">如果你使用的 Visual Studio，Pro 和更高版本中包含 SQL Server Express Edition。</span><span class="sxs-lookup"><span data-stu-id="81167-136">If you are using Visual Studio, SQL Server Express Edition is included in the Pro and higher editions.</span></span>  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a><span data-ttu-id="81167-137">下载并安装 SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="81167-137">To download and install SQL Server Express Edition</span></span>  
  
1.  <span data-ttu-id="81167-138">启动 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="81167-138">Start Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="81167-139">转到[Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070)下载页。</span><span class="sxs-lookup"><span data-stu-id="81167-139">Go to the  [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) download page.</span></span>  
  
3.  <span data-ttu-id="81167-140">按照网站上的安装说明操作。</span><span class="sxs-lookup"><span data-stu-id="81167-140">Follow the installation instructions on the Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81167-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="81167-141">See Also</span></span>  
 [<span data-ttu-id="81167-142">入门</span><span class="sxs-lookup"><span data-stu-id="81167-142">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
