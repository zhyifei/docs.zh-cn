---
title: 示例提供程序中的 SQL 生成
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: 88223930b65ccec9d030104c62d8b4b2e77ddbe2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879289"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="84431-102">示例提供程序中的 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="84431-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="84431-103">[实体框架示例提供程序](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)演示了 ADO.NET 数据提供程序支持的新组件[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="84431-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="84431-104">它使用 SQL Server 2005 数据库，并实现为 System.Data.SqlClient ADO.NET 2.0 数据提供程序的一个包装。</span><span class="sxs-lookup"><span data-stu-id="84431-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="84431-105">该示例提供程序的 SQL 生成模块（位于 SQL Generation 文件夹下，不包括 DmlSqlGenerator.cs 文件）采用一个输入 DbQueryCommandTree，并且生成单个 SQL SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="84431-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84431-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="84431-106">In This Section</span></span>  
 <span data-ttu-id="84431-107">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="84431-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="84431-108">体系结构和设计</span><span class="sxs-lookup"><span data-stu-id="84431-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="84431-109">演练：SQL 生成</span><span class="sxs-lookup"><span data-stu-id="84431-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="84431-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="84431-110">See also</span></span>

- [<span data-ttu-id="84431-111">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="84431-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
