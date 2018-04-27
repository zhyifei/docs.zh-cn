---
title: 参数类型&#39; &lt;parametername&gt; &#39;不符合 CLS
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d34de9e5914b02a0e878b87e786b81a5940a6d85
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="type-of-parameter-39ltparameternamegt39-is-not-cls-compliant"></a><span data-ttu-id="84cf3-102">参数类型&#39; &lt;parametername&gt; &#39;不符合 CLS</span><span class="sxs-lookup"><span data-stu-id="84cf3-102">Type of parameter &#39;&lt;parametername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="84cf3-103">一个过程标记为`<CLSCompliant(True)>`但具有标记为的类型声明参数`<CLSCompliant(False)>`、 未标记，或不合格，因为它是不符合要求的类型。</span><span class="sxs-lookup"><span data-stu-id="84cf3-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="84cf3-104">一个过程要符合[语言独立性和与语言无关的组件](../../../standard/language-independence-and-language-independent-components.md) (CLS)，必须只使用符合 CLS 的类型。</span><span class="sxs-lookup"><span data-stu-id="84cf3-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="84cf3-105">这适用于参数的类型、返回类型及其所有本地变量的类型。</span><span class="sxs-lookup"><span data-stu-id="84cf3-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="84cf3-106">下面的 Visual Basic 数据类型不符合 cls 的：</span><span class="sxs-lookup"><span data-stu-id="84cf3-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="84cf3-107">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="84cf3-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="84cf3-108">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="84cf3-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="84cf3-109">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="84cf3-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="84cf3-110">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="84cf3-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="84cf3-111">当将 <xref:System.CLSCompliantAttribute> 应用到编程元素中时，需要将该特性的 `isCompliant` 参数设置为 `True` 或 `False` 来指示符合或不符合性。</span><span class="sxs-lookup"><span data-stu-id="84cf3-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="84cf3-112">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="84cf3-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="84cf3-113">如果不将 <xref:System.CLSCompliantAttribute> 应用到元素，则它将被视为不符合规范。</span><span class="sxs-lookup"><span data-stu-id="84cf3-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="84cf3-114">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="84cf3-114">By default, this message is a warning.</span></span> <span data-ttu-id="84cf3-115">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="84cf3-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="84cf3-116">**错误 ID:** BC40028</span><span class="sxs-lookup"><span data-stu-id="84cf3-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="84cf3-117">更正此错误</span><span class="sxs-lookup"><span data-stu-id="84cf3-117">To correct this error</span></span>  
  
-   <span data-ttu-id="84cf3-118">如果该过程必须采用这种特定类型的参数，请删除<xref:System.CLSCompliantAttribute>。</span><span class="sxs-lookup"><span data-stu-id="84cf3-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="84cf3-119">该过程不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="84cf3-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="84cf3-120">如果该过程必须符合 CLS，更改此参数的类型为最接近的符合 cls 的类型。</span><span class="sxs-lookup"><span data-stu-id="84cf3-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="84cf3-121">例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。</span><span class="sxs-lookup"><span data-stu-id="84cf3-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="84cf3-122">如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。</span><span class="sxs-lookup"><span data-stu-id="84cf3-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="84cf3-123">如果在与自动化或 COM 对象对接，请记住，某些类型具有与 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中不同的数据宽度。</span><span class="sxs-lookup"><span data-stu-id="84cf3-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="84cf3-124">例如，`int` 在其他环境中通常为 16 位。</span><span class="sxs-lookup"><span data-stu-id="84cf3-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="84cf3-125">如果你接受来自此类组件的 16 位整数，将其声明为`Short`而不是`Integer`托管 Visual Basic 代码中。</span><span class="sxs-lookup"><span data-stu-id="84cf3-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>