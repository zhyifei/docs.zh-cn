---
title: 使用命令修改数据
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 34c73549f18cd4bebb8caf842b252828b7f0a185
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780559"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="37280-102">使用命令修改数据</span><span class="sxs-lookup"><span data-stu-id="37280-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="37280-103">使用 .NET Framework 数据提供程序，您可以执行存储过程或数据定义语言语句（如 CREATE TABLE 和 ALTER COLUMN）来对数据库或编录执行架构处理。</span><span class="sxs-lookup"><span data-stu-id="37280-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="37280-104">这些命令不会像查询那样返回行，因此**Command**对象提供**ExecuteNonQuery**来处理它们。</span><span class="sxs-lookup"><span data-stu-id="37280-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="37280-105">除了使用**ExecuteNonQuery**修改架构以外，还可以使用此方法来处理修改数据但不返回行的 SQL 语句，如 INSERT、UPDATE 和 DELETE。</span><span class="sxs-lookup"><span data-stu-id="37280-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="37280-106">尽管**ExecuteNonQuery**方法不返回行，但输入和输出参数和返回值可通过**命令**对象的**参数**集合进行传递和返回。</span><span class="sxs-lookup"><span data-stu-id="37280-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37280-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="37280-107">In This Section</span></span>  
 [<span data-ttu-id="37280-108">更新数据源中的数据</span><span class="sxs-lookup"><span data-stu-id="37280-108">Updating Data in a Data Source</span></span>](updating-data-in-a-data-source.md)  
 <span data-ttu-id="37280-109">描述如何执行对数据库中的数据进行修改的命令或存储过程。</span><span class="sxs-lookup"><span data-stu-id="37280-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="37280-110">执行目录操作</span><span class="sxs-lookup"><span data-stu-id="37280-110">Performing Catalog Operations</span></span>](performing-catalog-operations.md)  
 <span data-ttu-id="37280-111">描述如何执行对数据库架构进行修改的命令。</span><span class="sxs-lookup"><span data-stu-id="37280-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37280-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="37280-112">See also</span></span>

- [<span data-ttu-id="37280-113">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="37280-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="37280-114">命令和参数</span><span class="sxs-lookup"><span data-stu-id="37280-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="37280-115">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="37280-115">ADO.NET Overview</span></span>](ado-net-overview.md)
