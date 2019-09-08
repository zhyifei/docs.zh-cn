---
title: SQL Server 中的批量复制操作
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: ae97bcdd6776d573cf9e523133c2c00a42c273bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782528"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="fde5a-102">SQL Server 中的批量复制操作</span><span class="sxs-lookup"><span data-stu-id="fde5a-102">Bulk Copy Operations in SQL Server</span></span>
<span data-ttu-id="fde5a-103">Microsoft SQL Server 包括一个名为**bcp**的常用命令行实用程序，用于快速将大型文件大容量复制到 SQL Server 数据库中的表或视图中。</span><span class="sxs-lookup"><span data-stu-id="fde5a-103">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="fde5a-104">使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类可以编写提供类似功能的托管代码解决方案。</span><span class="sxs-lookup"><span data-stu-id="fde5a-104">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="fde5a-105">还可以通过其他方式将数据加载到 SQL Server 表中（例如 INSERT 语句），但是 <xref:System.Data.SqlClient.SqlBulkCopy> 提供的性能要明显优于这些方式。</span><span class="sxs-lookup"><span data-stu-id="fde5a-105">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="fde5a-106"><xref:System.Data.SqlClient.SqlBulkCopy> 类只能用于向 SQL Server 表中写入数据。</span><span class="sxs-lookup"><span data-stu-id="fde5a-106">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="fde5a-107">但是，数据源不限于 SQL Server；可以使用任何数据源，只要数据可以加载到 <xref:System.Data.DataTable> 实例或使用 <xref:System.Data.IDataReader> 实例读取即可。</span><span class="sxs-lookup"><span data-stu-id="fde5a-107">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="fde5a-108">使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="fde5a-108">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="fde5a-109">单次批量复制操作</span><span class="sxs-lookup"><span data-stu-id="fde5a-109">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="fde5a-110">多次批量复制操作</span><span class="sxs-lookup"><span data-stu-id="fde5a-110">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="fde5a-111">事务中的批量复制操作</span><span class="sxs-lookup"><span data-stu-id="fde5a-111">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fde5a-112">当使用 .NET Framework 版本1.1 或更早版本（不支持<xref:System.Data.SqlClient.SqlBulkCopy>类）时，可以使用<xref:System.Data.SqlClient.SqlCommand>对象执行 SQL Server transact-sql **BULK INSERT**语句。</span><span class="sxs-lookup"><span data-stu-id="fde5a-112">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fde5a-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="fde5a-113">In This Section</span></span>  
 [<span data-ttu-id="fde5a-114">大容量复制示例设置</span><span class="sxs-lookup"><span data-stu-id="fde5a-114">Bulk Copy Example Setup</span></span>](bulk-copy-example-setup.md)  
 <span data-ttu-id="fde5a-115">描述批量复制示例中使用的表，并提供用于在 AdventureWorks 数据库中创建表的 SQL 脚本。</span><span class="sxs-lookup"><span data-stu-id="fde5a-115">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="fde5a-116">单个大容量复制操作</span><span class="sxs-lookup"><span data-stu-id="fde5a-116">Single Bulk Copy Operations</span></span>](single-bulk-copy-operations.md)  
 <span data-ttu-id="fde5a-117">描述如何使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类将数据单次批量复制到 SQL Server 实例中，以及如何使用 Transact-SQL 语句和 <xref:System.Data.SqlClient.SqlCommand> 类执行批量复制操作。</span><span class="sxs-lookup"><span data-stu-id="fde5a-117">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="fde5a-118">多个大容量复制操作</span><span class="sxs-lookup"><span data-stu-id="fde5a-118">Multiple Bulk Copy Operations</span></span>](multiple-bulk-copy-operations.md)  
 <span data-ttu-id="fde5a-119">描述如何使用 <xref:System.Data.SqlClient.SqlBulkCopy> 类将数据多次批量复制到 SQL Server 实例中。</span><span class="sxs-lookup"><span data-stu-id="fde5a-119">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="fde5a-120">事务和大容量复制操作</span><span class="sxs-lookup"><span data-stu-id="fde5a-120">Transaction and Bulk Copy Operations</span></span>](transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="fde5a-121">描述如何在事务中执行批量复制操作，包括如何提交或回滚事务。</span><span class="sxs-lookup"><span data-stu-id="fde5a-121">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde5a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="fde5a-122">See also</span></span>

- [<span data-ttu-id="fde5a-123">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fde5a-123">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="fde5a-124">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="fde5a-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
