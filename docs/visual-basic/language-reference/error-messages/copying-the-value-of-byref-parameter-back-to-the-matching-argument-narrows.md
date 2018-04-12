---
title: 复制的值的 &#39;ByRef &#39;参数 &#39;&lt;parametername&gt;&#39; 回匹配自变量缩小从类型 &#39;&lt;typename1&gt;&#39; 类型 &#39;&lt;typename2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4bf993639007162e2e17d4b8cb9dfe8d5316acaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="72c3c-102">复制的值的 &#39;ByRef &#39;参数 &#39;&lt;parametername&gt;&#39; 回匹配自变量缩小从类型 &#39;&lt;typename1&gt;&#39; 类型 &#39;&lt;typename2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="72c3c-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="72c3c-103">调用过程时使用的自变量扩大到相应的参数类型，并从参数到自变量转换为收缩转换。</span><span class="sxs-lookup"><span data-stu-id="72c3c-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="72c3c-104">在定义类或结构时，可以定义一个或多个转换运算符来将该类或结构类型转换为其他类型。</span><span class="sxs-lookup"><span data-stu-id="72c3c-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="72c3c-105">也可以定义反向转换运算符来将这些其他类型转换回类或结构类型。</span><span class="sxs-lookup"><span data-stu-id="72c3c-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="72c3c-106">当在过程调用中使用你的类或结构类型时， [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 可以使用这些转换运算符将参数的类型转换为其对应的参数的类型。</span><span class="sxs-lookup"><span data-stu-id="72c3c-106">When you use your class or structure type in a procedure call, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="72c3c-107">如果传递参数[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]有时会将自变量值复制到本地变量中而不是传递一个引用的过程。</span><span class="sxs-lookup"><span data-stu-id="72c3c-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="72c3c-108">在这种情况下，当过程返回时， [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 必须随后将局部变量值复制回调用代码中的参数。</span><span class="sxs-lookup"><span data-stu-id="72c3c-108">In such a case, when the procedure returns, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="72c3c-109">如果将 `ByRef` 实参值复制到过程中，并且实参与形参为同一类型，则不必进行转换。</span><span class="sxs-lookup"><span data-stu-id="72c3c-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="72c3c-110">但是，如果类型不同，则必须对 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 进行双向转换。</span><span class="sxs-lookup"><span data-stu-id="72c3c-110">But if the types are different, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert in both directions.</span></span> <span data-ttu-id="72c3c-111">如果其中一个类型是你的类或结构类型，则 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 就必须在该类型与其他类型之间进行双向转换。</span><span class="sxs-lookup"><span data-stu-id="72c3c-111">If one of the types is your class or structure type, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert it both to and from the other type.</span></span> <span data-ttu-id="72c3c-112">如果这些转换之一扩大转换，则可能收缩反向转换。</span><span class="sxs-lookup"><span data-stu-id="72c3c-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="72c3c-113">**错误 ID:** BC32053</span><span class="sxs-lookup"><span data-stu-id="72c3c-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72c3c-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="72c3c-114">To correct this error</span></span>  
  
-   <span data-ttu-id="72c3c-115">如果可能，请使用与过程参数同类型的调用参数，这样 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 就不需要进行任何转换。</span><span class="sxs-lookup"><span data-stu-id="72c3c-115">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="72c3c-116">如果你需要使用自变量调用过程类型的参数类型不同，但不是需要将值返回到调用自变量、 参数定义为[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)而不是`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="72c3c-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="72c3c-117">如果你需要将值返回到调用自变量，定义反向转换运算符用作[Widening](../../../visual-basic/language-reference/modifiers/widening.md)如果可能。</span><span class="sxs-lookup"><span data-stu-id="72c3c-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c3c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72c3c-118">See Also</span></span>  
 [<span data-ttu-id="72c3c-119">过程</span><span class="sxs-lookup"><span data-stu-id="72c3c-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="72c3c-120">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="72c3c-120">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="72c3c-121">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="72c3c-121">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="72c3c-122">运算符过程</span><span class="sxs-lookup"><span data-stu-id="72c3c-122">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="72c3c-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="72c3c-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="72c3c-124">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="72c3c-124">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="72c3c-125">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="72c3c-125">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="72c3c-126">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="72c3c-126">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="72c3c-127">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="72c3c-127">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
