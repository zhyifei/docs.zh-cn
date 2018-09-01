---
title: 在 LINQ to Entities 查询中调用函数
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 4aed9fd59cceb72baac9dc12a85c52787c4b3866
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388510"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="54695-102">在 LINQ to Entities 查询中调用函数</span><span class="sxs-lookup"><span data-stu-id="54695-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="54695-103">本节中的主题说明如何调用 LINQ to Entities 查询中的函数。</span><span class="sxs-lookup"><span data-stu-id="54695-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="54695-104"><xref:System.Data.Objects.EntityFunctions> 和 <xref:System.Data.Objects.SqlClient.SqlFunctions> 类提供了对作为实体框架的一部分的规范函数和数据库函数的访问功能。</span><span class="sxs-lookup"><span data-stu-id="54695-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="54695-105">有关详细信息，请参阅[如何： 调用规范函数](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)并[如何： 调用数据库函数](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="54695-105">For more information, see [How to: Call Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) and [How to: Call Database Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="54695-106">调用自定义函数的过程需要三个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="54695-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1.  <span data-ttu-id="54695-107">在概念模型中定义函数或在存储模型中声明函数。</span><span class="sxs-lookup"><span data-stu-id="54695-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2.  <span data-ttu-id="54695-108">将方法添加到应用程序并将其映射到具有 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> 的模型中的函数。</span><span class="sxs-lookup"><span data-stu-id="54695-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3.  <span data-ttu-id="54695-109">在 LINQ to Entities 查询中调用该函数。</span><span class="sxs-lookup"><span data-stu-id="54695-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="54695-110">有关更多信息，请参见本节中的各主题。</span><span class="sxs-lookup"><span data-stu-id="54695-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54695-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="54695-111">In This Section</span></span>  
 [<span data-ttu-id="54695-112">如何：调用 Canonical 函数</span><span class="sxs-lookup"><span data-stu-id="54695-112">How to: Call Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="54695-113">如何：调用数据库函数</span><span class="sxs-lookup"><span data-stu-id="54695-113">How to: Call Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [<span data-ttu-id="54695-114">如何：调用自定义数据库函数</span><span class="sxs-lookup"><span data-stu-id="54695-114">How to: Call Custom Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="54695-115">如何：在查询中调用模型定义的函数</span><span class="sxs-lookup"><span data-stu-id="54695-115">How to: Call Model-Defined Functions in Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="54695-116">如何：调用模型定义的函数作为对象方法</span><span class="sxs-lookup"><span data-stu-id="54695-116">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="54695-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="54695-117">See Also</span></span>  
 [<span data-ttu-id="54695-118">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="54695-118">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="54695-119">规范函数</span><span class="sxs-lookup"><span data-stu-id="54695-119">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [<span data-ttu-id="54695-120">.edmx 文件概述</span><span class="sxs-lookup"><span data-stu-id="54695-120">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="54695-121">如何： 在概念模型中定义自定义函数</span><span class="sxs-lookup"><span data-stu-id="54695-121">How to: Define Custom Functions in the Conceptual Model</span></span>](https://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)
