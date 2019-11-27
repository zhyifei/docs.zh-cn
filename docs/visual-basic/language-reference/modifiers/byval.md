---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: a96f871c6ce119f65ebbec54fdb1471ae105d504
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351587"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="f4581-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4581-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="f4581-103">指定参数[按值](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)传递，因此被调用的过程或属性无法更改调用代码中参数的基础变量的值。</span><span class="sxs-lookup"><span data-stu-id="f4581-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="f4581-104">如果未指定修饰符，则 ByVal 为默认值。</span><span class="sxs-lookup"><span data-stu-id="f4581-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="f4581-105">由于这是默认值，因此不必在方法签名中显式指定 `ByVal` 关键字。</span><span class="sxs-lookup"><span data-stu-id="f4581-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="f4581-106">它往往会产生干扰的代码，通常会导致被忽略的非默认 `ByRef` 关键字。</span><span class="sxs-lookup"><span data-stu-id="f4581-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4581-107">备注</span><span class="sxs-lookup"><span data-stu-id="f4581-107">Remarks</span></span>
 <span data-ttu-id="f4581-108">`ByVal` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="f4581-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="f4581-109">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="f4581-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

 [<span data-ttu-id="f4581-110">Function 语句</span><span class="sxs-lookup"><span data-stu-id="f4581-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [<span data-ttu-id="f4581-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="f4581-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [<span data-ttu-id="f4581-112">Property 语句</span><span class="sxs-lookup"><span data-stu-id="f4581-112">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [<span data-ttu-id="f4581-113">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="f4581-113">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="f4581-114">示例</span><span class="sxs-lookup"><span data-stu-id="f4581-114">Example</span></span>
 <span data-ttu-id="f4581-115">下面的示例演示如何将 `ByVal` 参数传递机制与引用类型参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="f4581-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="f4581-116">在此示例中，参数 `c1`，类 `Class1`的实例。</span><span class="sxs-lookup"><span data-stu-id="f4581-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="f4581-117">`ByVal` 阻止过程中的代码更改 reference 参数的基础值，`c1`，但不保护 `c1`的可访问字段和属性。</span><span class="sxs-lookup"><span data-stu-id="f4581-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="f4581-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4581-118">See also</span></span>

- [<span data-ttu-id="f4581-119">关键字</span><span class="sxs-lookup"><span data-stu-id="f4581-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="f4581-120">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="f4581-120">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
