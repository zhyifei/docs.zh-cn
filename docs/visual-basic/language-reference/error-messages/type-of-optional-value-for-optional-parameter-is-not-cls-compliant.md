---
title: "可选值的可选参数的类型&lt;parametername&gt;不符合 cls 的 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- BC40042
- vbc40042
dev_langs:
- VB
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
caps.latest.revision: 8
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
ms.openlocfilehash: 4954c241b7cb704ebb9373d837bb1e51c1b44115
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="type-of-optional-value-for-optional-parameter-ltparameternamegt-is-not-cls-compliant"></a><span data-ttu-id="eea4b-102">可选值的可选参数的类型&lt;parametername&gt;不符合 CLS</span><span class="sxs-lookup"><span data-stu-id="eea4b-102">Type of optional value for optional parameter &lt;parametername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="eea4b-103">一个过程标记为 `<CLSCompliant(True)>`，但声明一个[可选](../../../visual-basic/language-reference/modifiers/optional.md)参数，该参数具有不符合的类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="eea4b-103">A procedure is marked as `<CLSCompliant(True)>` but declares an [Optional](../../../visual-basic/language-reference/modifiers/optional.md) parameter with default value of a noncompliant type.</span></span>  
  
 <span data-ttu-id="eea4b-104">一个过程要符合[语言独立性和与语言无关的组件](https://msdn.microsoft.com/library/12a7a7h3) (CLS)，必须只使用符合 CLS 的类型。</span><span class="sxs-lookup"><span data-stu-id="eea4b-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="eea4b-105">这适用于参数的类型、返回类型及其所有本地变量的类型。</span><span class="sxs-lookup"><span data-stu-id="eea4b-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span> <span data-ttu-id="eea4b-106">也适用于可选参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="eea4b-106">It also applies to the default values of optional parameters.</span></span>  
  
 <span data-ttu-id="eea4b-107">以下 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 数据类型不符合 CLS：</span><span class="sxs-lookup"><span data-stu-id="eea4b-107">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="eea4b-108">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="eea4b-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="eea4b-109">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="eea4b-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="eea4b-110">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="eea4b-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="eea4b-111">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="eea4b-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="eea4b-112">当您将应用<xref:System.CLSCompliantAttribute>属性编程元素中，设置该属性的`isCompliant`至任一参数`True`或`False`来指示符合或不符合性。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="eea4b-112">When you apply the <xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="eea4b-113">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="eea4b-113">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="eea4b-114">如果不适用<xref:System.CLSCompliantAttribute>到元素，它被视为不符合要求。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="eea4b-114">If you do not apply <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="eea4b-115">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="eea4b-115">By default, this message is a warning.</span></span> <span data-ttu-id="eea4b-116">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="eea4b-116">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="eea4b-117">**错误 ID:** BC40042</span><span class="sxs-lookup"><span data-stu-id="eea4b-117">**Error ID:** BC40042</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eea4b-118">更正此错误</span><span class="sxs-lookup"><span data-stu-id="eea4b-118">To correct this error</span></span>  
  
-   <span data-ttu-id="eea4b-119">如果可选参数都必须具有默认值为这种特定类型，请删除<xref:System.CLSCompliantAttribute>。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="eea4b-119">If the optional parameter must have a default value of this particular type, remove <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="eea4b-120">该过程不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="eea4b-120">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="eea4b-121">如果过程必须符合 CLS，则将此默认值的类型改为最接近的符合 CLS 的类型。</span><span class="sxs-lookup"><span data-stu-id="eea4b-121">If the procedure must be CLS-compliant, change the type of this default value to the closest CLS-compliant type.</span></span> <span data-ttu-id="eea4b-122">例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。</span><span class="sxs-lookup"><span data-stu-id="eea4b-122">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="eea4b-123">如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。</span><span class="sxs-lookup"><span data-stu-id="eea4b-123">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="eea4b-124">如果在与自动化或 COM 对象对接，请记住，某些类型具有与 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 中不同的数据宽度。</span><span class="sxs-lookup"><span data-stu-id="eea4b-124">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="eea4b-125">例如，`int` 在其他环境中通常为 16 位。</span><span class="sxs-lookup"><span data-stu-id="eea4b-125">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="eea4b-126">如果接受此类组件中的一个 16 位整数，则在托管的 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 代码中将其声明为 `Short` 而不是 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="eea4b-126">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eea4b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eea4b-127">See Also</span></span>  
 [<span data-ttu-id="eea4b-128">\<PAVE 通过&1;> 编写符合 Cls 的代码</span><span class="sxs-lookup"><span data-stu-id="eea4b-128">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
