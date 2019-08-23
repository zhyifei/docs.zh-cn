---
title: 进行和提交数据更改
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: dd0a8288ca924cb17bdacdeeb94f81c3d27d3e4e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915775"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="c10fc-102">进行和提交数据更改</span><span class="sxs-lookup"><span data-stu-id="c10fc-102">Making and Submitting Data Changes</span></span>
<span data-ttu-id="c10fc-103">本节中的主题介绍如何做出更改并将更改传输至数据库，以及如何处理开放式并发冲突。</span><span class="sxs-lookup"><span data-stu-id="c10fc-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c10fc-104">您可以重写 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]、`Insert` 和 `Update` 数据库操作的 `Delete` 默认方法。</span><span class="sxs-lookup"><span data-stu-id="c10fc-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="c10fc-105">有关详细信息, 请参阅[自定义插入、更新和删除操作](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="c10fc-105">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="c10fc-106">使用 Visual Studio 的开发人员可以使用对象关系设计器来开发用于实现相同目的的存储过程。</span><span class="sxs-lookup"><span data-stu-id="c10fc-106">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c10fc-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="c10fc-107">In This Section</span></span>  
 [<span data-ttu-id="c10fc-108">如何：在数据库中插入行</span><span class="sxs-lookup"><span data-stu-id="c10fc-108">How to: Insert Rows Into the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md)  
 <span data-ttu-id="c10fc-109">介绍如何通过向对象模型添加对象将行插入到数据库中。</span><span class="sxs-lookup"><span data-stu-id="c10fc-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>  
  
 [<span data-ttu-id="c10fc-110">如何：更新数据库中的行</span><span class="sxs-lookup"><span data-stu-id="c10fc-110">How to: Update Rows in the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md)  
 <span data-ttu-id="c10fc-111">介绍如何通过更新对象模型中的对象来更新数据库中的行。</span><span class="sxs-lookup"><span data-stu-id="c10fc-111">Describes how to update rows in the database by updating objects in the object model.</span></span>  
  
 [<span data-ttu-id="c10fc-112">如何：删除数据库中的行</span><span class="sxs-lookup"><span data-stu-id="c10fc-112">How to: Delete Rows From the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)  
 <span data-ttu-id="c10fc-113">介绍如何通过删除对象模型中的对象来删除数据库中的行。</span><span class="sxs-lookup"><span data-stu-id="c10fc-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>  
  
 [<span data-ttu-id="c10fc-114">如何：将更改提交到数据库</span><span class="sxs-lookup"><span data-stu-id="c10fc-114">How to: Submit Changes to the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md)  
 <span data-ttu-id="c10fc-115">介绍如何将对象模型更改发送到数据库。</span><span class="sxs-lookup"><span data-stu-id="c10fc-115">Describes how to send object-model changes to the database.</span></span>  
  
 [<span data-ttu-id="c10fc-116">如何：使用事务提交方括号数据</span><span class="sxs-lookup"><span data-stu-id="c10fc-116">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)  
 <span data-ttu-id="c10fc-117">介绍如何将操作包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="c10fc-117">Describes how to include operations in a transaction.</span></span>  
  
 [<span data-ttu-id="c10fc-118">如何：动态创建数据库</span><span class="sxs-lookup"><span data-stu-id="c10fc-118">How to: Dynamically Create a Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)  
 <span data-ttu-id="c10fc-119">介绍如何动态生成数据库，以及此方法的一些典型方案。</span><span class="sxs-lookup"><span data-stu-id="c10fc-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>  
  
 [<span data-ttu-id="c10fc-120">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="c10fc-120">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 <span data-ttu-id="c10fc-121">介绍用于处理开放式并发问题的技术。</span><span class="sxs-lookup"><span data-stu-id="c10fc-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
