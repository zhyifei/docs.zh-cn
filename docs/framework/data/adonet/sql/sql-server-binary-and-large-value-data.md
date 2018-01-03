---
title: "SQL Server 二进制和大值数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 015003becc47910b875629f021a9e196ba8445f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="cca3a-102">SQL Server 二进制和大值数据</span><span class="sxs-lookup"><span data-stu-id="cca3a-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="cca3a-103">SQL Server 提供 `max` 说明符，它可扩展 `varchar`、`nvarchar` 和 `varbinary` 数据类型的存储容量。</span><span class="sxs-lookup"><span data-stu-id="cca3a-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="cca3a-104">`varchar(max)``nvarchar(max)`，和`varbinary(max)`统称为*大型值数据类型*。</span><span class="sxs-lookup"><span data-stu-id="cca3a-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="cca3a-105">您可以使用大值数据类型来存储最大为 2^31-1 个字节的数据。</span><span class="sxs-lookup"><span data-stu-id="cca3a-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="cca3a-106">SQL Server 2008 引入了 FILESTREAM 属性，该属性不是一种数据类型，而是一种可在列上定义的属性，因而允许将大值数据存储在文件系统上而不是存储在数据库中。</span><span class="sxs-lookup"><span data-stu-id="cca3a-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cca3a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="cca3a-107">In This Section</span></span>  
 [<span data-ttu-id="cca3a-108">在 ADO.NET 中修改大值 (max) 数据</span><span class="sxs-lookup"><span data-stu-id="cca3a-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 <span data-ttu-id="cca3a-109">说明如何使用大值数据类型。</span><span class="sxs-lookup"><span data-stu-id="cca3a-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="cca3a-110">FILESTREAM 数据</span><span class="sxs-lookup"><span data-stu-id="cca3a-110">FILESTREAM Data</span></span>](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 <span data-ttu-id="cca3a-111">描述如何使用在 SQL Server 2008 中通过 FILESTREAM 属性存储的大值数据。</span><span class="sxs-lookup"><span data-stu-id="cca3a-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca3a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cca3a-112">See Also</span></span>  
 [<span data-ttu-id="cca3a-113">SQL Server 数据类型和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cca3a-113">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="cca3a-114">ADO.NET 中的 SQL Server 数据操作</span><span class="sxs-lookup"><span data-stu-id="cca3a-114">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="cca3a-115">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="cca3a-115">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="cca3a-116">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="cca3a-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
