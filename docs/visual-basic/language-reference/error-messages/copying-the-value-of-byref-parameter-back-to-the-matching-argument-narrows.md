---
title: 将“ByRef”参数“<parametername>”的值复制回匹配的参数将导致从类型“<typename1>”到类型“<typename2>”的收缩转换
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: fa8607bf72dfb344048ec82514182dcb6810274d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817149"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a><span data-ttu-id="bd5ea-102">复制的 ByRef 参数值\<parametername > 返回到匹配的参数用于限制从类型\<typename1 > 类型\<typename2 ></span><span class="sxs-lookup"><span data-stu-id="bd5ea-102">Copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument narrows from type '\<typename1>' to type '\<typename2>'</span></span>
<span data-ttu-id="bd5ea-103">加宽到相应的参数类型，由自变量调用过程时，从参数的参数转换为收缩转换。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="bd5ea-104">在定义类或结构时，可以定义一个或多个转换运算符来将该类或结构类型转换为其他类型。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="bd5ea-105">也可以定义反向转换运算符来将这些其他类型转换回类或结构类型。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="bd5ea-106">当在过程调用中使用你的类或结构类型时，Visual Basic 可以使用这些转换运算符来将自变量的类型转换为其对应的参数类型。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-106">When you use your class or structure type in a procedure call, Visual Basic can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="bd5ea-107">如果传递参数[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 有时会将参数值复制到本地变量中而不是传递一个引用，该过程。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="bd5ea-108">在这种情况下，当过程返回时，Visual Basic 必须然后将本地变量值复制回调用代码中的参数。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-108">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="bd5ea-109">如果将 `ByRef` 实参值复制到过程中，并且实参与形参为同一类型，则不必进行转换。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="bd5ea-110">但如果类型不同，必须将 Visual Basic 转换两个方向。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-110">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="bd5ea-111">如果你的类或结构类型的类型之一，Visual Basic 必须将其转换到和从其他类型。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-111">If one of the types is your class or structure type, Visual Basic must convert it both to and from the other type.</span></span> <span data-ttu-id="bd5ea-112">如果其中一个这些转换扩大转换，则可能会收缩反向转换。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="bd5ea-113">**错误 ID:** BC32053</span><span class="sxs-lookup"><span data-stu-id="bd5ea-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bd5ea-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bd5ea-114">To correct this error</span></span>  
  
-   <span data-ttu-id="bd5ea-115">如果可能，请与过程参数，使用相同类型的调用参数，因此 Visual Basic 不需要执行任何转换。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-115">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="bd5ea-116">如果需要调用实参类型与形参类型不同的过程，但不需要将值返回到调用实参中，请将形参定义为 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 而不是 `ByRef`。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="bd5ea-117">如果你需要将值返回到调用的参数，定义反向转换运算符用作[Widening](../../../visual-basic/language-reference/modifiers/widening.md)如有可能。</span><span class="sxs-lookup"><span data-stu-id="bd5ea-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5ea-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd5ea-118">See also</span></span>

- [<span data-ttu-id="bd5ea-119">过程</span><span class="sxs-lookup"><span data-stu-id="bd5ea-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="bd5ea-120">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="bd5ea-120">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="bd5ea-121">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="bd5ea-121">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="bd5ea-122">运算符过程</span><span class="sxs-lookup"><span data-stu-id="bd5ea-122">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="bd5ea-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="bd5ea-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="bd5ea-124">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="bd5ea-124">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="bd5ea-125">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="bd5ea-125">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="bd5ea-126">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="bd5ea-126">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="bd5ea-127">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="bd5ea-127">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
