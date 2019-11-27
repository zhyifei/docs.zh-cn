---
title: 静态
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f020756466888f51298abb423997906ddc7caff7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350762"
---
# <a name="static-visual-basic"></a><span data-ttu-id="38468-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38468-102">Static (Visual Basic)</span></span>
<span data-ttu-id="38468-103">指定一个或多个已声明的局部变量将继续存在，并在其声明过程终止后保留其最新值。</span><span class="sxs-lookup"><span data-stu-id="38468-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38468-104">备注</span><span class="sxs-lookup"><span data-stu-id="38468-104">Remarks</span></span>  
 <span data-ttu-id="38468-105">通常，过程停止后，过程中的局部变量将立即停止存在。</span><span class="sxs-lookup"><span data-stu-id="38468-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="38468-106">静态变量将继续存在并保留其最新值。</span><span class="sxs-lookup"><span data-stu-id="38468-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="38468-107">当你的代码下一次调用该过程时，不会重新初始化该变量，并且它仍保留你分配给它的最新值。</span><span class="sxs-lookup"><span data-stu-id="38468-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="38468-108">静态变量在定义它的类或模块的生存期内继续存在。</span><span class="sxs-lookup"><span data-stu-id="38468-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="38468-109">规则</span><span class="sxs-lookup"><span data-stu-id="38468-109">Rules</span></span>  
  
- <span data-ttu-id="38468-110">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="38468-110">**Declaration Context.**</span></span> <span data-ttu-id="38468-111">只能对本地变量使用 `Static`。</span><span class="sxs-lookup"><span data-stu-id="38468-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="38468-112">这意味着，`Static` 变量的声明上下文必须是过程中的过程或块，而不能是源文件、命名空间、类、结构或模块。</span><span class="sxs-lookup"><span data-stu-id="38468-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="38468-113">不能在结构过程中使用 `Static`。</span><span class="sxs-lookup"><span data-stu-id="38468-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="38468-114">不能推断 `Static` 局部变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="38468-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="38468-115">有关详细信息，请参阅[局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="38468-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="38468-116">**组合修饰符。**</span><span class="sxs-lookup"><span data-stu-id="38468-116">**Combined Modifiers.**</span></span> <span data-ttu-id="38468-117">不能在同一声明中同时指定 `Static` 与 `ReadOnly`、`Shadows`或 `Shared`。</span><span class="sxs-lookup"><span data-stu-id="38468-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="38468-118">行为</span><span class="sxs-lookup"><span data-stu-id="38468-118">Behavior</span></span>  
 <span data-ttu-id="38468-119">如果在 `Shared` 过程中声明静态变量，则整个应用程序只有一个静态变量副本可供使用。</span><span class="sxs-lookup"><span data-stu-id="38468-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="38468-120">使用类名称调用 `Shared` 过程，而不是指向类的实例的变量。</span><span class="sxs-lookup"><span data-stu-id="38468-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="38468-121">如果在不 `Shared`的过程中声明静态变量，则该类的每个实例只能有一个变量副本。</span><span class="sxs-lookup"><span data-stu-id="38468-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="38468-122">使用指向类的特定实例的变量调用非共享过程。</span><span class="sxs-lookup"><span data-stu-id="38468-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38468-123">示例</span><span class="sxs-lookup"><span data-stu-id="38468-123">Example</span></span>  
 <span data-ttu-id="38468-124">以下示例演示了 `Static` 的用法。</span><span class="sxs-lookup"><span data-stu-id="38468-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="38468-125">`Static` 变量 `totalSales` 初始化为0次。</span><span class="sxs-lookup"><span data-stu-id="38468-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="38468-126">每次输入 `updateSales`时，`totalSales` 仍然具有为其计算的最新值。</span><span class="sxs-lookup"><span data-stu-id="38468-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="38468-127">`Static` 修饰符可用于以下上下文：</span><span class="sxs-lookup"><span data-stu-id="38468-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="38468-128">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="38468-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="38468-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38468-129">See also</span></span>

- [<span data-ttu-id="38468-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="38468-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="38468-131">Shared</span><span class="sxs-lookup"><span data-stu-id="38468-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="38468-132">生存期（Visual Basic</span><span class="sxs-lookup"><span data-stu-id="38468-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="38468-133">变量声明</span><span class="sxs-lookup"><span data-stu-id="38468-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="38468-134">结构</span><span class="sxs-lookup"><span data-stu-id="38468-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="38468-135">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="38468-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="38468-136">对象和类</span><span class="sxs-lookup"><span data-stu-id="38468-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
