---
title: SQL Server 二进制和大值数据
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 4b7a3f16726d6363cd702fb912bb7be281a25000
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192961"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="477cf-102">SQL Server 二进制和大值数据</span><span class="sxs-lookup"><span data-stu-id="477cf-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="477cf-103">SQL Server 提供 `max` 说明符，它可扩展 `varchar`、`nvarchar` 和 `varbinary` 数据类型的存储容量。</span><span class="sxs-lookup"><span data-stu-id="477cf-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> `varchar(max)`<span data-ttu-id="477cf-104">`nvarchar(max)`，并`varbinary(max)`统称为*大型值数据类型*。</span><span class="sxs-lookup"><span data-stu-id="477cf-104">, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="477cf-105">您可以使用大值数据类型来存储最大为 2^31-1 个字节的数据。</span><span class="sxs-lookup"><span data-stu-id="477cf-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="477cf-106">SQL Server 2008 引入了 FILESTREAM 属性，该属性不是一种数据类型，而是一种可在列上定义的属性，因而允许将大值数据存储在文件系统上而不是存储在数据库中。</span><span class="sxs-lookup"><span data-stu-id="477cf-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="477cf-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="477cf-107">In This Section</span></span>  
 [<span data-ttu-id="477cf-108">在 ADO.NET 中修改大值 (max) 数据</span><span class="sxs-lookup"><span data-stu-id="477cf-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 <span data-ttu-id="477cf-109">说明如何使用大值数据类型。</span><span class="sxs-lookup"><span data-stu-id="477cf-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="477cf-110">FILESTREAM 数据</span><span class="sxs-lookup"><span data-stu-id="477cf-110">FILESTREAM Data</span></span>](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 <span data-ttu-id="477cf-111">描述如何使用在 SQL Server 2008 中通过 FILESTREAM 属性存储的大值数据。</span><span class="sxs-lookup"><span data-stu-id="477cf-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477cf-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="477cf-112">See also</span></span>

- [<span data-ttu-id="477cf-113">SQL Server 数据类型和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="477cf-113">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [<span data-ttu-id="477cf-114">ADO.NET 中的 SQL Server 数据操作</span><span class="sxs-lookup"><span data-stu-id="477cf-114">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)
- [<span data-ttu-id="477cf-115">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="477cf-115">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="477cf-116">ADO.NET 托管提供程序和 DataSet 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="477cf-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
