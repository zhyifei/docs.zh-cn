---
title: 连接事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: a7ad0d4d950da71db0aebca872949fa82669c5c5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151690"
---
# <a name="connection-events"></a><span data-ttu-id="f6e06-102">连接事件</span><span class="sxs-lookup"><span data-stu-id="f6e06-102">Connection Events</span></span>
<span data-ttu-id="f6e06-103">所有 .NET Framework 数据提供程序都有**连接**对象，具有两个事件，可用于从数据源检索信息消息或确定**连接**的状态是否已更改。</span><span class="sxs-lookup"><span data-stu-id="f6e06-103">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="f6e06-104">下表描述了**连接**对象的事件。</span><span class="sxs-lookup"><span data-stu-id="f6e06-104">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="f6e06-105">事件</span><span class="sxs-lookup"><span data-stu-id="f6e06-105">Event</span></span>|<span data-ttu-id="f6e06-106">说明</span><span class="sxs-lookup"><span data-stu-id="f6e06-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f6e06-107">**信息留言**</span><span class="sxs-lookup"><span data-stu-id="f6e06-107">**InfoMessage**</span></span>|<span data-ttu-id="f6e06-108">当从数据源中返回信息性消息时发生。</span><span class="sxs-lookup"><span data-stu-id="f6e06-108">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="f6e06-109">信息性消息是数据源中不会引发异常的消息。</span><span class="sxs-lookup"><span data-stu-id="f6e06-109">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|<span data-ttu-id="f6e06-110">**StateChange**</span><span class="sxs-lookup"><span data-stu-id="f6e06-110">**StateChange**</span></span>|<span data-ttu-id="f6e06-111">当**连接**状态更改时发生。</span><span class="sxs-lookup"><span data-stu-id="f6e06-111">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="f6e06-112">使用 InfoMessage 事件</span><span class="sxs-lookup"><span data-stu-id="f6e06-112">Working with the InfoMessage Event</span></span>  
 <span data-ttu-id="f6e06-113">您可以使用 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 对象的 <xref:System.Data.SqlClient.SqlConnection> 事件从 SQL Server 数据源中检索警告和信息性消息。</span><span class="sxs-lookup"><span data-stu-id="f6e06-113">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="f6e06-114">从数据源返回的严重程度为 11 到 16 的错误将引发异常。</span><span class="sxs-lookup"><span data-stu-id="f6e06-114">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="f6e06-115">但是，<xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件可用于从数据源中获取与错误无关联的消息。</span><span class="sxs-lookup"><span data-stu-id="f6e06-115">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="f6e06-116">对于 Microsoft SQL Server，任何严重程度等于或小于 10 的错误都将被视为信息性消息，将使用 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件来捕获。</span><span class="sxs-lookup"><span data-stu-id="f6e06-116">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="f6e06-117">有关详细信息，请参阅[数据库引擎错误权限](/sql/relational-databases/errors-events/database-engine-error-severities)一文。</span><span class="sxs-lookup"><span data-stu-id="f6e06-117">For more information, see the [Database Engine Error Severities](/sql/relational-databases/errors-events/database-engine-error-severities) article.</span></span>
  
 <span data-ttu-id="f6e06-118">该<xref:System.Data.SqlClient.SqlConnection.InfoMessage>事件接收的对象<xref:System.Data.SqlClient.SqlInfoMessageEventArgs>在其**Errors**属性中包含来自数据源的消息的集合。</span><span class="sxs-lookup"><span data-stu-id="f6e06-118">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="f6e06-119">您可以查询此集合中的**Error**对象以查找错误编号和消息文本以及错误源。</span><span class="sxs-lookup"><span data-stu-id="f6e06-119">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="f6e06-120">SQL Server .NET Framework 数据提供程序还包含有关消息所来自的数据库、存储过程和行号的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6e06-120">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f6e06-121">示例</span><span class="sxs-lookup"><span data-stu-id="f6e06-121">Example</span></span>  
 <span data-ttu-id="f6e06-122">以下代码示例显示如何为 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="f6e06-122">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
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
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="f6e06-123">将错误作为信息性消息处理</span><span class="sxs-lookup"><span data-stu-id="f6e06-123">Handling Errors as InfoMessages</span></span>  
 <span data-ttu-id="f6e06-124">通常，只有从服务器发出的信息性消息和警告消息才会触发 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件。</span><span class="sxs-lookup"><span data-stu-id="f6e06-124">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="f6e06-125">但是，当发生实际错误时，启动服务器操作的执行**NonQuery**或**ExecuteReader**方法将停止，并引发异常。</span><span class="sxs-lookup"><span data-stu-id="f6e06-125">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="f6e06-126">如果无论服务器生成任何错误都要继续处理命令中的语句的其他部分，请将 <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> 的 <xref:System.Data.SqlClient.SqlConnection> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="f6e06-126">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="f6e06-127">这样做会使连接对错误触发 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件，而不是引发异常并中断处理。</span><span class="sxs-lookup"><span data-stu-id="f6e06-127">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="f6e06-128">客户端应用程序可以处理此事件并对错误情况做出响应。</span><span class="sxs-lookup"><span data-stu-id="f6e06-128">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6e06-129">严重程度等于或大于 17 的错误会造成服务器停止处理命令，这种错误必须作为异常来处理。</span><span class="sxs-lookup"><span data-stu-id="f6e06-129">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="f6e06-130">在这种情况下，无论如何在 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件中处理该错误，都会引发异常。</span><span class="sxs-lookup"><span data-stu-id="f6e06-130">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="f6e06-131">使用 StateChange 事件</span><span class="sxs-lookup"><span data-stu-id="f6e06-131">Working with the StateChange Event</span></span>  
 <span data-ttu-id="f6e06-132">当**连接**状态更改时，将发生**状态更改**事件。</span><span class="sxs-lookup"><span data-stu-id="f6e06-132">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="f6e06-133">**状态更改**事件接收<xref:System.Data.StateChangeEventArgs>，使您能够通过使用**原始状态**和**当前状态**属性确定**连接**状态的更改。</span><span class="sxs-lookup"><span data-stu-id="f6e06-133">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="f6e06-134">**原始状态**属性是一个<xref:System.Data.ConnectionState>枚举，用于指示**连接**在更改之前的状态。</span><span class="sxs-lookup"><span data-stu-id="f6e06-134">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="f6e06-135">**当前状态**是一<xref:System.Data.ConnectionState>个枚举，指示**连接**更改后的状态。</span><span class="sxs-lookup"><span data-stu-id="f6e06-135">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="f6e06-136">以下代码示例使用**StateChange**事件在**连接**状态更改时向控制台写入消息。</span><span class="sxs-lookup"><span data-stu-id="f6e06-136">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f6e06-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6e06-137">See also</span></span>

- [<span data-ttu-id="f6e06-138">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="f6e06-138">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="f6e06-139">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="f6e06-139">ADO.NET Overview</span></span>](ado-net-overview.md)
