---
title: 连接事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: c1ef9ff9cc4d77e4951e99ed74c96cf78eb71506
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465520"
---
# <a name="connection-events"></a><span data-ttu-id="b334b-102">连接事件</span><span class="sxs-lookup"><span data-stu-id="b334b-102">Connection Events</span></span>
<span data-ttu-id="b334b-103">所有.NET Framework 数据提供程序都具有**连接**若要从数据源中检索信息性消息，或若要确定是否可以使用的两个事件的对象的状态**连接**具有更改。</span><span class="sxs-lookup"><span data-stu-id="b334b-103">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="b334b-104">下表描述的事件**连接**对象。</span><span class="sxs-lookup"><span data-stu-id="b334b-104">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="b334b-105">事件</span><span class="sxs-lookup"><span data-stu-id="b334b-105">Event</span></span>|<span data-ttu-id="b334b-106">描述</span><span class="sxs-lookup"><span data-stu-id="b334b-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b334b-107">**InfoMessage**</span><span class="sxs-lookup"><span data-stu-id="b334b-107">**InfoMessage**</span></span>|<span data-ttu-id="b334b-108">当从数据源中返回信息性消息时发生。</span><span class="sxs-lookup"><span data-stu-id="b334b-108">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="b334b-109">信息性消息是数据源中不会引发异常的消息。</span><span class="sxs-lookup"><span data-stu-id="b334b-109">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|<span data-ttu-id="b334b-110">**StateChange**</span><span class="sxs-lookup"><span data-stu-id="b334b-110">**StateChange**</span></span>|<span data-ttu-id="b334b-111">发生时的状态**连接**更改。</span><span class="sxs-lookup"><span data-stu-id="b334b-111">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="b334b-112">使用 InfoMessage 事件</span><span class="sxs-lookup"><span data-stu-id="b334b-112">Working with the InfoMessage Event</span></span>  
 <span data-ttu-id="b334b-113">您可以使用 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 对象的 <xref:System.Data.SqlClient.SqlConnection> 事件从 SQL Server 数据源中检索警告和信息性消息。</span><span class="sxs-lookup"><span data-stu-id="b334b-113">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="b334b-114">从数据源返回的严重程度为 11 到 16 的错误将引发异常。</span><span class="sxs-lookup"><span data-stu-id="b334b-114">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="b334b-115">但是，<xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件可用于从数据源中获取与错误无关联的消息。</span><span class="sxs-lookup"><span data-stu-id="b334b-115">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="b334b-116">对于 Microsoft SQL Server，任何严重程度等于或小于 10 的错误都将被视为信息性消息，将使用 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件来捕获。</span><span class="sxs-lookup"><span data-stu-id="b334b-116">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="b334b-117">有关详细信息，请参阅[数据库引擎错误严重性](/sql/relational-databases/errors-events/database-engine-error-severities)一文。</span><span class="sxs-lookup"><span data-stu-id="b334b-117">For more information, see the [Database Engine Error Severities](/sql/relational-databases/errors-events/database-engine-error-severities) article.</span></span>
  
 <span data-ttu-id="b334b-118"><xref:System.Data.SqlClient.SqlConnection.InfoMessage>事件接收<xref:System.Data.SqlClient.SqlInfoMessageEventArgs>对象包含其**错误**属性、 数据源的消息的集合。</span><span class="sxs-lookup"><span data-stu-id="b334b-118">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="b334b-119">您可以查询**错误**此集合中的错误号和消息文本以及错误的源中的对象。</span><span class="sxs-lookup"><span data-stu-id="b334b-119">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="b334b-120">SQL Server .NET Framework 数据提供程序还包含有关消息所来自的数据库、存储过程和行号的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b334b-120">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="b334b-121">示例</span><span class="sxs-lookup"><span data-stu-id="b334b-121">Example</span></span>  
 <span data-ttu-id="b334b-122">以下代码示例显示如何为 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b334b-122">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
```vb  
' Assumes that connection represents a SqlConnection object.  
  AddHandler connection.InfoMessage, _  
    New SqlInfoMessageEventHandler(AddressOf OnInfoMessage)  
  
Private Shared Sub OnInfoMessage(sender As Object, _  
  args As SqlInfoMessageEventArgs)  
  Dim err As SqlError  
  For Each err In args.Errors  
    Console.WriteLine("The {0} has received a severity {1}, _  
       state {2} error number {3}\n" & _  
      "on line {4} of procedure {5} on server {6}:\n{7}", _  
      err.Source, err.Class, err.State, err.Number, err.LineNumber, _  
    err.Procedure, err.Server, err.Message)  
  Next  
End Sub  
```  
  
