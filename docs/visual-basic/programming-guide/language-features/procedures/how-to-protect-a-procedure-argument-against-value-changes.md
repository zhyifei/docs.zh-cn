---
title: 如何：防止过程参数的值被更改
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: 75c718c83f36e2f0b2c4cfb5504c2d740eaa3520
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347903"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="d6986-102">如何：防止过程自变量的值被更改 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6986-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="d6986-103">如果过程将参数声明为[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 将为过程代码提供对调用代码中参数的基础编程元素的直接引用。</span><span class="sxs-lookup"><span data-stu-id="d6986-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="d6986-104">这允许过程更改调用代码中参数的基础值。</span><span class="sxs-lookup"><span data-stu-id="d6986-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="d6986-105">在某些情况下，调用代码可能需要防止这种更改。</span><span class="sxs-lookup"><span data-stu-id="d6986-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="d6986-106">始终可以通过在过程中声明相应的参数[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) ，来保护参数不受更改。</span><span class="sxs-lookup"><span data-stu-id="d6986-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="d6986-107">如果希望能够在某些情况下更改给定的参数，但不能在其他情况下更改，则可以 `ByRef` 将其声明，并让调用代码确定每个调用中的传递机制。</span><span class="sxs-lookup"><span data-stu-id="d6986-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="d6986-108">为此，可将相应的自变量括在括号中，以便按值传递它，或者不将其括在括号中，以便通过引用传递它。</span><span class="sxs-lookup"><span data-stu-id="d6986-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="d6986-109">有关详细信息，请参阅[如何：强制通过值传递参数](./how-to-force-an-argument-to-be-passed-by-value.md)。</span><span class="sxs-lookup"><span data-stu-id="d6986-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6986-110">示例</span><span class="sxs-lookup"><span data-stu-id="d6986-110">Example</span></span>  
 <span data-ttu-id="d6986-111">下面的示例演示了两个过程，这些过程使用数组变量并对其元素进行操作。</span><span class="sxs-lookup"><span data-stu-id="d6986-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="d6986-112">`increase` 过程只是向每个元素添加一个。</span><span class="sxs-lookup"><span data-stu-id="d6986-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="d6986-113">`replace` 过程将新数组分配给参数 `a()` 然后向每个元素添加一个数组。</span><span class="sxs-lookup"><span data-stu-id="d6986-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="d6986-114">但是，重新分配不会影响调用代码中的基础数组变量。</span><span class="sxs-lookup"><span data-stu-id="d6986-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="d6986-115">第一个 `MsgBox` 调用显示 "增加（n）：11，21，31，41" 之后的 "。</span><span class="sxs-lookup"><span data-stu-id="d6986-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="d6986-116">由于数组 `n` 是引用类型，因此 `increase` 可以更改其成员，即使传递机制是 `ByVal`的。</span><span class="sxs-lookup"><span data-stu-id="d6986-116">Because the array `n` is a reference type, `increase` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="d6986-117">第二个 `MsgBox` 调用显示 "replace （n）：11，21，31，41" 之后的。</span><span class="sxs-lookup"><span data-stu-id="d6986-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="d6986-118">由于 `n` 传递 `ByVal`，`replace` 无法通过向其分配新数组来修改调用代码中的变量 `n`。</span><span class="sxs-lookup"><span data-stu-id="d6986-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="d6986-119">如果 `replace` 创建新的数组实例 `k` 并将其分配给本地变量 `a`，则它将失去调用代码传入的 `n` 的引用。</span><span class="sxs-lookup"><span data-stu-id="d6986-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="d6986-120">当它更改 `a`的成员时，只会影响本地数组 `k`。</span><span class="sxs-lookup"><span data-stu-id="d6986-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="d6986-121">因此，`replace` 不会在调用代码中递增数组 `n` 的值。</span><span class="sxs-lookup"><span data-stu-id="d6986-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="d6986-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="d6986-122">Compile the code</span></span>  
 <span data-ttu-id="d6986-123">Visual Basic 中的默认值是按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="d6986-123">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="d6986-124">但是，将[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字用于每个声明的参数是一种好的编程做法。</span><span class="sxs-lookup"><span data-stu-id="d6986-124">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="d6986-125">这使代码更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="d6986-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6986-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6986-126">See also</span></span>

- [<span data-ttu-id="d6986-127">过程</span><span class="sxs-lookup"><span data-stu-id="d6986-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="d6986-128">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="d6986-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d6986-129">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="d6986-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="d6986-130">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="d6986-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="d6986-131">可修改和不可修改自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="d6986-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="d6986-132">通过值传递自变量和通过引用传递自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="d6986-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="d6986-133">如何：更改过程自变量的值</span><span class="sxs-lookup"><span data-stu-id="d6986-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="d6986-134">如何：强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="d6986-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="d6986-135">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="d6986-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="d6986-136">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="d6986-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
