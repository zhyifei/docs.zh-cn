---
title: 运算符优先级 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 722ebe5f0ec530f8c7f86e9f9901451b060903f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760345"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="8dbf2-102">运算符优先级 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8dbf2-102">Operator Precedence (Entity SQL)</span></span>
<span data-ttu-id="8dbf2-103">当[!INCLUDE[esql](../../../../../../includes/esql-md.md)]查询有多个运算符，运算符优先级确定执行的操作序列。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="8dbf2-104">执行顺序可能对查询结果有明显的影响。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="8dbf2-105">运算符的优先级别如下表中所示。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="8dbf2-106">在较低级别的运算符之前先对较高级别的运算符进行求值。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="8dbf2-107">级别</span><span class="sxs-lookup"><span data-stu-id="8dbf2-107">Level</span></span>|<span data-ttu-id="8dbf2-108">运算类型</span><span class="sxs-lookup"><span data-stu-id="8dbf2-108">Operation type</span></span>|<span data-ttu-id="8dbf2-109">运算符</span><span class="sxs-lookup"><span data-stu-id="8dbf2-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="8dbf2-110">1</span><span class="sxs-lookup"><span data-stu-id="8dbf2-110">1</span></span>|<span data-ttu-id="8dbf2-111">基本</span><span class="sxs-lookup"><span data-stu-id="8dbf2-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="8dbf2-112">2</span><span class="sxs-lookup"><span data-stu-id="8dbf2-112">2</span></span>|<span data-ttu-id="8dbf2-113">一元</span><span class="sxs-lookup"><span data-stu-id="8dbf2-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="8dbf2-114">3</span><span class="sxs-lookup"><span data-stu-id="8dbf2-114">3</span></span>|<span data-ttu-id="8dbf2-115">乘法</span><span class="sxs-lookup"><span data-stu-id="8dbf2-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="8dbf2-116">4</span><span class="sxs-lookup"><span data-stu-id="8dbf2-116">4</span></span>|<span data-ttu-id="8dbf2-117">加法</span><span class="sxs-lookup"><span data-stu-id="8dbf2-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="8dbf2-118">5</span><span class="sxs-lookup"><span data-stu-id="8dbf2-118">5</span></span>|<span data-ttu-id="8dbf2-119">排序</span><span class="sxs-lookup"><span data-stu-id="8dbf2-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="8dbf2-120">6</span><span class="sxs-lookup"><span data-stu-id="8dbf2-120">6</span></span>|<span data-ttu-id="8dbf2-121">相等</span><span class="sxs-lookup"><span data-stu-id="8dbf2-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="8dbf2-122">7</span><span class="sxs-lookup"><span data-stu-id="8dbf2-122">7</span></span>|<span data-ttu-id="8dbf2-123">条件“与”</span><span class="sxs-lookup"><span data-stu-id="8dbf2-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="8dbf2-124">8</span><span class="sxs-lookup"><span data-stu-id="8dbf2-124">8</span></span>|<span data-ttu-id="8dbf2-125">条件“或”</span><span class="sxs-lookup"><span data-stu-id="8dbf2-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="8dbf2-126">当一个表达式中的两个运算符有相同的运算符优先级别时，将按照它们在查询中的位置对其从左到右进行求值。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="8dbf2-127">例如，`x+y-z` 将计算为 `(x+y)-z`。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="8dbf2-128">在查询中可以使用括号替代所定义的运算符的优先级。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="8dbf2-129">首先对括号中的内容进行求值，从而产生一个结果，然后括号外的运算符才可以使用这个结果。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="8dbf2-130">例如，`x+y*z`乘以`y`通过`z`，然后添加`x`，但`(x+y)*z`添加`x`到`y`然后相乘的结果`z`。</span><span class="sxs-lookup"><span data-stu-id="8dbf2-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dbf2-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="8dbf2-131">See also</span></span>

- [<span data-ttu-id="8dbf2-132">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="8dbf2-132">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
