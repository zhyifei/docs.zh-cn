---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: de4f67fc5b60de48383a8ca886cff02b03830318
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814158"
---
# <a name="static-visual-basic"></a><span data-ttu-id="6cfca-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cfca-102">Static (Visual Basic)</span></span>
<span data-ttu-id="6cfca-103">指定一个或多个声明的局部变量继续存在，并在其中声明它们的过程终止后保留最新值。</span><span class="sxs-lookup"><span data-stu-id="6cfca-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cfca-104">备注</span><span class="sxs-lookup"><span data-stu-id="6cfca-104">Remarks</span></span>  
 <span data-ttu-id="6cfca-105">通常情况下，在过程中的本地变量将消失就立即停止该过程。</span><span class="sxs-lookup"><span data-stu-id="6cfca-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="6cfca-106">静态变量继续存在，并保留其最新值。</span><span class="sxs-lookup"><span data-stu-id="6cfca-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="6cfca-107">你的代码调用该过程，下一次未重新初始化该变量，并且它仍保留分配给它的最新值。</span><span class="sxs-lookup"><span data-stu-id="6cfca-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="6cfca-108">静态变量将继续存在的类或模块中定义的生存期内。</span><span class="sxs-lookup"><span data-stu-id="6cfca-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="6cfca-109">规则</span><span class="sxs-lookup"><span data-stu-id="6cfca-109">Rules</span></span>  
  
-   <span data-ttu-id="6cfca-110">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="6cfca-110">**Declaration Context.**</span></span> <span data-ttu-id="6cfca-111">可以使用`Static`仅对本地变量。</span><span class="sxs-lookup"><span data-stu-id="6cfca-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="6cfca-112">这意味着声明上下文`Static`变量必须是一个过程或块，在过程中，并且它不能为源文件、 命名空间、 类、 结构或模块。</span><span class="sxs-lookup"><span data-stu-id="6cfca-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="6cfca-113">不能使用`Static`结构过程内。</span><span class="sxs-lookup"><span data-stu-id="6cfca-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
-   <span data-ttu-id="6cfca-114">数据类型的`Static`无法推断局部变量。</span><span class="sxs-lookup"><span data-stu-id="6cfca-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="6cfca-115">有关详细信息，请参阅[本地类型推断](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="6cfca-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
-   <span data-ttu-id="6cfca-116">**组合的修饰符。**</span><span class="sxs-lookup"><span data-stu-id="6cfca-116">**Combined Modifiers.**</span></span> <span data-ttu-id="6cfca-117">不能指定`Static`连同`ReadOnly`， `Shadows`，或`Shared`同一声明中。</span><span class="sxs-lookup"><span data-stu-id="6cfca-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="6cfca-118">行为</span><span class="sxs-lookup"><span data-stu-id="6cfca-118">Behavior</span></span>  
 <span data-ttu-id="6cfca-119">当声明中的静态变量`Shared`过程中，只有一个静态变量副本是可用于整个应用程序。</span><span class="sxs-lookup"><span data-stu-id="6cfca-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="6cfca-120">在调用`Shared`过程的方法是使用类名称，不是指向类的实例的变量。</span><span class="sxs-lookup"><span data-stu-id="6cfca-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="6cfca-121">当声明不是一个过程中的静态变量`Shared`，只有一个变量的副本可为每个类实例。</span><span class="sxs-lookup"><span data-stu-id="6cfca-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="6cfca-122">使用指向类的特定实例的变量调用的非共享过程。</span><span class="sxs-lookup"><span data-stu-id="6cfca-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cfca-123">示例</span><span class="sxs-lookup"><span data-stu-id="6cfca-123">Example</span></span>  
 <span data-ttu-id="6cfca-124">以下示例演示了 `Static` 的用法。</span><span class="sxs-lookup"><span data-stu-id="6cfca-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="6cfca-125">`Static`变量`totalSales`仅一次初始化为 0。</span><span class="sxs-lookup"><span data-stu-id="6cfca-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="6cfca-126">你输入每次`updateSales`，`totalSales`仍具有为其计算的最新值。</span><span class="sxs-lookup"><span data-stu-id="6cfca-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="6cfca-127">`Static`修饰符可用于在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="6cfca-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="6cfca-128">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="6cfca-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="6cfca-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="6cfca-129">See also</span></span>

- [<span data-ttu-id="6cfca-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="6cfca-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="6cfca-131">Shared</span><span class="sxs-lookup"><span data-stu-id="6cfca-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="6cfca-132">在 Visual Basic 中的生存期</span><span class="sxs-lookup"><span data-stu-id="6cfca-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="6cfca-133">变量声明</span><span class="sxs-lookup"><span data-stu-id="6cfca-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="6cfca-134">结构</span><span class="sxs-lookup"><span data-stu-id="6cfca-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6cfca-135">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="6cfca-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="6cfca-136">对象和类</span><span class="sxs-lookup"><span data-stu-id="6cfca-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
