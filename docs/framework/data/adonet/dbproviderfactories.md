---
title: DbProviderFactories
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 8692dc761f00e0ddc8ec9fad5a5df66b7fda7916
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="dbproviderfactories"></a><span data-ttu-id="02d81-102">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="02d81-102">DbProviderFactories</span></span>
<span data-ttu-id="02d81-103"><xref:System.Data.Common> 命名空间提供用于创建与特定数据源一起使用的 <xref:System.Data.Common.DbProviderFactory> 实例的类。</span><span class="sxs-lookup"><span data-stu-id="02d81-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="02d81-104">当创建 <xref:System.Data.Common.DbProviderFactory> 实例并向其传递有关数据提供程序的信息时，`DbProviderFactory` 可以根据为其提供的信息确定要返回的正确的强类型连接对象。</span><span class="sxs-lookup"><span data-stu-id="02d81-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="02d81-105">从 .NET Framework 4 开始，machine.config 文件中不再列出诸如 <xref:System.Data.Odbc>、<xref:System.Data.OleDb>、<xref:System.Data.SqlClient> 和 <xref:System.Data.OracleClient> 等数据提供程序，但会继续列出自定义提供程序。</span><span class="sxs-lookup"><span data-stu-id="02d81-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02d81-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="02d81-106">In This Section</span></span>  
 [<span data-ttu-id="02d81-107">工厂模型概述</span><span class="sxs-lookup"><span data-stu-id="02d81-107">Factory Model Overview</span></span>](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 <span data-ttu-id="02d81-108">提供工厂设计样式和编程接口概述。</span><span class="sxs-lookup"><span data-stu-id="02d81-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="02d81-109">获取 DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="02d81-109">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="02d81-110">演示如何列出安装的数据提供程序以及如何从 <xref:System.Data.Common.DbConnection> 创建 `DbProviderFactory`。</span><span class="sxs-lookup"><span data-stu-id="02d81-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="02d81-111">DbConnection、DbCommand 和 DbException</span><span class="sxs-lookup"><span data-stu-id="02d81-111">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="02d81-112">演示如何创建 <xref:System.Data.Common.DbCommand> 和 <xref:System.Data.Common.DbDataReader>，以及如何使用 <xref:System.Data.Common.DbException> 处理数据错误。</span><span class="sxs-lookup"><span data-stu-id="02d81-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="02d81-113">使用 DbDataAdapter 修改数据</span><span class="sxs-lookup"><span data-stu-id="02d81-113">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="02d81-114">演示如何使用 <xref:System.Data.Common.DbCommandBuilder> 和 <xref:System.Data.Common.DbDataAdapter> 检索并修改数据。</span><span class="sxs-lookup"><span data-stu-id="02d81-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d81-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="02d81-115">See Also</span></span>  
 [<span data-ttu-id="02d81-116">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="02d81-116">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="02d81-117">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="02d81-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
