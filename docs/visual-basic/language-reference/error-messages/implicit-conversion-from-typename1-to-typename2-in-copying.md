---
title: 从隐式转换 &#39;&lt;typename1&gt;&#39; 为 &#39;&lt;typename2&gt;&#39; 中复制的值的 &#39;ByRef &#39;参数 &#39;&lt;parametername&gt;&#39; 回匹配的自变量。
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e858b475a816a35d18822643de5a273abe28562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a><span data-ttu-id="bb5bd-102">从隐式转换 &#39;&lt;typename1&gt;&#39; 为 &#39;&lt;typename2&gt;&#39; 中复制的值的 &#39;ByRef &#39;参数 &#39;&lt;parametername&gt;&#39; 回匹配的自变量。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-102">Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument.</span></span>
<span data-ttu-id="bb5bd-103">调用过程时使用[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)比其对应的参数的不同类型自变量。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-103">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="bb5bd-104">如果传递了参数`ByRef`，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]有时会将自变量值复制到本地变量中而不是传递一个引用的过程。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-104">If you pass an argument `ByRef`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="bb5bd-105">在这种情况下，当过程返回时， [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 必须随后将局部变量值复制回调用代码中的参数。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-105">In such a case, when the procedure returns, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="bb5bd-106">如果将 `ByRef` 实参值复制到过程中，并且实参与形参为同一类型，则不必进行转换。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="bb5bd-107">但是，如果类型不同，则必须对 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 进行双向转换。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-107">But if the types are different, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert in both directions.</span></span> <span data-ttu-id="bb5bd-108">因为无法使用`CType`或任何其他转换关键字上过程自变量或参数，这种转换始终是隐式。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="bb5bd-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-109">By default, this message is a warning.</span></span> <span data-ttu-id="bb5bd-110">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="bb5bd-111">**错误 ID:** BC41999</span><span class="sxs-lookup"><span data-stu-id="bb5bd-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bb5bd-112">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bb5bd-112">To correct this error</span></span>  
  
-   <span data-ttu-id="bb5bd-113">如果可能，请使用与过程参数同类型的调用参数，这样 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 就不需要进行任何转换。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-113">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="bb5bd-114">如果你需要使用自变量调用过程类型的参数类型不同，但不是需要将值返回到调用自变量、 参数定义为[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)而不是`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="bb5bd-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5bd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb5bd-115">See Also</span></span>  
 [<span data-ttu-id="bb5bd-116">过程</span><span class="sxs-lookup"><span data-stu-id="bb5bd-116">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="bb5bd-117">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="bb5bd-117">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="bb5bd-118">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="bb5bd-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="bb5bd-119">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="bb5bd-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