```csharp  
// Assumes that connection represents a SqlConnection object.  
  connection.InfoMessage +=   
    new SqlInfoMessageEventHandler(OnInfoMessage);  
  
protected static void OnInfoMessage(  
  object sender, SqlInfoMessageEventArgs args)  
{  
  foreach (SqlError err in args.Errors)  
  {  
    Console.WriteLine(  
  "The {0} has received a severity {1}, state {2} error number {3}\n" +  
  "on line {4} of procedure {5} on server {6}:\n{7}",  
   err.Source, err.Class, err.State, err.Number, err.LineNumber,   
   err.Procedure, err.Server, err.Message);  
  }  
}  
```  
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="b334b-123">将错误作为信息性消息处理</span><span class="sxs-lookup"><span data-stu-id="b334b-123">Handling Errors as InfoMessages</span></span>  
 <span data-ttu-id="b334b-124">通常，只有从服务器发出的信息性消息和警告消息才会触发 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件。</span><span class="sxs-lookup"><span data-stu-id="b334b-124">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="b334b-125">但是，实际发生错误时，执行**ExecuteNonQuery**或**ExecuteReader**启动服务器操作的方法将暂停和引发异常。</span><span class="sxs-lookup"><span data-stu-id="b334b-125">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="b334b-126">如果无论服务器生成任何错误都要继续处理命令中的语句的其他部分，请将 <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> 的 <xref:System.Data.SqlClient.SqlConnection> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b334b-126">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="b334b-127">这样做会使连接对错误触发 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件，而不是引发异常并中断处理。</span><span class="sxs-lookup"><span data-stu-id="b334b-127">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="b334b-128">客户端应用程序可以处理此事件并对错误情况做出响应。</span><span class="sxs-lookup"><span data-stu-id="b334b-128">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b334b-129">严重程度等于或大于 17 的错误会造成服务器停止处理命令，这种错误必须作为异常来处理。</span><span class="sxs-lookup"><span data-stu-id="b334b-129">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="b334b-130">在这种情况下，无论如何在 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件中处理该错误，都会引发异常。</span><span class="sxs-lookup"><span data-stu-id="b334b-130">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="b334b-131">使用 StateChange 事件</span><span class="sxs-lookup"><span data-stu-id="b334b-131">Working with the StateChange Event</span></span>  
 <span data-ttu-id="b334b-132">**StateChange**事件发生时的状态**连接**更改。</span><span class="sxs-lookup"><span data-stu-id="b334b-132">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="b334b-133">**StateChange**事件接收<xref:System.Data.StateChangeEventArgs>，可以确定状态的改变**连接**通过**OriginalState**和**CurrentState**属性。</span><span class="sxs-lookup"><span data-stu-id="b334b-133">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="b334b-134">**OriginalState**属性是<xref:System.Data.ConnectionState>枚举，指示的状态**连接**改变前。</span><span class="sxs-lookup"><span data-stu-id="b334b-134">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="b334b-135">**CurrentState**是<xref:System.Data.ConnectionState>枚举，指示的状态**连接**改变后。</span><span class="sxs-lookup"><span data-stu-id="b334b-135">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="b334b-136">下面的代码示例使用**StateChange**事件向控制台写入一条消息时的状态**连接**更改。</span><span class="sxs-lookup"><span data-stu-id="b334b-136">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
```vb  
' Assumes connection represents a SqlConnection object.  
  AddHandler connection.StateChange, _  
    New StateChangeEventHandler(AddressOf OnStateChange)  
  
Protected Shared Sub OnStateChange( _  
  sender As Object, args As StateChangeEventArgs)  
  
  Console.WriteLine( _  
  "The current Connection state has changed from {0} to {1}.", _  
  args.OriginalState, args.CurrentState)  
End Sub  
```  
  
```csharp  
// Assumes connection represents a SqlConnection object.  
  connection.StateChange  += new StateChangeEventHandler(OnStateChange);  
  
protected static void OnStateChange(object sender,   
  StateChangeEventArgs args)  
{  
  Console.WriteLine(  
    "The current Connection state has changed from {0} to {1}.",  
      args.OriginalState, args.CurrentState);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b334b-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="b334b-137">See Also</span></span>  
 [<span data-ttu-id="b334b-138">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="b334b-138">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="b334b-139">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="b334b-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
