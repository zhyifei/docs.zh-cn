---
title: 如何：在值 (Visual Basic 中) 创建一个变量，不会更改
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 57792db826caa996e163bc0a51b01a6bbd6a4858
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823319"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="c053f-102">如何：在值 (Visual Basic 中) 创建一个变量，不会更改</span><span class="sxs-lookup"><span data-stu-id="c053f-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>
<span data-ttu-id="c053f-103">不会更改其值的变量的概念可能似乎是矛盾。</span><span class="sxs-lookup"><span data-stu-id="c053f-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="c053f-104">但有些情况下常量不可行时，并可用于具有固定值的变量。</span><span class="sxs-lookup"><span data-stu-id="c053f-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="c053f-105">在这种情况下，你可以定义具有的成员变量[ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="c053f-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
 <span data-ttu-id="c053f-106">不能使用[Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md)来声明和分配在以下情况下的常量值：</span><span class="sxs-lookup"><span data-stu-id="c053f-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>  
  
-   <span data-ttu-id="c053f-107">`Const`语句不接受你想要使用的数据类型</span><span class="sxs-lookup"><span data-stu-id="c053f-107">The `Const` statement does not accept the data type you want to use</span></span>  
  
-   <span data-ttu-id="c053f-108">在编译时不知道值</span><span class="sxs-lookup"><span data-stu-id="c053f-108">You do not know the value at compile time</span></span>  
  
-   <span data-ttu-id="c053f-109">无法在编译时计算的常量值</span><span class="sxs-lookup"><span data-stu-id="c053f-109">You are unable to compute the constant value at compile time</span></span>  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="c053f-110">若要在值中创建一个变量，不会更改</span><span class="sxs-lookup"><span data-stu-id="c053f-110">To create a variable that does not change in value</span></span>  
  
1.  <span data-ttu-id="c053f-111">在模块级别声明的成员变量[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)，并包括[ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="c053f-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     <span data-ttu-id="c053f-112">您可以指定`ReadOnly`仅在成员变量上。</span><span class="sxs-lookup"><span data-stu-id="c053f-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="c053f-113">这意味着您必须定义在模块级别，任何过程之外的变量。</span><span class="sxs-lookup"><span data-stu-id="c053f-113">This means you must define the variable at module level, outside of any procedure.</span></span>  
  
2.  <span data-ttu-id="c053f-114">如果可以计算在编译时的单个语句中的值，使用中的初始化子句`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="c053f-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="c053f-115">请按照[作为](../../../../visual-basic/language-reference/statements/as-clause.md)子句以等号 (`=`) 后, 跟表达式。</span><span class="sxs-lookup"><span data-stu-id="c053f-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="c053f-116">请确保编译器可以计算此表达式为常量值。</span><span class="sxs-lookup"><span data-stu-id="c053f-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     <span data-ttu-id="c053f-117">可以将值赋给`ReadOnly`变量仅一次。</span><span class="sxs-lookup"><span data-stu-id="c053f-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="c053f-118">一旦您这样做，没有代码可以不断更改其值。</span><span class="sxs-lookup"><span data-stu-id="c053f-118">Once you do so, no code can ever change its value.</span></span>  
  
     <span data-ttu-id="c053f-119">如果在编译时，不知道的值或不能在单个语句中的编译时计算，可以仍将其分配在构造函数中的运行时。</span><span class="sxs-lookup"><span data-stu-id="c053f-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="c053f-120">若要执行此操作，必须声明`ReadOnly`变量在类或结构的级别。</span><span class="sxs-lookup"><span data-stu-id="c053f-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="c053f-121">在该类或结构的构造函数，计算该变量的固定的值，并返回从构造函数之前将其分配给该变量。</span><span class="sxs-lookup"><span data-stu-id="c053f-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c053f-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c053f-122">See also</span></span>

- [<span data-ttu-id="c053f-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="c053f-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="c053f-124">Const 语句</span><span class="sxs-lookup"><span data-stu-id="c053f-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
