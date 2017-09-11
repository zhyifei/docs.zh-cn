---
title: "&lt;proceduresignature1&gt;因为它重载不符合 cls 的&lt;proceduresignature2&gt;与它不同的只能通过数组参数类型的数组或通过数组参数类型的秩方面 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
dev_langs:
- VB
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d106f59e3faa317f67ee92ddcec8416eeff745d4
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="94a49-102">&lt;proceduresignature1&gt;因为它重载不符合 cls 的&lt;proceduresignature2&gt;与它不同的只能通过数组参数类型的数组或通过数组参数类型的秩方面</span><span class="sxs-lookup"><span data-stu-id="94a49-102">&lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="94a49-103">过程或属性被标记为`<CLSCompliant(True)>`时它会替代另一个过程或属性以及它们的参数列表的唯一区别是交错数组的嵌套级别还是数组的秩。</span><span class="sxs-lookup"><span data-stu-id="94a49-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="94a49-104">在下面的声明中，在第二个和第三个声明生成此错误。</span><span class="sxs-lookup"><span data-stu-id="94a49-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="94a49-105">第二个声明更改原始的一维参数`arrayParam`到数组的数组。</span><span class="sxs-lookup"><span data-stu-id="94a49-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="94a49-106">第三个声明的更改`arrayParam`为二维数组 （级别 2）。</span><span class="sxs-lookup"><span data-stu-id="94a49-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="94a49-107">尽管 Visual Basic 允许重载，可只是某项更改不同，这种过载不符合[语言独立性和与语言无关的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)。</span><span class="sxs-lookup"><span data-stu-id="94a49-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span>  
  
 <span data-ttu-id="94a49-108">当您将应用<xref:System.CLSCompliantAttribute>编程元素中，设置该属性的`isCompliant`至任一参数`True`或`False`来指示符合或不符合性。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="94a49-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="94a49-109">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="94a49-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="94a49-110">如果不适用<xref:System.CLSCompliantAttribute>到元素，它被视为不符合要求。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="94a49-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="94a49-111">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="94a49-111">By default, this message is a warning.</span></span> <span data-ttu-id="94a49-112">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="94a49-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="94a49-113">**错误 ID:** BC40035</span><span class="sxs-lookup"><span data-stu-id="94a49-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="94a49-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="94a49-114">To correct this error</span></span>  
  
-   <span data-ttu-id="94a49-115">如果您需要 CLS 遵从性，对重载进行定义在比仅引用此帮助页上的更改的更多方面不同于彼此。</span><span class="sxs-lookup"><span data-stu-id="94a49-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
-   <span data-ttu-id="94a49-116">如果你需要重载的区别仅由所做的更改引用此帮助页上，删除<xref:System.CLSCompliantAttribute>于它们的定义或将其标记为`<CLSCompliant(False)>`。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="94a49-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a49-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94a49-117">See Also</span></span>  
 <span data-ttu-id="94a49-118">[\<PAVE 通过&1;> 编写符合 Cls 的代码](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3) </span><span class="sxs-lookup"><span data-stu-id="94a49-118">[\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3) </span></span>  
<span data-ttu-id="94a49-119"> [过程重载](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="94a49-119"> [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md) </span></span>  
<span data-ttu-id="94a49-120"> [重载](../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="94a49-120"> [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
