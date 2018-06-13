---
title: As 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.as
helpviewer_keywords:
- constraints, Visual Basic generic types
- As keyword [Visual Basic], statement syntax
- As keyword [Visual Basic]
ms.assetid: b4281ec8-2be5-49f7-aae8-ae0a96265b0d
ms.openlocfilehash: 9c1d9943c59a8ed4c3f2002fdbcdefeefafe42ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604258"
---
# <a name="as-clause-visual-basic"></a><span data-ttu-id="0c34c-102">As 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c34c-102">As Clause (Visual Basic)</span></span>
<span data-ttu-id="0c34c-103">引入了`As`子句，用于标识声明语句或泛型类型参数上的约束列表中的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0c34c-103">Introduces an `As` clause, which identifies a data type in a declaration statement or a constraint list on a generic type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c34c-104">备注</span><span class="sxs-lookup"><span data-stu-id="0c34c-104">Remarks</span></span>  
 <span data-ttu-id="0c34c-105">`As` 关键字可用于以下上下文中：</span><span class="sxs-lookup"><span data-stu-id="0c34c-105">The `As` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="0c34c-106">Aggregate 子句</span><span class="sxs-lookup"><span data-stu-id="0c34c-106">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
  
 [<span data-ttu-id="0c34c-107">Class 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-107">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="0c34c-108">Const 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-108">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="0c34c-109">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="0c34c-110">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="0c34c-111">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="0c34c-112">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-112">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="0c34c-113">Event 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-113">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="0c34c-114">为...下一语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-114">For...Next Statements</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
  
 [<span data-ttu-id="0c34c-115">每个...下一语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-115">For Each...Next Statements</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
  
 [<span data-ttu-id="0c34c-116">From 子句</span><span class="sxs-lookup"><span data-stu-id="0c34c-116">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
  
 [<span data-ttu-id="0c34c-117">Function 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-117">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="0c34c-118">Group Join 子句</span><span class="sxs-lookup"><span data-stu-id="0c34c-118">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
  
 [<span data-ttu-id="0c34c-119">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="0c34c-120">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="0c34c-120">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="0c34c-121">Property 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="0c34c-122">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="0c34c-123">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
 [<span data-ttu-id="0c34c-124">重试...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="0c34c-124">Try...Catch...Finally Statements</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0c34c-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c34c-125">See Also</span></span>  
 [<span data-ttu-id="0c34c-126">如何：创建新变量</span><span class="sxs-lookup"><span data-stu-id="0c34c-126">How to: Create a New Variable</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)  
 [<span data-ttu-id="0c34c-127">数据类型</span><span class="sxs-lookup"><span data-stu-id="0c34c-127">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="0c34c-128">变量声明</span><span class="sxs-lookup"><span data-stu-id="0c34c-128">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="0c34c-129">类型列表</span><span class="sxs-lookup"><span data-stu-id="0c34c-129">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="0c34c-130">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="0c34c-130">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="0c34c-131">关键字</span><span class="sxs-lookup"><span data-stu-id="0c34c-131">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
