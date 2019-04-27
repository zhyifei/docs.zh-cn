---
title: 启用查询通知
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: a2227b33c7caacdd04c7bf50082bb0cfab7f3302
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877612"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="1d7c7-102">启用查询通知</span><span class="sxs-lookup"><span data-stu-id="1d7c7-102">Enabling Query Notifications</span></span>
<span data-ttu-id="1d7c7-103">使用查询通知的应用程序有一组通用的需求。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="1d7c7-104">必须正确配置数据源才能支持 SQL 查询通知，并且用户必须具有正确的客户端和服务器端权限。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="1d7c7-105">要使用查询通知，必须符合下列条件：</span><span class="sxs-lookup"><span data-stu-id="1d7c7-105">To use query notifications you must:</span></span>  
  
-   <span data-ttu-id="1d7c7-106">对数据库启用查询通知。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-106">Enable query notifications for your database.</span></span>  
  
-   <span data-ttu-id="1d7c7-107">确保用于连接数据库的用户 ID 具有必要的权限。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
-   <span data-ttu-id="1d7c7-108">使用 <xref:System.Data.SqlClient.SqlCommand> 对象执行有效的 SELECT 语句，包含关联的通知对象 — <xref:System.Data.SqlClient.SqlDependency> 或 <xref:System.Data.Sql.SqlNotificationRequest>。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
-   <span data-ttu-id="1d7c7-109">提供所监视的数据更改时用于处理通知的代码。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="1d7c7-110">查询通知需求</span><span class="sxs-lookup"><span data-stu-id="1d7c7-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="1d7c7-111">仅对满足一系列特定要求的 SELECT 语句支持查询通知。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="1d7c7-112">下表提供指向“SQL Server 联机丛书”中的 Service Broker 和“查询通知”文档的链接。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="1d7c7-113">**SQL Server 文档**</span><span class="sxs-lookup"><span data-stu-id="1d7c7-113">**SQL Server documentation**</span></span>  
  
-   <span data-ttu-id="1d7c7-114">[为通知创建查询](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="1d7c7-114">[Creating a Query for Notification](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
-   <span data-ttu-id="1d7c7-115">[Service Broker 的安全注意事项](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="1d7c7-115">[Security Considerations for Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span></span>  
  
-   <span data-ttu-id="1d7c7-116">[安全和保护 (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="1d7c7-116">[Security and Protection (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span></span>  
  
-   <span data-ttu-id="1d7c7-117">[Notification Services 的安全注意事项](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="1d7c7-117">[Security Considerations for Notifications Services](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span></span>  
  
-   <span data-ttu-id="1d7c7-118">[查询通知权限](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="1d7c7-118">[Query Notification Permissions](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span></span>  
  
-   <span data-ttu-id="1d7c7-119">[Service broker 的国际化注意事项](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="1d7c7-119">[International Considerations for Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span></span>  
  
-   <span data-ttu-id="1d7c7-120">[解决方案设计注意事项 (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="1d7c7-120">[Solution Design Considerations (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span></span>  
  
-   <span data-ttu-id="1d7c7-121">[Service Broker 开发人员信息中心](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="1d7c7-121">[Service Broker Developer InfoCenter](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
-   <span data-ttu-id="1d7c7-122">[开发人员指南 (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="1d7c7-122">[Developer's Guide (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="1d7c7-123">启用查询通知运行示例代码</span><span class="sxs-lookup"><span data-stu-id="1d7c7-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="1d7c7-124">若要上启用 Service Broker **AdventureWorks**数据库使用 SQL Server Management Studio 中，执行以下 TRANSACT-SQL 语句：</span><span class="sxs-lookup"><span data-stu-id="1d7c7-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="1d7c7-125">若要此查询通知示例正确运行，必须在数据库服务器上执行下面的 Transact-SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="1d7c7-126">查询通知权限</span><span class="sxs-lookup"><span data-stu-id="1d7c7-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="1d7c7-127">执行请求通知的命令的用户必须在服务器上具有 SUBSCRIBE QUERY NOTIFICATIONS 数据库权限。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="1d7c7-128">在部分信任情况下运行的客户端代码要求 <xref:System.Data.SqlClient.SqlClientPermission>。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="1d7c7-129">下面的代码创建一个 <xref:System.Data.SqlClient.SqlClientPermission> 对象，将 <xref:System.Security.Permissions.PermissionState> 设置为 <xref:System.Security.Permissions.PermissionState.Unrestricted>。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="1d7c7-130">如果尚未为调用堆栈中的所有高级调用方授予该权限，则 <xref:System.Security.CodeAccessPermission.Demand%2A> 将在运行时强制引发 <xref:System.Security.SecurityException>。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="1d7c7-131">选择通知对象</span><span class="sxs-lookup"><span data-stu-id="1d7c7-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="1d7c7-132">查询通知 API 提供两个用于处理通知的对象：<xref:System.Data.SqlClient.SqlDependency> 和 <xref:System.Data.Sql.SqlNotificationRequest>。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="1d7c7-133">通常情况下，大多数非 ASP.NET 应用程序应使用 <xref:System.Data.SqlClient.SqlDependency> 对象。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="1d7c7-134">ASP.NET 应用程序应使用更高级别的 <xref:System.Web.Caching.SqlCacheDependency>，以便包装 <xref:System.Data.SqlClient.SqlDependency> 并为管理通知和缓存对象提供框架。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="1d7c7-135">使用 SqlDependency</span><span class="sxs-lookup"><span data-stu-id="1d7c7-135">Using SqlDependency</span></span>  
 <span data-ttu-id="1d7c7-136">要使用 <xref:System.Data.SqlClient.SqlDependency>，必须对所使用的 SQL Server 数据库启用 Service Broker，并且用户必须具有接收通知的权限。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="1d7c7-137">Service Broker 对象（例如通知队列）已预定义。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="1d7c7-138">此外，<xref:System.Data.SqlClient.SqlDependency> 会自动启动一个辅助线程以在通知发布到队列中时处理这些通知；它还会分析 Service Broker 消息，将此信息作为事件自变量数据公开。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="1d7c7-139">必须通过调用 <xref:System.Data.SqlClient.SqlDependency> 方法初始化 `Start`，以建立与数据库的相关性。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="1d7c7-140">此方法是静态方法，在为每个所需的数据库连接初始化应用程序期间只需调用一次。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="1d7c7-141">必须在应用程序终止时为执行的每个相关连接调用 `Stop` 方法。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="1d7c7-142">使用 SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="1d7c7-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="1d7c7-143">相对而言，<xref:System.Data.Sql.SqlNotificationRequest> 要求您自己实现整个侦听基础结构。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="1d7c7-144">此外，必须定义队列所支持的所有支持 Service Broker 对象（例如队列、服务和消息类型）。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="1d7c7-145">如果应用程序要求特殊的通知消息或通知行为，或应用程序是更大的服务中介应用程序的一部分，此手动方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="1d7c7-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d7c7-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d7c7-146">See also</span></span>

- [<span data-ttu-id="1d7c7-147">SQL Server 中的查询通知</span><span class="sxs-lookup"><span data-stu-id="1d7c7-147">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [<span data-ttu-id="1d7c7-148">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="1d7c7-148">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
