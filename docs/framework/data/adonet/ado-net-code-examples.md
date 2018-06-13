---
title: ADO.NET 代码示例
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 5b34f93348c43a26f603140f2393389e1bce107a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759135"
---
# <a name="adonet-code-examples"></a><span data-ttu-id="dacf3-102">ADO.NET 代码示例</span><span class="sxs-lookup"><span data-stu-id="dacf3-102">ADO.NET code examples</span></span>
<span data-ttu-id="dacf3-103">本主题中的代码列表演示如何使用下面的 ADO.NET 技术从数据库中检索数据：</span><span class="sxs-lookup"><span data-stu-id="dacf3-103">The code listings in this topic demonstrate how to retrieve data from a database by using the following ADO.NET technologies:</span></span>

- <span data-ttu-id="dacf3-104">ADO.NET 数据提供程序：</span><span class="sxs-lookup"><span data-stu-id="dacf3-104">ADO.NET data providers:</span></span>

  - <span data-ttu-id="dacf3-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span><span class="sxs-lookup"><span data-stu-id="dacf3-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span></span>

  - <span data-ttu-id="dacf3-106">[OleDb](#oledb) (`System.Data.OleDb`)</span><span class="sxs-lookup"><span data-stu-id="dacf3-106">[OleDb](#oledb) (`System.Data.OleDb`)</span></span>

  - <span data-ttu-id="dacf3-107">[Odbc](#odbc) (`System.Data.Odbc`)</span><span class="sxs-lookup"><span data-stu-id="dacf3-107">[Odbc](#odbc) (`System.Data.Odbc`)</span></span>

  - <span data-ttu-id="dacf3-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span><span class="sxs-lookup"><span data-stu-id="dacf3-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span></span>

- <span data-ttu-id="dacf3-109">ADO.NET 实体框架：</span><span class="sxs-lookup"><span data-stu-id="dacf3-109">ADO.NET Entity Framework:</span></span>

  - [<span data-ttu-id="dacf3-110">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="dacf3-110">LINQ to Entities</span></span>](#linq-to-entities)

  - [<span data-ttu-id="dacf3-111">类型化的 ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="dacf3-111">Typed ObjectQuery</span></span>](#typed-objectquery)

  - <span data-ttu-id="dacf3-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span><span class="sxs-lookup"><span data-stu-id="dacf3-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span></span>

- [<span data-ttu-id="dacf3-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="dacf3-113">LINQ to SQL</span></span>](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a><span data-ttu-id="dacf3-114">ADO.NET 数据提供程序示例</span><span class="sxs-lookup"><span data-stu-id="dacf3-114">ADO.NET data provider examples</span></span>
<span data-ttu-id="dacf3-115">以下代码列表演示如何使用 ADO.NET 数据提供程序从数据库中检索数据。</span><span class="sxs-lookup"><span data-stu-id="dacf3-115">The following code listings demonstrate how to retrieve data from a database using ADO.NET data providers.</span></span> <span data-ttu-id="dacf3-116">数据在一个 `DataReader` 中返回。</span><span class="sxs-lookup"><span data-stu-id="dacf3-116">The data is returned in a `DataReader`.</span></span> <span data-ttu-id="dacf3-117">有关详细信息，请参阅[使用 DataReader 检索数据](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)。</span><span class="sxs-lookup"><span data-stu-id="dacf3-117">For more information, see [Retrieving Data Using a DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).</span></span>

### <a name="sqlclient"></a><span data-ttu-id="dacf3-118">SqlClient</span><span class="sxs-lookup"><span data-stu-id="dacf3-118">SqlClient</span></span>
<span data-ttu-id="dacf3-119">此示例中的代码假定你可以连接到`Northwind`Microsoft SQL Server 上的示例数据库。</span><span class="sxs-lookup"><span data-stu-id="dacf3-119">The code in this example assumes that you can connect to the `Northwind` sample database on Microsoft SQL Server.</span></span> <span data-ttu-id="dacf3-120">在此情形 5 中，示例代码创建一个 <xref:System.Data.SqlClient.SqlCommand> 以从 Products 表中选择行，并添加 <xref:System.Data.SqlClient.SqlParameter> 来将结果限制为其 UnitPrice 大于指定参数值的行。</span><span class="sxs-lookup"><span data-stu-id="dacf3-120">The code creates a <xref:System.Data.SqlClient.SqlCommand> to select rows from the Products table, adding a <xref:System.Data.SqlClient.SqlParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="dacf3-121"><xref:System.Data.SqlClient.SqlConnection>在内部打开`using`块，这将确保关闭和释放在代码退出时会资源。</span><span class="sxs-lookup"><span data-stu-id="dacf3-121">The <xref:System.Data.SqlClient.SqlConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="dacf3-122">示例代码使用 <xref:System.Data.SqlClient.SqlDataReader> 执行命令，并在控制台窗口中显示结果。</span><span class="sxs-lookup"><span data-stu-id="dacf3-122">The code executes the command by using a <xref:System.Data.SqlClient.SqlDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a><span data-ttu-id="dacf3-123">OleDb</span><span class="sxs-lookup"><span data-stu-id="dacf3-123">OleDb</span></span>
<span data-ttu-id="dacf3-124">此示例中的代码假定您可以连接到 Microsoft Access Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="dacf3-124">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="dacf3-125">在此情形 5 中，示例代码创建一个 <xref:System.Data.OleDb.OleDbCommand> 以从 Products 表中选择行，并添加 <xref:System.Data.OleDb.OleDbParameter> 来将结果限制为其 UnitPrice 大于指定参数值的行。</span><span class="sxs-lookup"><span data-stu-id="dacf3-125">The code creates a <xref:System.Data.OleDb.OleDbCommand> to select rows from the Products table, adding a <xref:System.Data.OleDb.OleDbParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="dacf3-126"><xref:System.Data.OleDb.OleDbConnection> 在 `using` 块内打开，这将确保在代码退出时会关闭和释放资源。</span><span class="sxs-lookup"><span data-stu-id="dacf3-126">The <xref:System.Data.OleDb.OleDbConnection> is opened inside of a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="dacf3-127">示例代码使用 <xref:System.Data.OleDb.OleDbDataReader> 执行命令，并在控制台窗口中显示结果。</span><span class="sxs-lookup"><span data-stu-id="dacf3-127">The code executes the command by using a <xref:System.Data.OleDb.OleDbDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a><span data-ttu-id="dacf3-128">Odbc</span><span class="sxs-lookup"><span data-stu-id="dacf3-128">Odbc</span></span>
<span data-ttu-id="dacf3-129">此示例中的代码假定您可以连接到 Microsoft Access Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="dacf3-129">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="dacf3-130">在此情形 5 中，示例代码创建一个 <xref:System.Data.Odbc.OdbcCommand> 以从 Products 表中选择行，并添加 <xref:System.Data.Odbc.OdbcParameter> 来将结果限制为其 UnitPrice 大于指定参数值的行。</span><span class="sxs-lookup"><span data-stu-id="dacf3-130">The code creates a <xref:System.Data.Odbc.OdbcCommand> to select rows from the Products table, adding a <xref:System.Data.Odbc.OdbcParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="dacf3-131"><xref:System.Data.Odbc.OdbcConnection>在内部打开`using`块，这将确保关闭和释放在代码退出时会资源。</span><span class="sxs-lookup"><span data-stu-id="dacf3-131">The <xref:System.Data.Odbc.OdbcConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="dacf3-132">示例代码使用 <xref:System.Data.Odbc.OdbcDataReader> 执行命令，并在控制台窗口中显示结果。</span><span class="sxs-lookup"><span data-stu-id="dacf3-132">The code executes the command by using a <xref:System.Data.Odbc.OdbcDataReader>, and displays the results in the console window.</span></span>

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)] 
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)] 

### <a name="oracleclient"></a><span data-ttu-id="dacf3-133">OracleClient</span><span class="sxs-lookup"><span data-stu-id="dacf3-133">OracleClient</span></span>
<span data-ttu-id="dacf3-134">此示例中的代码假定已建立与 Oracle 服务器上的 DEMO.CUSTOMER 的连接。</span><span class="sxs-lookup"><span data-stu-id="dacf3-134">The code in this example assumes a connection to DEMO.CUSTOMER on an Oracle server.</span></span> <span data-ttu-id="dacf3-135">您还必须添加对 System.Data.OracleClient.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="dacf3-135">You must also add a reference to the System.Data.OracleClient.dll.</span></span> <span data-ttu-id="dacf3-136">示例代码在 <xref:System.Data.OracleClient.OracleDataReader> 中返回数据。</span><span class="sxs-lookup"><span data-stu-id="dacf3-136">The code returns the data in an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a><span data-ttu-id="dacf3-137">实体框架示例</span><span class="sxs-lookup"><span data-stu-id="dacf3-137">Entity Framework examples</span></span>
<span data-ttu-id="dacf3-138">以下代码列表演示如何通过查询实体数据模型 (EDM) 中的实体来从数据源检索数据。</span><span class="sxs-lookup"><span data-stu-id="dacf3-138">The following code listings demonstrate how to retrieve data from a data source by querying entities in an Entity Data Model (EDM).</span></span> <span data-ttu-id="dacf3-139">这些示例使用[Northwind 模型](http://msdn.microsoft.com/74521f8c-e974-48cb-8858-c08deff52638)。</span><span class="sxs-lookup"><span data-stu-id="dacf3-139">These examples use the [Northwind model](http://msdn.microsoft.com/74521f8c-e974-48cb-8858-c08deff52638).</span></span> <span data-ttu-id="dacf3-140">有关详细信息，请参阅[实体框架概述](../../../../docs/framework/data/adonet/ef/overview.md)。</span><span class="sxs-lookup"><span data-stu-id="dacf3-140">For more information, see [Entity Framework Overview](../../../../docs/framework/data/adonet/ef/overview.md).</span></span>

### <a name="linq-to-entities"></a><span data-ttu-id="dacf3-141">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="dacf3-141">LINQ to Entities</span></span>
<span data-ttu-id="dacf3-142">此示例中的代码使用 LINQ 查询以 Categories 对象的形式返回数据，这些对象将作为仅包含 CategoryID 和 CategoryName 属性的匿名类型提取。</span><span class="sxs-lookup"><span data-stu-id="dacf3-142">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="dacf3-143">有关详细信息，请参阅[LINQ to Entities 概述](http://msdn.microsoft.com/86d87a27-c17a-45ac-b28d-72c8500333c6)。</span><span class="sxs-lookup"><span data-stu-id="dacf3-143">For more information, see [LINQ to Entities Overview](http://msdn.microsoft.com/86d87a27-c17a-45ac-b28d-72c8500333c6).</span></span>

```csharp
using System;
using System.Linq;
using System.Data.Objects;
using NorthwindModel;

class LinqSample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            try
            {
                var query = from category in context.Categories
                            select new
                            {
                                categoryID = category.CategoryID,
                                categoryName = category.CategoryName
                            };

                foreach (var categoryInfo in query)
                {
                    Console.WriteLine("\t{0}\t{1}",
                        categoryInfo.categoryID, categoryInfo.categoryName);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Linq
Imports System.Data.Objects
Imports NorthwindModel

Class LinqSample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Try
                Dim query = From category In context.Categories _
                            Select New With _
                            { _
                                .categoryID = category.CategoryID, _
                                .categoryName = category.CategoryName _
                            }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                        categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

### <a name="typed-objectquery"></a><span data-ttu-id="dacf3-144">类型化 ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="dacf3-144">Typed ObjectQuery</span></span>
<span data-ttu-id="dacf3-145">此示例中的代码使用 <xref:System.Data.Objects.ObjectQuery%601> 以 Categories 对象的形式返回数据。</span><span class="sxs-lookup"><span data-stu-id="dacf3-145">The code in this example uses an <xref:System.Data.Objects.ObjectQuery%601> to return data as Categories objects.</span></span> <span data-ttu-id="dacf3-146">有关详细信息，请参阅[对象查询](http://msdn.microsoft.com/0768033c-876f-471d-85d5-264884349276)。</span><span class="sxs-lookup"><span data-stu-id="dacf3-146">For more information, see [Object Queries](http://msdn.microsoft.com/0768033c-876f-471d-85d5-264884349276).</span></span>

```csharp
using System;
using System.Data.Objects;
using NorthwindModel;

class ObjectQuerySample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            ObjectQuery<Categories> categoryQuery = context.Categories;

            foreach (Categories category in 
                categoryQuery.Execute(MergeOption.AppendOnly))
            {
                Console.WriteLine("\t{0}\t{1}",
                    category.CategoryID, category.CategoryName);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Data.Objects
Imports NorthwindModel

Class ObjectQuerySample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Dim categoryQuery As ObjectQuery(Of Categories) = context.Categories

            For Each category As Categories In _
                categoryQuery.Execute(MergeOption.AppendOnly)
                Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                    category.CategoryID, category.CategoryName)
            Next
        End Using
    End Sub
End Class
```

### <a name="entityclient"></a><span data-ttu-id="dacf3-147">EntityClient</span><span class="sxs-lookup"><span data-stu-id="dacf3-147">EntityClient</span></span>
<span data-ttu-id="dacf3-148">此示例中的代码使用 <xref:System.Data.EntityClient.EntityCommand> 来执行实体 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="dacf3-148">The code in this example uses an <xref:System.Data.EntityClient.EntityCommand> to execute an Entity SQL query.</span></span> <span data-ttu-id="dacf3-149">此查询会返回表示 Categories 实体类型的实例的记录的列表。</span><span class="sxs-lookup"><span data-stu-id="dacf3-149">This query returns a list of records that represent instances of the Categories entity type.</span></span> <span data-ttu-id="dacf3-150"><xref:System.Data.EntityClient.EntityDataReader> 用于访问结果集中的数据记录。</span><span class="sxs-lookup"><span data-stu-id="dacf3-150">An <xref:System.Data.EntityClient.EntityDataReader> is used to access data records in the result set.</span></span> <span data-ttu-id="dacf3-151">有关详细信息，请参阅[用于实体框架的 EntityClient 提供程序](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)。</span><span class="sxs-lookup"><span data-stu-id="dacf3-151">For more information, see [EntityClient Provider for the Entity Framework](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.EntityClient;
using NorthwindModel;

class EntityClientSample
{
    public static void ExecuteQuery()
    {
        string queryString =
            @"SELECT c.CategoryID, c.CategoryName 
                FROM NorthwindEntities.Categories AS c";

        using (EntityConnection conn =
            new EntityConnection("name=NorthwindEntities"))
        {
            try
            {
                conn.Open();
                using (EntityCommand query = new EntityCommand(queryString, conn))
                {
                    using (DbDataReader rdr = 
                        query.ExecuteReader(CommandBehavior.SequentialAccess))
                    {
                        while (rdr.Read())
                        {
                            Console.WriteLine("\t{0}\t{1}", rdr[0], rdr[1]);
                        }
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Data
Imports System.Data.Common
Imports System.Data.EntityClient
Imports NorthwindModel

Class EntityClientSample
    Public Shared Sub ExecuteQuery()
        Dim queryString As String = _
            "SELECT c.CategoryID, c.CategoryName " & _
                "FROM NorthwindEntities.Categories AS c"

        Using conn As EntityConnection = _
            New EntityConnection("name=NorthwindEntities")

            Try
                conn.Open()
                Using query As EntityCommand = _
                New EntityCommand(queryString, conn)
                    Using rdr As DbDataReader = _
                        query.ExecuteReader(CommandBehavior.SequentialAccess)
                        While rdr.Read()
                            Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                                              rdr(0), rdr(1))
                        End While
                    End Using
                End Using
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using 
    End Sub
End Class
```

## <a name="linq-to-sql"></a><span data-ttu-id="dacf3-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="dacf3-152">LINQ to SQL</span></span>
<span data-ttu-id="dacf3-153">此示例中的代码使用 LINQ 查询以 Categories 对象的形式返回数据，这些对象将作为仅包含 CategoryID 和 CategoryName 属性的匿名类型提取。</span><span class="sxs-lookup"><span data-stu-id="dacf3-153">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="dacf3-154">此示例基于 Northwind 数据上下文。</span><span class="sxs-lookup"><span data-stu-id="dacf3-154">This example is based on the Northwind data context.</span></span> <span data-ttu-id="dacf3-155">有关详细信息，请参阅[入门](../../../../docs/framework/data/adonet/sql/linq/getting-started.md)。</span><span class="sxs-lookup"><span data-stu-id="dacf3-155">For more information, see [Getting Started](../../../../docs/framework/data/adonet/sql/linq/getting-started.md).</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Northwind;

    class LinqSqlSample
    {
        public static void ExecuteQuery()
        {
            using (NorthwindDataContext db = new NorthwindDataContext())
            {
                try
                {
                    var query = from category in db.Categories
                                select new
                                {
                                    categoryID = category.CategoryID,
                                    categoryName = category.CategoryName
                                };

                    foreach (var categoryInfo in query)
                    {
                        Console.WriteLine("vbTab {0} vbTab {1}",
                            categoryInfo.categoryID, categoryInfo.categoryName);
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine(ex.Message);
                }
            }
        }
    }
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports Northwind

Class LinqSqlSample
    Public Shared Sub ExecuteQuery()
        Using db As NorthwindDataContext = New NorthwindDataContext()
            Try
                Dim query = From category In db.Categories _
                                Select New With _
                                { _
                                    .categoryID = category.CategoryID, _
                                    .categoryName = category.CategoryName _
                                }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                            categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
            End Using 
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="dacf3-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="dacf3-156">See also</span></span>
 [<span data-ttu-id="dacf3-157">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="dacf3-157">ADO.NET Overview</span></span>](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [<span data-ttu-id="dacf3-158">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="dacf3-158">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="dacf3-159">创建数据应用程序</span><span class="sxs-lookup"><span data-stu-id="dacf3-159">Creating Data Applications</span></span>](http://msdn.microsoft.com/library/ab334d5f-4f49-4346-bce0-3325d6130b3e)  
 [<span data-ttu-id="dacf3-160">查询实体数据模型 （实体框架任务）</span><span class="sxs-lookup"><span data-stu-id="dacf3-160">Querying an Entity Data Model (Entity Framework Tasks)</span></span>](http://msdn.microsoft.com/187f1caa-e4d3-4e31-bd99-5d5c2b329c77)  
 [<span data-ttu-id="dacf3-161">如何： 执行返回匿名类型的对象的查询</span><span class="sxs-lookup"><span data-stu-id="dacf3-161">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](http://msdn.microsoft.com/3b264025-e911-4d73-90ce-992d2b9d189d)  
 [<span data-ttu-id="dacf3-162">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="dacf3-162">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)  
