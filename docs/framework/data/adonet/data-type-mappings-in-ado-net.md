---
title: "ADO.NET 中的数据类型映射"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 65f9d8a6182c5882a173a3a3733c1c0c220efbf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="data-type-mappings-in-adonet"></a><span data-ttu-id="2ef3c-102">ADO.NET 中的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="2ef3c-102">Data Type Mappings in ADO.NET</span></span>
<span data-ttu-id="2ef3c-103">.NET Framework 基于用于定义如何在运行时声明、使用和管理类型的通用类型系统。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-103">The .NET Framework is based on the common type system, which defines how types are declared, used, and managed in the runtime.</span></span> <span data-ttu-id="2ef3c-104">它由值类型和引用类型组成，这两种类型均派生自 <xref:System.Object> 基类型。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-104">It consists of both value types and reference types, which all derive from the <xref:System.Object> base type.</span></span> <span data-ttu-id="2ef3c-105">使用数据源时，如果未显式指定数据类型，则从数据提供程序推断出它。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-105">When working with a data source, the data type is inferred from the data provider if it is not explicitly specified.</span></span> <span data-ttu-id="2ef3c-106">例如，<xref:System.Data.DataSet> 对象独立于任何特定的数据源。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-106">For example, a <xref:System.Data.DataSet> object is independent of any specific data source.</span></span> <span data-ttu-id="2ef3c-107">`DataSet` 中的数据从数据源中进行检索，而更改则会使用 `DataAdapter` 持久保存回数据源。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-107">Data in a `DataSet` is retrieved from a data source, and changes are persisted back to the data source by using a `DataAdapter`.</span></span> <span data-ttu-id="2ef3c-108">这意味着当 `DataAdapter` 使用数据源中的值填充 <xref:System.Data.DataTable> 中的 `DataSet` 时，`DataTable` 中列的结果数据类型为 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 类型，而不是特定于用于连接数据源的 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 数据提供程序的类型。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-108">This means that when a `DataAdapter` fills a <xref:System.Data.DataTable> in a `DataSet` with values from a data source, the resulting data types of the columns in the `DataTable` are [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types, instead of types specific to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider that is used to connect to the data source.</span></span>  
  
 <span data-ttu-id="2ef3c-109">同样，当 `DataReader` 返回数据源中的值时，生成的值将存储在具有 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 类型的局部变量中。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-109">Likewise, when a `DataReader` returns a value from a data source, the resulting value is stored in a local variable that has a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type.</span></span> <span data-ttu-id="2ef3c-110">对于 `Fill` 的 `DataAdapter` 操作和 `Get` 的 `DataReader` 方法，将从 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 数据提供程序中返回的值来推断 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 类型。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-110">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type is inferred from the value returned from the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider.</span></span>  
  
 <span data-ttu-id="2ef3c-111">当所返回值的特定类型已知时，您可以使用 `DataReader` 的类型化访问器方法，而不是依靠推断出的数据类型。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-111">Instead of relying on the inferred data type, you can use the typed accessor methods of the `DataReader` when you know the specific type of the value being returned.</span></span> <span data-ttu-id="2ef3c-112">类型化访问器方法以特定 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 类型的形式返回值，无需再进行其他类型转换，因此会提高性能。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-112">Typed accessor methods give you better performance by returning a value as a specific [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type, which eliminates the need for additional type conversion.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ef3c-113">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 数据提供程序的数据类型的 null 值都用 `DBNull.Value` 表示。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-113">Null values for [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider data types are represented by `DBNull.Value`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ef3c-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="2ef3c-114">In This Section</span></span>  
 [<span data-ttu-id="2ef3c-115">SQL Server 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="2ef3c-115">SQL Server Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 <span data-ttu-id="2ef3c-116">列出针对 <xref:System.Data.SqlClient> 的推断数据类型映射和数据访问器方法。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-116">Lists inferred data type mappings and data accessor methods for <xref:System.Data.SqlClient>.</span></span>  
  
 [<span data-ttu-id="2ef3c-117">OLE DB 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="2ef3c-117">OLE DB Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 <span data-ttu-id="2ef3c-118">列出针对 <xref:System.Data.OleDb> 的推断数据类型映射和数据访问器方法。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-118">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OleDb>.</span></span>  
  
 [<span data-ttu-id="2ef3c-119">ODBC 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="2ef3c-119">ODBC Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 <span data-ttu-id="2ef3c-120">列出针对 <xref:System.Data.Odbc> 的推断数据类型映射和数据访问器方法。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-120">Lists inferred data type mappings and data accessor methods for <xref:System.Data.Odbc>.</span></span>  
  
 [<span data-ttu-id="2ef3c-121">Oracle 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="2ef3c-121">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="2ef3c-122">列出针对 <xref:System.Data.OracleClient> 的推断数据类型映射和数据访问器方法。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-122">Lists inferred data type mappings and data accessor methods for <xref:System.Data.OracleClient>.</span></span>  
  
 [<span data-ttu-id="2ef3c-123">浮点数字</span><span class="sxs-lookup"><span data-stu-id="2ef3c-123">Floating-Point Numbers</span></span>](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 <span data-ttu-id="2ef3c-124">描述开发人员在使用浮点数时经常遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="2ef3c-124">Describes issues that developers frequently encounter when working with floating-point numbers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef3c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ef3c-125">See Also</span></span>  
 [<span data-ttu-id="2ef3c-126">SQL Server 数据类型和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2ef3c-126">SQL Server Data Types and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="2ef3c-127">配置参数和参数数据类型</span><span class="sxs-lookup"><span data-stu-id="2ef3c-127">Configuring Parameters and Parameter Data Types</span></span>](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="2ef3c-128">检索数据库架构信息</span><span class="sxs-lookup"><span data-stu-id="2ef3c-128">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="2ef3c-129">常规类型系统</span><span class="sxs-lookup"><span data-stu-id="2ef3c-129">Common Type System</span></span>](../../../../docs/standard/base-types/common-type-system.md)  
 [<span data-ttu-id="2ef3c-130">转换类型</span><span class="sxs-lookup"><span data-stu-id="2ef3c-130">Converting Types</span></span>](http://msdn.microsoft.com/en-us/6038316e-bdaf-4f55-8006-407f591ce156)  
 [<span data-ttu-id="2ef3c-131">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="2ef3c-131">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
