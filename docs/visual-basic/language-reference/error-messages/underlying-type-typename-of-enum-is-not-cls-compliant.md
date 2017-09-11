---
title: "基础类型&lt;typename&gt;枚举不符合 cls 的 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40032
- bc40032
dev_langs:
- VB
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
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
ms.openlocfilehash: 51628d2232b9e1c89e7fbf931ef0d6602f7cddc9
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="underlying-type-lttypenamegt-of-enum-is-not-cls-compliant"></a><span data-ttu-id="dd286-102">基础类型&lt;typename&gt;枚举不符合 CLS</span><span class="sxs-lookup"><span data-stu-id="dd286-102">Underlying type &lt;typename&gt; of Enum is not CLS-compliant</span></span>
<span data-ttu-id="dd286-103">为此枚举不符合指定的数据类型的一部分[语言独立性和与语言无关的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)。</span><span class="sxs-lookup"><span data-stu-id="dd286-103">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span> <span data-ttu-id="dd286-104">这不是在您的组件，一个错误，因为[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]和[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="dd286-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] and [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] support this data type.</span></span> <span data-ttu-id="dd286-105">但是，在严格符合 cls 的代码中编写的其他组件可能不支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="dd286-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="dd286-106">此类组件可能不能成功进行交互与您的组件。</span><span class="sxs-lookup"><span data-stu-id="dd286-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="dd286-107">以下 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 数据类型不符合 CLS：</span><span class="sxs-lookup"><span data-stu-id="dd286-107">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="dd286-108">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="dd286-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="dd286-109">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="dd286-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="dd286-110">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="dd286-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="dd286-111">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="dd286-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="dd286-112">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="dd286-112">By default, this message is a warning.</span></span> <span data-ttu-id="dd286-113">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="dd286-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="dd286-114">**错误 ID:** BC40032</span><span class="sxs-lookup"><span data-stu-id="dd286-114">**Error ID:** BC40032</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dd286-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="dd286-115">To correct this error</span></span>  
  
-   <span data-ttu-id="dd286-116">如果您的组件接口只与其他[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]组件，或者不与任何其他组件不接口，不需要更改任何内容。</span><span class="sxs-lookup"><span data-stu-id="dd286-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="dd286-117">如果您要与没有为编写组件交互[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]，您可能能够确定，请通过反射或从文档中，它是否支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="dd286-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="dd286-118">如果是这样，您不需要更改任何内容。</span><span class="sxs-lookup"><span data-stu-id="dd286-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="dd286-119">如果您要与不支持此数据类型的组件交互，您必须将其替换最接近的符合 cls 的类型。</span><span class="sxs-lookup"><span data-stu-id="dd286-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="dd286-120">例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。</span><span class="sxs-lookup"><span data-stu-id="dd286-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="dd286-121">如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。</span><span class="sxs-lookup"><span data-stu-id="dd286-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="dd286-122">如果在与自动化或 COM 对象对接，请记住，某些类型具有与 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 中不同的数据宽度。</span><span class="sxs-lookup"><span data-stu-id="dd286-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="dd286-123">例如，`uint` 在其他环境中通常为 16 位。</span><span class="sxs-lookup"><span data-stu-id="dd286-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="dd286-124">如果将一个 16 位参数传递给此类组件，将其声明为`UShort`而不是`UInteger`在托管[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]代码。</span><span class="sxs-lookup"><span data-stu-id="dd286-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd286-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd286-125">See Also</span></span>  
 <span data-ttu-id="dd286-126">[反射](http://msdn.microsoft.com/library/5d1d1bcf-08de-4d0b-97a8-912d17c00f26) </span><span class="sxs-lookup"><span data-stu-id="dd286-126">[Reflection](http://msdn.microsoft.com/library/5d1d1bcf-08de-4d0b-97a8-912d17c00f26) </span></span>  
<span data-ttu-id="dd286-127"> [反射](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775) </span><span class="sxs-lookup"><span data-stu-id="dd286-127"> [Reflection](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775) </span></span>  
<span data-ttu-id="dd286-128"> [\<PAVE 通过&1;> 编写符合 Cls 的代码](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="dd286-128"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
