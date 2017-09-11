---
title: "参数的类型 &quot;&lt;parametername&gt;&quot; 不是符合 cls 的 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40028
- bc40028
dev_langs:
- VB
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
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
ms.openlocfilehash: 25392d9855b44d9f82157601648384955951475e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="type-of-parameter-39ltparameternamegt39-is-not-cls-compliant"></a><span data-ttu-id="ebd91-102">参数的类型 '&lt;parametername&gt;' 不是符合 CLS</span><span class="sxs-lookup"><span data-stu-id="ebd91-102">Type of parameter &#39;&lt;parametername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="ebd91-103">过程标记为`<CLSCompliant(True)>`但被标记为的类型声明参数`<CLSCompliant(False)>`、 没有被标记，或不合格，因为它是不符合要求的类型。</span><span class="sxs-lookup"><span data-stu-id="ebd91-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="ebd91-104">一个过程要符合[语言独立性和与语言无关的组件](https://msdn.microsoft.com/library/12a7a7h3) (CLS)，必须只使用符合 CLS 的类型。</span><span class="sxs-lookup"><span data-stu-id="ebd91-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="ebd91-105">这适用于参数的类型、返回类型及其所有本地变量的类型。</span><span class="sxs-lookup"><span data-stu-id="ebd91-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="ebd91-106">以下 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 数据类型不符合 CLS：</span><span class="sxs-lookup"><span data-stu-id="ebd91-106">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="ebd91-107">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="ebd91-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="ebd91-108">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="ebd91-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="ebd91-109">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="ebd91-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="ebd91-110">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="ebd91-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="ebd91-111">当您将应用<xref:System.CLSCompliantAttribute>编程元素中，设置该属性的`isCompliant`至任一参数`True`或`False`来指示符合或不符合性。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="ebd91-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="ebd91-112">此参数没有默认值，必须为其提供一个值。</span><span class="sxs-lookup"><span data-stu-id="ebd91-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="ebd91-113">如果不适用<xref:System.CLSCompliantAttribute>到元素，它被视为不符合要求。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="ebd91-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="ebd91-114">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="ebd91-114">By default, this message is a warning.</span></span> <span data-ttu-id="ebd91-115">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="ebd91-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ebd91-116">**错误 ID:** BC40028</span><span class="sxs-lookup"><span data-stu-id="ebd91-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ebd91-117">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ebd91-117">To correct this error</span></span>  
  
-   <span data-ttu-id="ebd91-118">如果该过程必须采用这种特定类型的参数，请删除<xref:System.CLSCompliantAttribute>。</xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="ebd91-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="ebd91-119">该过程不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="ebd91-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="ebd91-120">如果该过程必须符合 CLS，则为最接近的符合 cls 的类型更改此参数的类型。</span><span class="sxs-lookup"><span data-stu-id="ebd91-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="ebd91-121">例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。</span><span class="sxs-lookup"><span data-stu-id="ebd91-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="ebd91-122">如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。</span><span class="sxs-lookup"><span data-stu-id="ebd91-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="ebd91-123">如果在与自动化或 COM 对象对接，请记住，某些类型具有与 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 中不同的数据宽度。</span><span class="sxs-lookup"><span data-stu-id="ebd91-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="ebd91-124">例如，`int` 在其他环境中通常为 16 位。</span><span class="sxs-lookup"><span data-stu-id="ebd91-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="ebd91-125">如果接受此类组件中的一个 16 位整数，则在托管的 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 代码中将其声明为 `Short` 而不是 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="ebd91-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebd91-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebd91-126">See Also</span></span>  
 [<span data-ttu-id="ebd91-127">\<PAVE 通过&1;> 编写符合 Cls 的代码</span><span class="sxs-lookup"><span data-stu-id="ebd91-127">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
