---
title: '&lt;proceduresignature1&gt;因为它重载不符合 CLS 規格&lt;proceduresignature2&gt;与它不同的仅通过数组参数类型的数组或数组参数类型的秩'
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 0f4eaa09c3d04af350637fba0d672f55040a6466
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626844"
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="e8ea1-102">&lt;proceduresignature1&gt;因为它重载不符合 CLS 規格&lt;proceduresignature2&gt;与它不同的仅通过数组参数类型的数组或数组参数类型的秩</span><span class="sxs-lookup"><span data-stu-id="e8ea1-102">&lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="e8ea1-103">过程或属性被标记为`<CLSCompliant(True)>`时它将替代另一个过程或属性，而且它们的参数列表之间的唯一区别是交错数组的嵌套级别或数组的秩。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="e8ea1-104">在以下声明中，第二个和第三个声明生成此错误。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="e8ea1-105">第二个声明更改原始的一维参数`arrayParam`到数组的数组。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="e8ea1-106">第三个声明更改`arrayParam`到二维数组 （级别 2）。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="e8ea1-107">尽管 Visual Basic 允许重载，可只是某项更改不同，此类重载不符合[语言独立性和与语言无关的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="e8ea1-108">当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="e8ea1-109">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="e8ea1-110">如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="e8ea1-111">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-111">By default, this message is a warning.</span></span> <span data-ttu-id="e8ea1-112">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e8ea1-113">**错误 ID:** BC40035</span><span class="sxs-lookup"><span data-stu-id="e8ea1-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e8ea1-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e8ea1-114">To correct this error</span></span>  
  
-   <span data-ttu-id="e8ea1-115">如果你需要 CLS 遵从性，定义在重载，可通过比仅引用此帮助页上的更改的更多方式彼此不同。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
-   <span data-ttu-id="e8ea1-116">如果你需要重载的区别仅由所做的更改引用上此帮助页上，删除<xref:System.CLSCompliantAttribute>与其定义或将其作为标记`<CLSCompliant(False)>`。</span><span class="sxs-lookup"><span data-stu-id="e8ea1-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ea1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8ea1-117">See also</span></span>

- [<span data-ttu-id="e8ea1-118">过程重载</span><span class="sxs-lookup"><span data-stu-id="e8ea1-118">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="e8ea1-119">重载</span><span class="sxs-lookup"><span data-stu-id="e8ea1-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
