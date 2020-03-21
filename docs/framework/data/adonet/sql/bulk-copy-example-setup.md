---
title: 批量复制示例设置
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 80350d112da03c00e422432ce271ca5ea3ac58ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148837"
---
# <a name="bulk-copy-example-setup"></a><span data-ttu-id="f02fe-102">批量复制示例设置</span><span class="sxs-lookup"><span data-stu-id="f02fe-102">Bulk Copy Example Setup</span></span>
<span data-ttu-id="f02fe-103"><xref:System.Data.SqlClient.SqlBulkCopy> 类可用于只将数据写入 SQL Server 表。</span><span class="sxs-lookup"><span data-stu-id="f02fe-103">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="f02fe-104">本主题中所示的代码示例使用 SQL Server 示例数据库 AdventureWorks\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f02fe-104">The code samples shown in this topic use the SQL Server sample database, **AdventureWorks**.</span></span> <span data-ttu-id="f02fe-105">为避免改变现有表，代码示例将数据写入必须一开始就创建的表中。</span><span class="sxs-lookup"><span data-stu-id="f02fe-105">To avoid altering the existing tables code samples write data to tables that you must create first.</span></span>  
  
 <span data-ttu-id="f02fe-106">BulkCopyDemoMatchingColumns 表和 BulkCopyDemoDifferentColumns 表均基于 AdventureWorks Production.Products 表\*\*\*\*\*\*\*\*\*\*\*\* \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f02fe-106">The **BulkCopyDemoMatchingColumns** and **BulkCopyDemoDifferentColumns** tables are both based on the **AdventureWorks** **Production.Products** table.</span></span> <span data-ttu-id="f02fe-107">在使用这些表的代码示例中，数据将从**Production.Products**表添加到这些示例表中。</span><span class="sxs-lookup"><span data-stu-id="f02fe-107">In code samples that use these tables, data is added from the **Production.Products** table to one of these sample tables.</span></span> <span data-ttu-id="f02fe-108">当示例演示如何将列从源数据映射到目标表时，将使用**BulkCopyDemo不同列**表;**批量复制演示匹配列**用于大多数其他示例。</span><span class="sxs-lookup"><span data-stu-id="f02fe-108">The **BulkCopyDemoDifferentColumns** table is used when the sample illustrates how to map columns from the source data to the destination table; **BulkCopyDemoMatchingColumns** is used for most other samples.</span></span>  
  
 <span data-ttu-id="f02fe-109">多个代码示例演示如何使用一个 <xref:System.Data.SqlClient.SqlBulkCopy> 类写入多个表。</span><span class="sxs-lookup"><span data-stu-id="f02fe-109">A few of the code samples demonstrate how to use one <xref:System.Data.SqlClient.SqlBulkCopy> class to write to multiple tables.</span></span> <span data-ttu-id="f02fe-110">对于这些示例，**批量复制DemoOrderHeader**和**BulkCopyDemoOrder 详细信息**表用作目标表。</span><span class="sxs-lookup"><span data-stu-id="f02fe-110">For these samples, the **BulkCopyDemoOrderHeader** and **BulkCopyDemoOrderDetail** tables are used as the destination tables.</span></span> <span data-ttu-id="f02fe-111">这些表基于《销售 **.销售订单标题\*\*\*\*》和《销售订单详细信息**》中的 **"销售**订单详细信息"表。</span><span class="sxs-lookup"><span data-stu-id="f02fe-111">These tables are based on the **Sales.SalesOrderHeader** and **Sales.SalesOrderDetail** tables in **AdventureWorks**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f02fe-112">提供 SqlBulkCopy 代码示例是为了演示仅使用 SqlBulkCopy 时的语法\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f02fe-112">The **SqlBulkCopy** code samples are provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="f02fe-113">如果源表和目标表位于同一 SQL Server 实例中，可以更便捷地使用 Transact-SQL `INSERT … SELECT` 语句复制数据。</span><span class="sxs-lookup"><span data-stu-id="f02fe-113">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
## <a name="table-setup"></a><span data-ttu-id="f02fe-114">表设置</span><span class="sxs-lookup"><span data-stu-id="f02fe-114">Table Setup</span></span>  
 <span data-ttu-id="f02fe-115">若要创建正确运行代码示例所需的表，必须在 SQL Server 数据库中运行以下 Transact-SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="f02fe-115">To create the tables necessary for the code samples to run correctly, you must run the following Transact-SQL statements in a SQL Server database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f02fe-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f02fe-116">See also</span></span>

- [<span data-ttu-id="f02fe-117">SQL 服务器中的批量复制操作</span><span class="sxs-lookup"><span data-stu-id="f02fe-117">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="f02fe-118">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="f02fe-118">ADO.NET Overview</span></span>](../ado-net-overview.md)
