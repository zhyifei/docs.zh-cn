---
title: SqlClient 对 LocalDB 的支持
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 1ef75def3f3de44b5e23cb1197a4410dcf6b547f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532704"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="f70dd-102">SqlClient 对 LocalDB 的支持</span><span class="sxs-lookup"><span data-stu-id="f70dd-102">SqlClient Support for LocalDB</span></span>
<span data-ttu-id="f70dd-103">从 SQL Server 代号 Denali，SQL Server 的称作 LocalDB 的轻量版本将提供。</span><span class="sxs-lookup"><span data-stu-id="f70dd-103">Beginning in SQL Server code name Denali, a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="f70dd-104">本主题讨论如何连接到 LocalDB 数据库。</span><span class="sxs-lookup"><span data-stu-id="f70dd-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f70dd-105">备注</span><span class="sxs-lookup"><span data-stu-id="f70dd-105">Remarks</span></span>  
 <span data-ttu-id="f70dd-106">有关 LocalDB 的详细信息，包括如何安装 LocalDB 和配置 LocalDB 实例，请参阅 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="f70dd-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="f70dd-107">以下汇总了使用 LocalDB 可以执行的操作：</span><span class="sxs-lookup"><span data-stu-id="f70dd-107">To summarize what you can do with LocalDB:</span></span>  
  
-   <span data-ttu-id="f70dd-108">使用 sqllocaldb.exe 或 app.config 文件创建和启动 LocalDB 实例。</span><span class="sxs-lookup"><span data-stu-id="f70dd-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
-   <span data-ttu-id="f70dd-109">使用 sqlcmd.exe 添加和修改 LocalDB 实例中的数据库。</span><span class="sxs-lookup"><span data-stu-id="f70dd-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="f70dd-110">例如 `sqlcmd -S (localdb)\myinst`。</span><span class="sxs-lookup"><span data-stu-id="f70dd-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
-   <span data-ttu-id="f70dd-111">使用 `AttachDBFilename` 连接字符串关键字将数据库添加到 LocalDB 实例。</span><span class="sxs-lookup"><span data-stu-id="f70dd-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="f70dd-112">使用 `AttachDBFilename`时，如果不使用 `Database` 连接字符串关键字指定数据库的名称，则在应用程序关闭时，将从 LocalDB 实例中删除数据库。</span><span class="sxs-lookup"><span data-stu-id="f70dd-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="f70dd-113">在连接字符串中指定 LocalDB 实例。</span><span class="sxs-lookup"><span data-stu-id="f70dd-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="f70dd-114">例如，如果实例名称是 `myInstance`，连接字符串将包括：</span><span class="sxs-lookup"><span data-stu-id="f70dd-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 <span data-ttu-id="f70dd-115">连接到 LocalDB 数据库时，不允许`User Instance=True` 。</span><span class="sxs-lookup"><span data-stu-id="f70dd-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="f70dd-116">您可以下载从 LocalDB [Microsoft SQL Server 2012 功能包](https://www.microsoft.com/download/en/details.aspx?id=29065)。</span><span class="sxs-lookup"><span data-stu-id="f70dd-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="f70dd-117">如果将使用 sqlcmd.exe 来修改 LocalDB 实例中的数据，则需要 SQL Server 2012，您还可以从 SQL Server 2012 功能包中的 sqlcmd。</span><span class="sxs-lookup"><span data-stu-id="f70dd-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from SQL Server 2012, which you can also get from the SQL Server 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="f70dd-118">以编程方式创建命名实例</span><span class="sxs-lookup"><span data-stu-id="f70dd-118">Programmatically Create a Named Instance</span></span>  
 <span data-ttu-id="f70dd-119">应用程序可以创建命名实例并指定数据库，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f70dd-119">An application can create a named instance and specify a database as follows:</span></span>  
  
-   <span data-ttu-id="f70dd-120">在 app.config 文件中指定要创建的 LocalDB 实例，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f70dd-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="f70dd-121">实例版本号应与 LocalDB 安装的版本号相同。</span><span class="sxs-lookup"><span data-stu-id="f70dd-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="f70dd-122">使用 `server` 连接字符串关键字指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="f70dd-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="f70dd-123">`server` 连接字符串关键字中指定的实例名称必须与 app.config 文件中指定的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="f70dd-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
-   <span data-ttu-id="f70dd-124">使用 `AttachDBFilename` 连接字符串关键字来指定 .MDF 文件。</span><span class="sxs-lookup"><span data-stu-id="f70dd-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70dd-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f70dd-125">See Also</span></span>  
 [<span data-ttu-id="f70dd-126">SQL Server 功能和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f70dd-126">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [<span data-ttu-id="f70dd-127">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="f70dd-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
