---
title: 示例提供程序中的 SQL 生成
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: a59f1fecf85d63208c3388204c962b5838902ba7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854318"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="bcd6c-102">示例提供程序中的 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="bcd6c-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="bcd6c-103">[实体框架示例提供程序](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)演示支持实体框架的 ADO.NET 数据提供程序的新组件。</span><span class="sxs-lookup"><span data-stu-id="bcd6c-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the Entity Framework.</span></span>  <span data-ttu-id="bcd6c-104">它使用 SQL Server 2005 数据库，并实现为 System.Data.SqlClient ADO.NET 2.0 数据提供程序的一个包装。</span><span class="sxs-lookup"><span data-stu-id="bcd6c-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="bcd6c-105">该示例提供程序的 SQL 生成模块（位于 SQL Generation 文件夹下，不包括 DmlSqlGenerator.cs 文件）采用一个输入 DbQueryCommandTree，并且生成单个 SQL SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="bcd6c-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bcd6c-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="bcd6c-106">In This Section</span></span>  
 <span data-ttu-id="bcd6c-107">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="bcd6c-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="bcd6c-108">体系结构和设计</span><span class="sxs-lookup"><span data-stu-id="bcd6c-108">Architecture and Design</span></span>](architecture-and-design.md)  
  
 [<span data-ttu-id="bcd6c-109">演练：SQL 生成</span><span class="sxs-lookup"><span data-stu-id="bcd6c-109">Walkthrough: SQL Generation</span></span>](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="bcd6c-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcd6c-110">See also</span></span>

- [<span data-ttu-id="bcd6c-111">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="bcd6c-111">SQL Generation</span></span>](sql-generation.md)
