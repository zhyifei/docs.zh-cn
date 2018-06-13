---
title: 成员类型&#39; &lt;membername&gt; &#39;不符合 CLS
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 5735b5104884a702a649a029116be7446424ec67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595963"
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a><span data-ttu-id="0b9ad-102">成员类型&#39; &lt;membername&gt; &#39;不符合 CLS</span><span class="sxs-lookup"><span data-stu-id="0b9ad-102">Type of member &#39;&lt;membername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="0b9ad-103">为此成员不是指定的数据类型的一部分[语言独立性和独立于语言的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="0b9ad-104">这不是在您的组件，一个错误，因为[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]和 Visual Basic 支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and Visual Basic support this data type.</span></span> <span data-ttu-id="0b9ad-105">但是，在严格符合 cls 的代码中编写的另一个组件可能不支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="0b9ad-106">此类组件可能不能成功与你的组件进行交互。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="0b9ad-107">下面的 Visual Basic 数据类型不符合 cls 的：</span><span class="sxs-lookup"><span data-stu-id="0b9ad-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="0b9ad-108">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="0b9ad-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="0b9ad-109">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="0b9ad-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="0b9ad-110">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="0b9ad-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="0b9ad-111">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="0b9ad-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="0b9ad-112">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-112">By default, this message is a warning.</span></span> <span data-ttu-id="0b9ad-113">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="0b9ad-114">**错误 ID:** BC40025</span><span class="sxs-lookup"><span data-stu-id="0b9ad-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0b9ad-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0b9ad-115">To correct this error</span></span>  
  
-   <span data-ttu-id="0b9ad-116">如果你的组件只与其他接口[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]组件，或者不与任何其他组件之间的接口，您不需要更改任何内容。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="0b9ad-117">如果你没有为编写的组件与交互[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]，你可能能够确定通过反射或从文档，它是否支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="0b9ad-118">如果是这样，你不需要更改任何内容。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="0b9ad-119">如果你与不支持此数据类型的组件交互，你必须将其替换最接近的符合 cls 的类型。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="0b9ad-120">例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="0b9ad-121">如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="0b9ad-122">如果在与自动化或 COM 对象对接，请记住，某些类型具有与 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中不同的数据宽度。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="0b9ad-123">例如，`uint` 在其他环境中通常为 16 位。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="0b9ad-124">如果你的 16 位自变量传递给此类组件，将其声明为`UShort`而不是`UInteger`托管 Visual Basic 代码中。</span><span class="sxs-lookup"><span data-stu-id="0b9ad-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b9ad-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b9ad-125">See Also</span></span>  
 [<span data-ttu-id="0b9ad-126">反射</span><span class="sxs-lookup"><span data-stu-id="0b9ad-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
 
