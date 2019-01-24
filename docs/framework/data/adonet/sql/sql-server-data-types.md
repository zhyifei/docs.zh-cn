---
title: SQL Server 数据类型和 ADO.NET
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 14a3c8b2f520efce96667b2028405ca36ed17a28
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741504"
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="ece10-102">SQL Server 数据类型和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ece10-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="ece10-103">SQL Server 和 .NET Framework 基于不同的类型系统，这可导致潜在的数据丢失。</span><span class="sxs-lookup"><span data-stu-id="ece10-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="ece10-104">为了保持数据的完整性，适用于 SQL Server 的 .NET Framework 数据提供程序 (<xref:System.Data.SqlClient>) 提供了用于处理 SQL Server 数据的类型化访问器方法。</span><span class="sxs-lookup"><span data-stu-id="ece10-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="ece10-105">可以使用 <xref:System.Data.SqlDbType> 类中的枚举来指定 <xref:System.Data.SqlClient.SqlParameter> 数据类型。</span><span class="sxs-lookup"><span data-stu-id="ece10-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="ece10-106">有关详细信息和说明 SQL Server 和.NET Framework 数据类型之间的数据类型映射的表，请参阅[SQL Server 数据类型映射](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="ece10-106">For more information and a table that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="ece10-107">SQL Server 2008 引入了旨在满足业务需求的新数据类型，以用于处理日期和时间、结构化、半结构化和非结构化的数据。</span><span class="sxs-lookup"><span data-stu-id="ece10-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="ece10-108">这些文档位于 SQL Server 2008 联机丛书中。</span><span class="sxs-lookup"><span data-stu-id="ece10-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="ece10-109">可在应用程序中使用的 SQL Server 数据类型取决于您正在使用的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="ece10-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="ece10-110">有关更多信息，请参见下表中的相关版本的 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="ece10-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="ece10-111">**SQL Server 联机丛书**</span><span class="sxs-lookup"><span data-stu-id="ece10-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="ece10-112">数据类型 （数据库引擎）</span><span class="sxs-lookup"><span data-stu-id="ece10-112">Data Types (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a><span data-ttu-id="ece10-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="ece10-113">In This Section</span></span>  
 [<span data-ttu-id="ece10-114">SqlTypes 和数据集</span><span class="sxs-lookup"><span data-stu-id="ece10-114">SqlTypes and the DataSet</span></span>](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 <span data-ttu-id="ece10-115">说明对 `SqlTypes` 中 `DataSet` 的类型支持。</span><span class="sxs-lookup"><span data-stu-id="ece10-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="ece10-116">处理 NULL 值</span><span class="sxs-lookup"><span data-stu-id="ece10-116">Handling Null Values</span></span>](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 <span data-ttu-id="ece10-117">演示如何使用空值和三值逻辑。</span><span class="sxs-lookup"><span data-stu-id="ece10-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="ece10-118">比较 GUID 和 uniqueidentifier 值</span><span class="sxs-lookup"><span data-stu-id="ece10-118">Comparing GUID and uniqueidentifier Values</span></span>](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="ece10-119">演示如何在 SQL Server 和 .NET Framework 中使用 GUID 和 uniqueidentifier 值。</span><span class="sxs-lookup"><span data-stu-id="ece10-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="ece10-120">日期和时间数据</span><span class="sxs-lookup"><span data-stu-id="ece10-120">Date and Time Data</span></span>](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 <span data-ttu-id="ece10-121">说明如何使用在 SQL Server 2008 中引入的新的日期和时间数据类型。</span><span class="sxs-lookup"><span data-stu-id="ece10-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="ece10-122">大型 UDT</span><span class="sxs-lookup"><span data-stu-id="ece10-122">Large UDTs</span></span>](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 <span data-ttu-id="ece10-123">演示如何从在 SQL Server 2008 中引入的大值 UDT 检索数据。</span><span class="sxs-lookup"><span data-stu-id="ece10-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="ece10-124">SQL Server 中的 XML 数据</span><span class="sxs-lookup"><span data-stu-id="ece10-124">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 <span data-ttu-id="ece10-125">说明如何使用从 SQL Server 中检索的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="ece10-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ece10-126">参考</span><span class="sxs-lookup"><span data-stu-id="ece10-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="ece10-127">描述 `DataSet` 类及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="ece10-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="ece10-128">说明 `SqlTypes` 命名空间及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="ece10-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="ece10-129">说明 `SqlDbType` 枚举及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="ece10-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="ece10-130">说明 `DbType` 枚举及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="ece10-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece10-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="ece10-131">See also</span></span>
- [<span data-ttu-id="ece10-132">SQL Server 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="ece10-132">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [<span data-ttu-id="ece10-133">配置参数和参数数据类型</span><span class="sxs-lookup"><span data-stu-id="ece10-133">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="ece10-134">表值参数</span><span class="sxs-lookup"><span data-stu-id="ece10-134">Table-Valued Parameters</span></span>](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)
- [<span data-ttu-id="ece10-135">SQL Server 二进制和大值数据</span><span class="sxs-lookup"><span data-stu-id="ece10-135">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="ece10-136">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ece10-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
