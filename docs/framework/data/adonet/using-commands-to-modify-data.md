---
title: 使用命令修改数据
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: f2e3d162bfbdcb79cfecefa4ddc8e6a0dc46ee3c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102448"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="57938-102">使用命令修改数据</span><span class="sxs-lookup"><span data-stu-id="57938-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="57938-103">使用 .NET Framework 数据提供程序，您可以执行存储过程或数据定义语言语句（如 CREATE TABLE 和 ALTER COLUMN）来对数据库或编录执行架构处理。</span><span class="sxs-lookup"><span data-stu-id="57938-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="57938-104">这些命令不返回行像查询一样，因此**命令**对象提供**ExecuteNonQuery**来处理它们。</span><span class="sxs-lookup"><span data-stu-id="57938-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="57938-105">除了使用之外**ExecuteNonQuery**来修改架构，您可以使用过程的 SQL 语句修改数据，但不是返回行，如 INSERT、 UPDATE，并删除此方法。</span><span class="sxs-lookup"><span data-stu-id="57938-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="57938-106">虽然不返回行**ExecuteNonQuery**方法、 输入和输出参数和返回值可以传递并通过返回**参数**的集合**命令**对象。</span><span class="sxs-lookup"><span data-stu-id="57938-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57938-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="57938-107">In This Section</span></span>  
 [<span data-ttu-id="57938-108">更新数据源中的数据</span><span class="sxs-lookup"><span data-stu-id="57938-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="57938-109">描述如何执行对数据库中的数据进行修改的命令或存储过程。</span><span class="sxs-lookup"><span data-stu-id="57938-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="57938-110">执行目录操作</span><span class="sxs-lookup"><span data-stu-id="57938-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="57938-111">描述如何执行对数据库架构进行修改的命令。</span><span class="sxs-lookup"><span data-stu-id="57938-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57938-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="57938-112">See also</span></span>

- [<span data-ttu-id="57938-113">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="57938-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="57938-114">命令和参数</span><span class="sxs-lookup"><span data-stu-id="57938-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="57938-115">ADO.NET 托管提供程序和 DataSet 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="57938-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
