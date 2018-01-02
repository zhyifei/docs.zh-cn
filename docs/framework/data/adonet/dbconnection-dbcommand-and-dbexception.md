---
title: "DbConnection、DbCommand 和 DbException"
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
ms.assetid: 58aab611-7e6f-4749-b983-28ab7ae87dbe
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 82d2dec81429da43bf19e8673b56658ee9f4a2d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="dbconnection-dbcommand-and-dbexception"></a><span data-ttu-id="73635-102">DbConnection、DbCommand 和 DbException</span><span class="sxs-lookup"><span data-stu-id="73635-102">DbConnection, DbCommand and DbException</span></span>
<span data-ttu-id="73635-103">创建了 <xref:System.Data.Common.DbProviderFactory> 和 <xref:System.Data.Common.DbConnection> 后，您便可以使用命令和数据读取器来从数据源检索数据。</span><span class="sxs-lookup"><span data-stu-id="73635-103">Once you have created a <xref:System.Data.Common.DbProviderFactory> and a <xref:System.Data.Common.DbConnection>, you can then work with commands and data readers to retrieve data from the data source.</span></span>  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="73635-104">检索数据示例</span><span class="sxs-lookup"><span data-stu-id="73635-104">Retrieving Data Example</span></span>  
 <span data-ttu-id="73635-105">此示例将 `DbConnection` 对象用作参数。</span><span class="sxs-lookup"><span data-stu-id="73635-105">This example takes a `DbConnection` object as an argument.</span></span> <span data-ttu-id="73635-106">通过将 <xref:System.Data.Common.DbCommand> 设置为 SQL SELECT 语句，可创建 <xref:System.Data.Common.DbCommand.CommandText%2A> 以从类别表中选择数据。</span><span class="sxs-lookup"><span data-stu-id="73635-106">A <xref:System.Data.Common.DbCommand> is created to select data from the Categories table by setting the <xref:System.Data.Common.DbCommand.CommandText%2A> to a SQL SELECT statement.</span></span> <span data-ttu-id="73635-107">该代码假定数据源中存在类别表。</span><span class="sxs-lookup"><span data-stu-id="73635-107">The code assumes that the Categories table exists at the data source.</span></span> <span data-ttu-id="73635-108">打开连接并使用 <xref:System.Data.Common.DbDataReader> 检索数据。</span><span class="sxs-lookup"><span data-stu-id="73635-108">The connection is opened and the data is retrieved using a <xref:System.Data.Common.DbDataReader>.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/VB/source.vb#1)]  
  
## <a name="executing-a-command-example"></a><span data-ttu-id="73635-109">执行命令示例</span><span class="sxs-lookup"><span data-stu-id="73635-109">Executing a Command Example</span></span>  
 <span data-ttu-id="73635-110">此示例将 `DbConnection` 对象用作参数。</span><span class="sxs-lookup"><span data-stu-id="73635-110">This example takes a `DbConnection` object as an argument.</span></span> <span data-ttu-id="73635-111">如果 `DbConnection` 有效，则会打开该连接，并创建和执行 <xref:System.Data.Common.DbCommand>。</span><span class="sxs-lookup"><span data-stu-id="73635-111">If the `DbConnection` is valid, the connection is opened and a <xref:System.Data.Common.DbCommand> is created and executed.</span></span> <span data-ttu-id="73635-112">将 <xref:System.Data.Common.DbCommand.CommandText%2A> 设置为 SQL INSERT 语句，以执行插入到 Northwind 数据库类别表中的操作。</span><span class="sxs-lookup"><span data-stu-id="73635-112">The <xref:System.Data.Common.DbCommand.CommandText%2A> is set to a SQL INSERT statement that performs an insert to the Categories table in the Northwind database.</span></span> <span data-ttu-id="73635-113">该代码假定数据源中存在 Northwind 数据库，并且 INSERT 语句中使用的 SQL 语法对于指定提供程序有效。</span><span class="sxs-lookup"><span data-stu-id="73635-113">The code assumes that the Northwind database exists at the data source, and that the SQL syntax used in the INSERT statement is valid for the specified provider.</span></span> <span data-ttu-id="73635-114">数据源中发生的错误由 <xref:System.Data.Common.DbException> 代码块处理，其他所有异常在 <xref:System.Exception> 块中处理。</span><span class="sxs-lookup"><span data-stu-id="73635-114">Errors occurring at the data source are handled by the <xref:System.Data.Common.DbException> code block, and all other exceptions are handled in the <xref:System.Exception> block.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/VB/source.vb#1)]  
  
## <a name="handling-data-errors-with-dbexception"></a><span data-ttu-id="73635-115">使用 DbException 处理数据错误</span><span class="sxs-lookup"><span data-stu-id="73635-115">Handling Data Errors with DbException</span></span>  
 <span data-ttu-id="73635-116"><xref:System.Data.Common.DbException> 类是代表数据源引发的所有异常的基类。</span><span class="sxs-lookup"><span data-stu-id="73635-116">The <xref:System.Data.Common.DbException> class is the base class for all exceptions thrown on behalf of a data source.</span></span> <span data-ttu-id="73635-117">您可以在异常处理代码中使用该类来处理由各种提供程序引发的异常，而不必引用特定异常类。</span><span class="sxs-lookup"><span data-stu-id="73635-117">You can use it in your exception handling code to handle exceptions thrown by different providers without having to reference a specific exception class.</span></span> <span data-ttu-id="73635-118">下面的代码段演示如何使用 <xref:System.Data.Common.DbException> 来显示使用 <xref:System.Exception.GetType%2A>、<xref:System.Exception.Source%2A>、<xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A> 和 <xref:System.Exception.Message%2A> 属性的数据源返回的错误信息。</span><span class="sxs-lookup"><span data-stu-id="73635-118">The following code fragment demonstrates how to use <xref:System.Data.Common.DbException> to display error information returned by the data source using <xref:System.Exception.GetType%2A>, <xref:System.Exception.Source%2A>, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A>, and <xref:System.Exception.Message%2A> properties.</span></span> <span data-ttu-id="73635-119">输出将显示错误类型、指示提供程序名称的源、错误代码以及与错误相关的消息。</span><span class="sxs-lookup"><span data-stu-id="73635-119">The output will display the type of error, the source indicating the provider name, an error code, and the message associated with the error.</span></span>  
  
```vb  
Try  
    ' Do work here.  
Catch ex As DbException  
    ' Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType())  
    Console.WriteLine("Source: {0}", ex.Source)  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode)  
    Console.WriteLine("Message: {0}", ex.Message)  
Finally  
    ' Perform cleanup here.  
End Try  
```  
  
```csharp  
try  
{  
    // Do work here.  
}  
catch (DbException ex)  
{  
    // Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType());  
    Console.WriteLine("Source: {0}", ex.Source);  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode);  
    Console.WriteLine("Message: {0}", ex.Message);  
}  
finally  
{  
    // Perform cleanup here.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="73635-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="73635-120">See Also</span></span>  
 [<span data-ttu-id="73635-121">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="73635-121">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [<span data-ttu-id="73635-122">获取 DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="73635-122">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [<span data-ttu-id="73635-123">使用 DbDataAdapter 修改数据</span><span class="sxs-lookup"><span data-stu-id="73635-123">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [<span data-ttu-id="73635-124">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="73635-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
