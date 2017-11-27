---
title: "使用 SqlDependency 检测更改"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3fe5aca218da7c862be90645e6fa73bc628b2328
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="41c2d-102">使用 SqlDependency 检测更改</span><span class="sxs-lookup"><span data-stu-id="41c2d-102">Detecting Changes with SqlDependency</span></span>
<span data-ttu-id="41c2d-103"><xref:System.Data.SqlClient.SqlDependency> 对象可以与 <xref:System.Data.SqlClient.SqlCommand> 关联，以便检测查询结果何时与最初检索的结果不同。</span><span class="sxs-lookup"><span data-stu-id="41c2d-103">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="41c2d-104">也可以向 `OnChange` 事件分配一个委托，当关联命令的结果更改时，将会触发该委托。</span><span class="sxs-lookup"><span data-stu-id="41c2d-104">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="41c2d-105">在执行命令前，必须将 <xref:System.Data.SqlClient.SqlDependency> 与该命令关联。</span><span class="sxs-lookup"><span data-stu-id="41c2d-105">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="41c2d-106">也可以使用 `HasChanges` 的 <xref:System.Data.SqlClient.SqlDependency> 属性来确定自从首次检索数据以来查询结果是否已经更改。</span><span class="sxs-lookup"><span data-stu-id="41c2d-106">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>  
  
