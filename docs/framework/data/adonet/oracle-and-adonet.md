---
title: Oracle 和 ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 5683f2b4ba57021ff6dda3a51baca016f886b605
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980075"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="de003-102">Oracle 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de003-102">Oracle and ADO.NET</span></span>
> [!NOTE]
> <span data-ttu-id="de003-103"><xref:System.Data.OracleClient> 中的类型已过时。</span><span class="sxs-lookup"><span data-stu-id="de003-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="de003-104">当前版本的 .NET Framework 仍支持这些类型，但以后的版本会将这些类型删除。</span><span class="sxs-lookup"><span data-stu-id="de003-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="de003-105">Microsoft 建议您使用第三方 Oracle 提供程序。</span><span class="sxs-lookup"><span data-stu-id="de003-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="de003-106">本节介绍特定于 Oracle .NET Framework 数据提供程序的功能和行为。</span><span class="sxs-lookup"><span data-stu-id="de003-106">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="de003-107">用于 Oracle 的 .NET Framework 数据提供程序使用 oracle 客户端软件提供的 Oracle 调用接口（OCI）来访问 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="de003-107">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="de003-108">数据提供程序的功能与 SQL Server、OLE DB 和 ODBC 的 .NET Framework 数据提供程序的功能类似。</span><span class="sxs-lookup"><span data-stu-id="de003-108">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="de003-109">若要使用适用于 Oracle 的 .NET Framework 数据提供程序，应用程序必须引用 <xref:System.Data.OracleClient> 命名空间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="de003-109">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="de003-110">在编译代码时还必须包括对该 DLL 的引用。</span><span class="sxs-lookup"><span data-stu-id="de003-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="de003-111">例如，如果编译的是 C# 程序，命令行中应包括：</span><span class="sxs-lookup"><span data-stu-id="de003-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="de003-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="de003-112">In This Section</span></span>  
 [<span data-ttu-id="de003-113">系统要求</span><span class="sxs-lookup"><span data-stu-id="de003-113">System Requirements</span></span>](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="de003-114">描述使用适用于 Oracle 的 .NET Framework 数据提供程序的要求，并介绍使用它时要注意的一些问题。</span><span class="sxs-lookup"><span data-stu-id="de003-114">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="de003-115">Oracle BFILEs</span><span class="sxs-lookup"><span data-stu-id="de003-115">Oracle BFILEs</span></span>](oracle-bfiles.md)  
 <span data-ttu-id="de003-116">描述用于使用 Oracle BFILE 数据类型的 <xref:System.Data.OracleClient.OracleBFile> 类。</span><span class="sxs-lookup"><span data-stu-id="de003-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="de003-117">Oracle LOBs</span><span class="sxs-lookup"><span data-stu-id="de003-117">Oracle LOBs</span></span>](oracle-lobs.md)  
 <span data-ttu-id="de003-118">描述用于使用 Oracle LOB 数据类型的 <xref:System.Data.OracleClient.OracleLob> 类。</span><span class="sxs-lookup"><span data-stu-id="de003-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="de003-119">Oracle REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="de003-119">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)  
 <span data-ttu-id="de003-120">描述对 Oracle REF CURSOR 数据类型的支持。</span><span class="sxs-lookup"><span data-stu-id="de003-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="de003-121">OracleTypes</span><span class="sxs-lookup"><span data-stu-id="de003-121">OracleTypes</span></span>](oracletypes.md)  
 <span data-ttu-id="de003-122">描述可以用于使用 Oracle 数据类型的结构，包括 <xref:System.Data.OracleClient.OracleNumber> 和 <xref:System.Data.OracleClient.OracleString>。</span><span class="sxs-lookup"><span data-stu-id="de003-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="de003-123">Oracle 序列</span><span class="sxs-lookup"><span data-stu-id="de003-123">Oracle Sequences</span></span>](oracle-sequences.md)  
 <span data-ttu-id="de003-124">说明对检索服务器生成的 Oracle 键序列值的支持。</span><span class="sxs-lookup"><span data-stu-id="de003-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="de003-125">Oracle 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="de003-125">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="de003-126">列出 Oracle 数据类型及其与 <xref:System.Data.OracleClient.OracleDataReader> 的映射。</span><span class="sxs-lookup"><span data-stu-id="de003-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="de003-127">Oracle 分布式事务</span><span class="sxs-lookup"><span data-stu-id="de003-127">Oracle Distributed Transactions</span></span>](oracle-distributed-transactions.md)  
 <span data-ttu-id="de003-128">描述 <xref:System.Data.OracleClient.OracleConnection> 对象如何自动在现有分布式事务中登记（如果确定某个事务是活动的）。</span><span class="sxs-lookup"><span data-stu-id="de003-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="de003-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="de003-129">Related Sections</span></span>  
 [<span data-ttu-id="de003-130">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="de003-130">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="de003-131">描述使用 ADO.NET 时的安全编码做法。</span><span class="sxs-lookup"><span data-stu-id="de003-131">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="de003-132">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="de003-132">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)  
 <span data-ttu-id="de003-133">说明如何创建和使用 `DataSets`、类型化 `DataSets`、`DataTables` 和 `DataViews`。</span><span class="sxs-lookup"><span data-stu-id="de003-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="de003-134">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="de003-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="de003-135">说明如何使用 ADO.NET 中的数据。</span><span class="sxs-lookup"><span data-stu-id="de003-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="de003-136">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de003-136">SQL Server and ADO.NET</span></span>](./sql/index.md)  
 <span data-ttu-id="de003-137">描述如何使用 SQL Server 特定的功能。</span><span class="sxs-lookup"><span data-stu-id="de003-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="de003-138">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="de003-138">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="de003-139">描述用于在 ADO.NET 中编写与提供程序无关的代码的一般类。</span><span class="sxs-lookup"><span data-stu-id="de003-139">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de003-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de003-140">See also</span></span>

- [<span data-ttu-id="de003-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="de003-141">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="de003-142">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="de003-142">ADO.NET Overview</span></span>](ado-net-overview.md)
