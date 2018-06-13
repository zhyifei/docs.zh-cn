---
title: 如何：创建固定值变量 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d63c254abe6d12c094e0d1252c9721f668947f09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651371"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="7fa87-102">如何：创建固定值变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fa87-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>
<span data-ttu-id="7fa87-103">不会更改其值的变量的概念可能看起来有点矛盾。</span><span class="sxs-lookup"><span data-stu-id="7fa87-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="7fa87-104">在一些情况下不可行常量时，但它可用于具有固定值的变量。</span><span class="sxs-lookup"><span data-stu-id="7fa87-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="7fa87-105">在这种情况下，你可以定义具有的成员变量[ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="7fa87-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
 <span data-ttu-id="7fa87-106">不能使用[Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md)声明和分配常量值在以下情况下：</span><span class="sxs-lookup"><span data-stu-id="7fa87-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>  
  
-   <span data-ttu-id="7fa87-107">`Const`语句不接受你想要使用的数据类型</span><span class="sxs-lookup"><span data-stu-id="7fa87-107">The `Const` statement does not accept the data type you want to use</span></span>  
  
-   <span data-ttu-id="7fa87-108">在编译时不知道值</span><span class="sxs-lookup"><span data-stu-id="7fa87-108">You do not know the value at compile time</span></span>  
  
-   <span data-ttu-id="7fa87-109">无法在编译时计算的常量值</span><span class="sxs-lookup"><span data-stu-id="7fa87-109">You are unable to compute the constant value at compile time</span></span>  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="7fa87-110">若要在值中创建一个变量，不会更改</span><span class="sxs-lookup"><span data-stu-id="7fa87-110">To create a variable that does not change in value</span></span>  
  
1.  <span data-ttu-id="7fa87-111">在模块级别声明的成员变量[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)，并且包括[ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="7fa87-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     <span data-ttu-id="7fa87-112">你可以指定`ReadOnly`仅在成员变量上。</span><span class="sxs-lookup"><span data-stu-id="7fa87-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="7fa87-113">这意味着你必须定义在模块级别，在任何过程之外的变量。</span><span class="sxs-lookup"><span data-stu-id="7fa87-113">This means you must define the variable at module level, outside of any procedure.</span></span>  
  
2.  <span data-ttu-id="7fa87-114">如果可以计算在编译时的单个语句中的值，使用中的初始化子句`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="7fa87-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="7fa87-115">请按照[作为](../../../../visual-basic/language-reference/statements/as-clause.md)子句以等号 (`=`) 后, 跟表达式。</span><span class="sxs-lookup"><span data-stu-id="7fa87-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="7fa87-116">请确保编译器可以计算此表达式与一个常数值。</span><span class="sxs-lookup"><span data-stu-id="7fa87-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     <span data-ttu-id="7fa87-117">你可以将值赋给`ReadOnly`变量一次。</span><span class="sxs-lookup"><span data-stu-id="7fa87-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="7fa87-118">这么做后，没有代码可以更改其值。</span><span class="sxs-lookup"><span data-stu-id="7fa87-118">Once you do so, no code can ever change its value.</span></span>  
  
     <span data-ttu-id="7fa87-119">如果你在编译时，不知道值或不能在单个语句中的编译时计算，可以仍将其分配在构造函数中的运行时。</span><span class="sxs-lookup"><span data-stu-id="7fa87-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="7fa87-120">若要执行此操作，您必须声明`ReadOnly`变量在类或结构的级别。</span><span class="sxs-lookup"><span data-stu-id="7fa87-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="7fa87-121">在该类或结构的构造函数，计算变量的固定的值，并在返回从构造函数之前将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="7fa87-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa87-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="7fa87-122">See Also</span></span>  
 [<span data-ttu-id="7fa87-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="7fa87-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [<span data-ttu-id="7fa87-124">Const 语句</span><span class="sxs-lookup"><span data-stu-id="7fa87-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
