---
title: 在 LINQ to Entities 查询中调用函数
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 267bb393d9e75c66eb18139e8897da34bd86e159
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251268"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="70d6c-102">在 LINQ to Entities 查询中调用函数</span><span class="sxs-lookup"><span data-stu-id="70d6c-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="70d6c-103">本节中的主题说明如何调用 LINQ to Entities 查询中的函数。</span><span class="sxs-lookup"><span data-stu-id="70d6c-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="70d6c-104"><xref:System.Data.Objects.EntityFunctions> 和 <xref:System.Data.Objects.SqlClient.SqlFunctions> 类提供了对作为实体框架的一部分的规范函数和数据库函数的访问功能。</span><span class="sxs-lookup"><span data-stu-id="70d6c-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="70d6c-105">有关详细信息，请参阅[如何：调用规范函数](how-to-call-canonical-functions.md)以及[如何：调用数据库函数](how-to-call-database-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="70d6c-105">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="70d6c-106">调用自定义函数的过程需要三个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="70d6c-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="70d6c-107">在概念模型中定义函数或在存储模型中声明函数。</span><span class="sxs-lookup"><span data-stu-id="70d6c-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="70d6c-108">将方法添加到应用程序并将其映射到具有 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> 的模型中的函数。</span><span class="sxs-lookup"><span data-stu-id="70d6c-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="70d6c-109">在 LINQ to Entities 查询中调用该函数。</span><span class="sxs-lookup"><span data-stu-id="70d6c-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="70d6c-110">有关更多信息，请参见本节中的各主题。</span><span class="sxs-lookup"><span data-stu-id="70d6c-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="70d6c-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="70d6c-111">In This Section</span></span>  
 [<span data-ttu-id="70d6c-112">如何：调用规范函数</span><span class="sxs-lookup"><span data-stu-id="70d6c-112">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="70d6c-113">如何：调用数据库函数</span><span class="sxs-lookup"><span data-stu-id="70d6c-113">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="70d6c-114">如何：调用自定义数据库函数</span><span class="sxs-lookup"><span data-stu-id="70d6c-114">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="70d6c-115">如何：在查询中调用模型定义的函数</span><span class="sxs-lookup"><span data-stu-id="70d6c-115">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="70d6c-116">如何：调用模型定义的函数作为对象方法</span><span class="sxs-lookup"><span data-stu-id="70d6c-116">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="70d6c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="70d6c-117">See also</span></span>

- [<span data-ttu-id="70d6c-118">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="70d6c-118">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="70d6c-119">规范函数</span><span class="sxs-lookup"><span data-stu-id="70d6c-119">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="70d6c-120">[.edmx 文件概述](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="70d6c-120">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="70d6c-121">[如何：在概念模型中定义自定义函数](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="70d6c-121">[How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
