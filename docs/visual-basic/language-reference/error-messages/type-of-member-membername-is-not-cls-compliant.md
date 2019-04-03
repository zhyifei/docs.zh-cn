---
title: 成员“<membername>”的类型不符合 CLS
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 0d87adee65f491f8c968e4ba93cf4b9df03aff85
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842650"
---
# <a name="type-of-member-membername-is-not-cls-compliant"></a><span data-ttu-id="9b99b-102">成员类型\<成员名称 > 不符合 cls 的</span><span class="sxs-lookup"><span data-stu-id="9b99b-102">Type of member '\<membername>' is not CLS-compliant</span></span>
<span data-ttu-id="9b99b-103">为此成员不是指定的数据类型的一部分[语言独立性和与语言无关的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)。</span><span class="sxs-lookup"><span data-stu-id="9b99b-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="9b99b-104">这不是在组件中，一个错误，因为[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]和 Visual Basic 支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="9b99b-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and Visual Basic support this data type.</span></span> <span data-ttu-id="9b99b-105">但是，在严格符合 cls 的代码中编写的另一个组件可能不支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="9b99b-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="9b99b-106">此类组件可能不能成功与您的组件进行交互。</span><span class="sxs-lookup"><span data-stu-id="9b99b-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="9b99b-107">以下 Visual Basic 数据类型不符合 CLS 規格：</span><span class="sxs-lookup"><span data-stu-id="9b99b-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="9b99b-108">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="9b99b-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="9b99b-109">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="9b99b-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="9b99b-110">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="9b99b-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="9b99b-111">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="9b99b-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="9b99b-112">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="9b99b-112">By default, this message is a warning.</span></span> <span data-ttu-id="9b99b-113">有关隐藏警告或将警告视为错误的详细信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="9b99b-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="9b99b-114">**错误 ID:** BC40025</span><span class="sxs-lookup"><span data-stu-id="9b99b-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9b99b-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9b99b-115">To correct this error</span></span>  
  
-   <span data-ttu-id="9b99b-116">如果你的组件接口与其他[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]组件，或者在不与任何其他组件接口中，不需要进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="9b99b-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="9b99b-117">如果你没有为编写的组件与交互[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]，您可能能够确定，请通过反射或从文档中，它是否支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="9b99b-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="9b99b-118">如果是这样，您不需要更改任何内容。</span><span class="sxs-lookup"><span data-stu-id="9b99b-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="9b99b-119">如果你与不支持此数据类型的组件交互，您必须将其替换的最接近的符合 cls 的类型。</span><span class="sxs-lookup"><span data-stu-id="9b99b-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="9b99b-120">例如，如果不需要 2147483647 以上的数值范围，可以使用 `UInteger` 取代 `Integer` 。</span><span class="sxs-lookup"><span data-stu-id="9b99b-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="9b99b-121">如果确实需要更大范围，可以用 `UInteger` 代替 `Long`。</span><span class="sxs-lookup"><span data-stu-id="9b99b-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="9b99b-122">如果在与自动化或 COM 对象对接，请记住，某些类型具有与 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中不同的数据宽度。</span><span class="sxs-lookup"><span data-stu-id="9b99b-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="9b99b-123">例如，`uint` 在其他环境中通常为 16 位。</span><span class="sxs-lookup"><span data-stu-id="9b99b-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="9b99b-124">如果您将 16 位自变量传递给此类组件，将其作为声明`UShort`而不是`UInteger`中托管的 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="9b99b-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b99b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b99b-125">See also</span></span>

- [<span data-ttu-id="9b99b-126">反射</span><span class="sxs-lookup"><span data-stu-id="9b99b-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
