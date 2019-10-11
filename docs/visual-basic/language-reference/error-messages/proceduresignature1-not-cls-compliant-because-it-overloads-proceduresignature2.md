---
title: <proceduresignature1> 不符合 CLS，因为它重载仅在数组参数类型的数组或数组参数类型的秩方面与它不同的 <proceduresignature2>
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 6143ebfbe7f131b0e196e531ed4282c8333be4ea
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250173"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="f7781-102">\<proceduresignature1 > 不符合 CLS，因为它重载了 \<proceduresignature2 >，后者仅与数组参数类型的数组或数组参数类型的秩不同</span><span class="sxs-lookup"><span data-stu-id="f7781-102">\<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>

<span data-ttu-id="f7781-103">如果过程或属性重写另一个过程或属性，并且其参数列表之间的唯一区别是交错数组或数组排名的嵌套级别，则它会被标记为 `<CLSCompliant(True)>`。</span><span class="sxs-lookup"><span data-stu-id="f7781-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>
  
 <span data-ttu-id="f7781-104">在下面的声明中，第二个和第三个声明生成此错误：</span><span class="sxs-lookup"><span data-stu-id="f7781-104">In the following declarations, the second and third declarations generate this error:</span></span>
  
 `Overloads Sub ProcessArray(arrayParam() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam()() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`  
  
 <span data-ttu-id="f7781-105">第二个声明将原始的一维参数 @no__t 更改为数组的数组。</span><span class="sxs-lookup"><span data-stu-id="f7781-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="f7781-106">第三个声明将 `arrayParam` 更改为二维数组（秩为2）。</span><span class="sxs-lookup"><span data-stu-id="f7781-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="f7781-107">虽然 Visual Basic 允许重载只是这些更改之一不同，但这种重载不符合[语言独立性和与语言无关的组件](../../../standard/language-independence-and-language-independent-components.md)（CLS）。</span><span class="sxs-lookup"><span data-stu-id="f7781-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="f7781-108">当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。</span><span class="sxs-lookup"><span data-stu-id="f7781-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="f7781-109">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="f7781-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="f7781-110">如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。</span><span class="sxs-lookup"><span data-stu-id="f7781-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="f7781-111">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="f7781-111">By default, this message is a warning.</span></span> <span data-ttu-id="f7781-112">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="f7781-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f7781-113">**错误 ID：** BC40035</span><span class="sxs-lookup"><span data-stu-id="f7781-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f7781-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f7781-114">To correct this error</span></span>  
  
- <span data-ttu-id="f7781-115">如果你需要 CLS 符合性，请将你的重载定义为与其他方法不同，而不只是此帮助页上提到的更改。</span><span class="sxs-lookup"><span data-stu-id="f7781-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>
- <span data-ttu-id="f7781-116">如果要求重载仅在此帮助页上引用的更改中有所不同，请从其定义中删除 @no__t 0，或将其标记为 `<CLSCompliant(False)>`。</span><span class="sxs-lookup"><span data-stu-id="f7781-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f7781-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7781-117">See also</span></span>

- [<span data-ttu-id="f7781-118">过程重载</span><span class="sxs-lookup"><span data-stu-id="f7781-118">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="f7781-119">重载</span><span class="sxs-lookup"><span data-stu-id="f7781-119">Overloads</span></span>](../modifiers/overloads.md)
