---
title: "连接事件"
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
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4d6a818f3173780cee2f8a01b9f66804cd2969b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="connection-events"></a>连接事件
所有.NET Framework 数据提供程序具有**连接**有从数据源中检索信息性消息，或以确定是否可以使用的两个事件的对象的状态**连接**具有更改。 下表说明的事件**连接**对象。  
  
|事件|描述|  
|-----------|-----------------|  
|**InfoMessage**|当从数据源中返回信息性消息时发生。 信息性消息是数据源中不会引发异常的消息。|  
|**StateChange**|发生时的状态**连接**更改。|  
  
## <a name="working-with-the-infomessage-event"></a>使用 InfoMessage 事件  
 您可以使用 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 对象的 <xref:System.Data.SqlClient.SqlConnection> 事件从 SQL Server 数据源中检索警告和信息性消息。 从数据源返回的严重程度为 11 到 16 的错误将引发异常。 但是，<xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件可用于从数据源中获取与错误无关联的消息。 对于 Microsoft SQL Server，任何严重程度等于或小于 10 的错误都将被视为信息性消息，将使用 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件来捕获。 有关更多信息，请参见“SQL Server 联机图书”中的“错误消息严重程度”主题。  
  
 <xref:System.Data.SqlClient.SqlConnection.InfoMessage>事件接收<xref:System.Data.SqlClient.SqlInfoMessageEventArgs>对象包含其**错误**属性、 数据源的消息的集合。 您可以查询**错误**错误号和消息文本以及错误根源此集合中的对象。 SQL Server .NET Framework 数据提供程序还包含有关消息所来自的数据库、存储过程和行号的详细信息。  
  
### <a name="example"></a>示例  
 以下代码示例显示如何为 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件添加事件处理程序。  
  
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
  
## <a name="handling-errors-as-infomessages"></a>将错误作为信息性消息处理  
 通常，只有从服务器发出的信息性消息和警告消息才会触发 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件。 但是，真正的错误发生时，执行**ExecuteNonQuery**或**ExecuteReader**启动服务器操作的方法将暂停，将引发异常。  
  
 如果无论服务器生成任何错误都要继续处理命令中的语句的其他部分，请将 <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> 的 <xref:System.Data.SqlClient.SqlConnection> 属性设置为 `true`。 这样做会使连接对错误触发 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件，而不是引发异常并中断处理。 客户端应用程序可以处理此事件并对错误情况做出响应。  
  
> [!NOTE]
>  严重程度等于或大于 17 的错误会造成服务器停止处理命令，这种错误必须作为异常来处理。 在这种情况下，无论如何在 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 事件中处理该错误，都会引发异常。  
  
## <a name="working-with-the-statechange-event"></a>使用 StateChange 事件  
 **StateChange**事件发生时的状态**连接**更改。 **StateChange**事件接收<xref:System.Data.StateChangeEventArgs>，使您能够确定状态的改变**连接**使用**OriginalState**和**CurrentState**属性。 **OriginalState**属性是<xref:System.Data.ConnectionState>枚举，指示的状态**连接**才将其更改。 **CurrentState**是<xref:System.Data.ConnectionState>枚举，指示的状态**连接**改变后。  
  
 下面的代码示例使用**StateChange**事件向控制台写入一条消息时的状态**连接**更改。  
  
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
  
## <a name="see-also"></a>请参阅  
 [连接到数据源](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
