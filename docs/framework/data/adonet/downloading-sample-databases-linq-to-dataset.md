---
title: "下载示例数据库 (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6450e683f51abe0bdd4eb7f45089f04d11660d5d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>下载示例数据库 (LINQ to DataSet)
示例和演练[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]文档使用 AdventureWorks 示例数据库。 您可以从 Microsoft 下载站点免费下载此产品。 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 文档中的示例和演练使用 SQL Server 作为数据存储区。 免费提供的 SQL Server Express Edition 也可代替 SQL Server 用作数据存储区。  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>下载并安装 AdventureWorks 数据库  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>下载和安装适用于 SQL Server 的 AdventureWorks 示例数据库  
  
1.  打开 Internet Explorer。  
  
2.  转到[SQL Server 2005 示例和示例数据库](http://go.microsoft.com/fwlink/?linkid=31046)Web 站点。  
  
3.  按照说明下载适用于您的处理器类型的 AdventureWorks 示例数据库（如 AdventureWorksDB.msi）并将该 .MSI 文件保存到您的本地计算机。  
  
4.  如果您通过下载或在 SQL Server 安装过程中安装了先前版本的 AdventureWorks，则在运行 AdventureWorks.msi 之前必须删除该版本。  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>删除先前下载的 AdventureWorks 示例数据库  
  
1.  放置 AdventureWorks 或 AdventureWorksDW 数据库。  
  
2.  从**添加或删除程序**，选择**AdventureWorksDB**或**AdventureWorksBI**单击**删除**。  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>删除先前使用安装程序安装的 AdventureWorks 示例数据库  
  
1.  放置 AdventureWorks 或 AdventureWorksDW 数据库。  
  
2.  从**添加或删除程序**，选择**Microsoft SQL Server 2005**单击**更改**。  
  
3.  从**组件选择**，选择**工作站组件**，然后单击**下一步**。  
  
4.  从**欢迎使用 SQL Server 安装向导**，单击**下一步**。  
  
5.  从**系统配置检查**，单击**下一步**。  
  
6.  从**更改或删除实例**，单击**更改已安装的组件**。  
  
7.  从**功能选择**，展开**文档、 示例和示例数据库**节点。  
  
8.  选择**示例代码和应用程序**。 展开**示例数据库**，选择示例数据库中删除，然后选择**整个功能将不可**。 单击 **“下一步”**。  
  
9. 单击**安装**并完成安装向导。  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>将 AdventureWorks 示例数据库文件附加到 SQL Server 的实例  
  
1.  已下载文件示例数据库安装程序文件后，双击**AdventureWorksDB.msi**文件 （或你下载的文件） 来安装数据库。 默认情况下，该数据库安装在 c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data 位置。  
  
2.  通过执行下面的脚本 SQLCMD 或 SQL Server Management Studio，将 AdventureWorks 数据库文件附加到 SQL Server 的实例：  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     如果您已将这些文件安装到其他驱动器或目录，则必须在执行 `sp_attach_db` 存储过程之前适当修改路径。  
  
## <a name="downloading-sql-server-express-edition"></a>下载 SQL Server Express Edition  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 一节中的示例和演练使用 SQL Server 2005 作为数据存储区，但也可以修改为使用 SQL Server Express Edition。 SQL Server Express Edition 免费提供，您可以利用应用程序重新发布它。 如果您要使用 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]，则 Pro 和更高的版本将会包括 SQL Server Express Edition。  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>下载并安装 SQL Server Express Edition  
  
1.  启动 Internet Explorer。  
  
2.  转到[Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070)下载页。  
  
3.  按照网站上的安装说明操作。  
  
## <a name="see-also"></a>另请参阅  
 [入门](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
