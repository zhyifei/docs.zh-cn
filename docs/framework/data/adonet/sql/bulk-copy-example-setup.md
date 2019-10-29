---
title: 批量复制示例设置
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 28fa5cde1dcbaf9f38450116a56fc11d904edc1c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040256"
---
# <a name="bulk-copy-example-setup"></a><span data-ttu-id="56aff-102">批量复制示例设置</span><span class="sxs-lookup"><span data-stu-id="56aff-102">Bulk Copy Example Setup</span></span>
<span data-ttu-id="56aff-103"><xref:System.Data.SqlClient.SqlBulkCopy> 类只能用于向 SQL Server 表中写入数据。</span><span class="sxs-lookup"><span data-stu-id="56aff-103">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="56aff-104">本主题中所示的代码示例使用 SQL Server 示例数据库**AdventureWorks**。</span><span class="sxs-lookup"><span data-stu-id="56aff-104">The code samples shown in this topic use the SQL Server sample database, **AdventureWorks**.</span></span> <span data-ttu-id="56aff-105">为避免改变现有表，代码示例将数据写入必须先创建的表。</span><span class="sxs-lookup"><span data-stu-id="56aff-105">To avoid altering the existing tables code samples write data to tables that you must create first.</span></span>  
  
 <span data-ttu-id="56aff-106">**BulkCopyDemoMatchingColumns**和**BulkCopyDemoDifferentColumns**表均基于**AdventureWorks** **Products**表。</span><span class="sxs-lookup"><span data-stu-id="56aff-106">The **BulkCopyDemoMatchingColumns** and **BulkCopyDemoDifferentColumns** tables are both based on the **AdventureWorks** **Production.Products** table.</span></span> <span data-ttu-id="56aff-107">在使用这些表的代码示例中，数据从**Products**表添加到其中一个示例表中。</span><span class="sxs-lookup"><span data-stu-id="56aff-107">In code samples that use these tables, data is added from the **Production.Products** table to one of these sample tables.</span></span> <span data-ttu-id="56aff-108">当示例演示如何将列从源数据映射到目标表时，将使用**BulkCopyDemoDifferentColumns**表;**BulkCopyDemoMatchingColumns**用于大多数其他示例。</span><span class="sxs-lookup"><span data-stu-id="56aff-108">The **BulkCopyDemoDifferentColumns** table is used when the sample illustrates how to map columns from the source data to the destination table; **BulkCopyDemoMatchingColumns** is used for most other samples.</span></span>  
  
 <span data-ttu-id="56aff-109">一些代码示例演示如何使用一个 <xref:System.Data.SqlClient.SqlBulkCopy> 类写入多个表。</span><span class="sxs-lookup"><span data-stu-id="56aff-109">A few of the code samples demonstrate how to use one <xref:System.Data.SqlClient.SqlBulkCopy> class to write to multiple tables.</span></span> <span data-ttu-id="56aff-110">对于这些示例， **BulkCopyDemoOrderHeader**和**BulkCopyDemoOrderDetail**表用作目标表。</span><span class="sxs-lookup"><span data-stu-id="56aff-110">For these samples, the **BulkCopyDemoOrderHeader** and **BulkCopyDemoOrderDetail** tables are used as the destination tables.</span></span> <span data-ttu-id="56aff-111">这些表基于**AdventureWorks**中的**SalesOrderHeader**和**SalesOrderDetail**表。</span><span class="sxs-lookup"><span data-stu-id="56aff-111">These tables are based on the **Sales.SalesOrderHeader** and **Sales.SalesOrderDetail** tables in **AdventureWorks**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56aff-112">提供**SqlBulkCopy**代码示例是为了演示仅使用**SqlBulkCopy**的语法。</span><span class="sxs-lookup"><span data-stu-id="56aff-112">The **SqlBulkCopy** code samples are provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="56aff-113">如果源表和目标表位于同一个 SQL Server 实例中，则使用 Transact-SQL `INSERT … SELECT` 语句复制数据会更加容易、更加迅速。</span><span class="sxs-lookup"><span data-stu-id="56aff-113">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
## <a name="table-setup"></a><span data-ttu-id="56aff-114">表设置</span><span class="sxs-lookup"><span data-stu-id="56aff-114">Table Setup</span></span>  
 <span data-ttu-id="56aff-115">若要创建代码示例正确运行所需的表，必须在 SQL Server 数据库中运行下面的 Transact-SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="56aff-115">To create the tables necessary for the code samples to run correctly, you must run the following Transact-SQL statements in a SQL Server database.</span></span>  
  
```sql
USE AdventureWorks  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoMatchingColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoMatchingColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoMatchingColumns]([ProductID] [int] IDENTITY(1,1) NOT NULL,  
    [Name] [nvarchar](50) NOT NULL,  
    [ProductNumber] [nvarchar](25) NOT NULL,  
 CONSTRAINT [PK_ProductID] PRIMARY KEY CLUSTERED  
(  
    [ProductID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoDifferentColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoDifferentColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoDifferentColumns]([ProdID] [int] IDENTITY(1,1) NOT NULL,  
    [ProdNum] [nvarchar](25) NOT NULL,  
    [ProdName] [nvarchar](50) NOT NULL,  
 CONSTRAINT [PK_ProdID] PRIMARY KEY CLUSTERED  
(  
    [ProdID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderHeader]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderHeader]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderHeader]([SalesOrderID] [int] IDENTITY(1,1) NOT NULL,  
    [OrderDate] [datetime] NOT NULL,  
    [AccountNumber] [nvarchar](15) NULL,  
 CONSTRAINT [PK_SalesOrderID] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderDetail]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderDetail]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderDetail]([SalesOrderID] [int] NOT NULL,  
    [SalesOrderDetailID] [int] NOT NULL,  
    [OrderQty] [smallint] NOT NULL,  
    [ProductID] [int] NOT NULL,  
    [UnitPrice] [money] NOT NULL,  
 CONSTRAINT [PK_LineNumber] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC,  
    [SalesOrderDetailID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
```  
  
## <a name="see-also"></a><span data-ttu-id="56aff-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="56aff-116">See also</span></span>

- [<span data-ttu-id="56aff-117">SQL Server 中的大容量复制操作</span><span class="sxs-lookup"><span data-stu-id="56aff-117">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="56aff-118">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="56aff-118">ADO.NET Overview</span></span>](../ado-net-overview.md)