## <a name="security-considerations"></a><span data-ttu-id="41c2d-107">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="41c2d-107">Security Considerations</span></span>  
 <span data-ttu-id="41c2d-108">依赖项基础结构依赖于 <xref:System.Data.SqlClient.SqlConnection>，它会在调用 <xref:System.Data.SqlClient.SqlDependency.Start%2A> 时打开，以便接收有关给定命令的基础数据已经更改的通知。</span><span class="sxs-lookup"><span data-stu-id="41c2d-108">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="41c2d-109">客户端启动对 `SqlDependency.Start` 的调用的能力是通过使用 <xref:System.Data.SqlClient.SqlClientPermission> 和代码访问安全性属性来控制的。</span><span class="sxs-lookup"><span data-stu-id="41c2d-109">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="41c2d-110">有关详细信息，请参阅[启用查询通知](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)和[代码访问安全性和 ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)。</span><span class="sxs-lookup"><span data-stu-id="41c2d-110">For more information, see [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) and [Code Access Security and ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="41c2d-111">示例</span><span class="sxs-lookup"><span data-stu-id="41c2d-111">Example</span></span>  
 <span data-ttu-id="41c2d-112">下面的步骤演示如何声明依赖项、执行命令和在结果集更改时接收通知：</span><span class="sxs-lookup"><span data-stu-id="41c2d-112">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>  
  
1.  <span data-ttu-id="41c2d-113">启动到服务器的 `SqlDependency` 连接。</span><span class="sxs-lookup"><span data-stu-id="41c2d-113">Initiate a `SqlDependency` connection to the server.</span></span>  
  
2.  <span data-ttu-id="41c2d-114">创建 <xref:System.Data.SqlClient.SqlConnection> 和 <xref:System.Data.SqlClient.SqlCommand> 对象以连接到服务器并定义 Transact-SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="41c2d-114">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>  
  
3.  <span data-ttu-id="41c2d-115">创建一个新的 `SqlDependency` 对象，或使用现有的对象，并将其绑定到 `SqlCommand` 对象。</span><span class="sxs-lookup"><span data-stu-id="41c2d-115">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="41c2d-116">这会在内部创建一个 <xref:System.Data.Sql.SqlNotificationRequest> 对象并根据需要将其绑定到命令对象。</span><span class="sxs-lookup"><span data-stu-id="41c2d-116">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="41c2d-117">此通知请求包含一个内部标识符，可唯一地标识此 `SqlDependency` 对象。</span><span class="sxs-lookup"><span data-stu-id="41c2d-117">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="41c2d-118">如果客户端侦听器尚未处于活动状态，它也将启动客户端侦听器。</span><span class="sxs-lookup"><span data-stu-id="41c2d-118">It also starts the client listener if it is not already active.</span></span>  
  
4.  <span data-ttu-id="41c2d-119">订阅一个针对 `OnChange` 对象的 `SqlDependency` 事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="41c2d-119">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>  
  
5.  <span data-ttu-id="41c2d-120">使用 `Execute` 对象的任一 `SqlCommand` 方法执行该命令。</span><span class="sxs-lookup"><span data-stu-id="41c2d-120">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="41c2d-121">因为该命令绑定到通知对象，所以服务器认识到它必须生成一个通知，并且队列信息将指向相关性队列。</span><span class="sxs-lookup"><span data-stu-id="41c2d-121">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>  
  
6.  <span data-ttu-id="41c2d-122">停止到服务器的 `SqlDependency` 连接。</span><span class="sxs-lookup"><span data-stu-id="41c2d-122">Stop the `SqlDependency` connection to the server.</span></span>  
  
 <span data-ttu-id="41c2d-123">如果任何用户随后更改了基础数据，Microsoft SQL Server 会检测到有针对此更改的挂起通知并发布通知，此通知经过处理后通过调用 `SqlConnection` 而创建的基础 `SqlDependency.Start` 转发到客户端。</span><span class="sxs-lookup"><span data-stu-id="41c2d-123">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="41c2d-124">客户端侦听程序接收无效消息。</span><span class="sxs-lookup"><span data-stu-id="41c2d-124">The client listener receives the invalidation message.</span></span> <span data-ttu-id="41c2d-125">然后客户端侦听器定位关联的 `SqlDependency` 对象并触发 `OnChange` 事件。</span><span class="sxs-lookup"><span data-stu-id="41c2d-125">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>  
  
 <span data-ttu-id="41c2d-126">下面的代码段演示创建示例应用程序所要使用的设计模式。</span><span class="sxs-lookup"><span data-stu-id="41c2d-126">The following code fragment shows the design pattern you would use to create a sample application.</span></span>  
  
```vb  
Sub Initialization()  
    ' Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName)  
End Sub  
  
Sub SomeMethod()   
    ' Assume connection is an open SqlConnection.  
    ' Create a new SqlCommand object.  
    Using command As New SqlCommand( _  
      "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", _  
      connection)  
  
        ' Create a dependency and associate it with the SqlCommand.  
        Dim dependency As New SqlDependency(command)  
        ' Maintain the refence in a class member.  
        ' Subscribe to the SqlDependency event.  
        AddHandler dependency.OnChange, AddressOf OnDependencyChange  
  
        ' Execute the command.  
        Using reader = command.ExecuteReader()  
            ' Process the DataReader.  
        End Using  
    End Using  
End Sub   
  
' Handler method  
Sub OnDependencyChange(ByVal sender As Object, _  
    ByVal e As SqlNotificationEventArgs)   
    ' Handle the event (for example, invalidate this cache entry).  
End Sub  
  
Sub Termination()  
    ' Release the dependency  
    SqlDependency.Stop(connectionString, queueName)  
End Sub  
```  
  
```csharp  
void Initialization()  
{  
    // Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName);  
}  
  
void SomeMethod()  
{  
    // Assume connection is an open SqlConnection.  
  
    // Create a new SqlCommand object.  
    using (SqlCommand command=new SqlCommand(  
        "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers",   
        connection))  
    {  
  
        // Create a dependency and associate it with the SqlCommand.  
        SqlDependency dependency=new SqlDependency(command);  
        // Maintain the refence in a class member.  
  
        // Subscribe to the SqlDependency event.  
        dependency.OnChange+=new  
           OnChangeEventHandler(OnDependencyChange);  
  
        // Execute the command.  
        using (SqlDataReader reader = command.ExecuteReader())  
        {  
            // Process the DataReader.  
        }  
    }  
}  
  
// Handler method  
void OnDependencyChange(object sender,   
   SqlNotificationEventArgs e )  
{  
  // Handle the event (for example, invalidate this cache entry).  
}  
  
void Termination()  
{  
    // Release the dependency.  
    SqlDependency.Stop(connectionString, queueName);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="41c2d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41c2d-127">See Also</span></span>  
 [<span data-ttu-id="41c2d-128">SQL Server 中的查询通知</span><span class="sxs-lookup"><span data-stu-id="41c2d-128">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="41c2d-129">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="41c2d-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
