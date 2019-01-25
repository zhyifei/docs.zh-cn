---
title: 属性&#39; &lt;propertyname&gt; &#39;没有&#39;t 上的所有代码路径都返回值
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: b8059ebc9b6c1de685f2f04c3ee362ab8cf6d05e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611249"
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="d2e5b-102">属性&#39; &lt;propertyname&gt; &#39;没有&#39;t 上的所有代码路径都返回值</span><span class="sxs-lookup"><span data-stu-id="d2e5b-102">Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="d2e5b-103">属性 '\<属性名称 > 没有在所有代码路径上返回一个值。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="d2e5b-104">使用该结果时，可能会在运行时发生 null 引用异常。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="d2e5b-105">属性`Get`过程包含至少一个可能不会返回一个值的代码路径。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="d2e5b-106">可以从属性中返回值`Get`处于以下任一过程：</span><span class="sxs-lookup"><span data-stu-id="d2e5b-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="d2e5b-107">将值分配给属性名称，然后执行`Exit Property`语句。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="d2e5b-108">将值分配给属性名称，然后执行`End Get`语句。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="d2e5b-109">包括中的值[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="d2e5b-110">控制权将传递给`Exit Property`或`End Get`并且没有分配任何值的属性名称，`Get`返回属性的数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="d2e5b-111">详细信息，请参阅"行为"中[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="d2e5b-112">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-112">By default, this message is a warning.</span></span> <span data-ttu-id="d2e5b-113">有关隐藏警告或将警告视为错误的详细信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d2e5b-114">**错误 ID:** BC42107</span><span class="sxs-lookup"><span data-stu-id="d2e5b-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d2e5b-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d2e5b-115">To correct this error</span></span>  
  
-   <span data-ttu-id="d2e5b-116">检查控制流逻辑，并确保分配导致返回每个语句前的值。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="d2e5b-117">它是更轻松地保证每个返回从过程返回一个值，如果始终使用`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="d2e5b-118">如果之前的最后一个语句执行此操作，`End Get`应为`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="d2e5b-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e5b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2e5b-119">See also</span></span>
- [<span data-ttu-id="d2e5b-120">属性过程</span><span class="sxs-lookup"><span data-stu-id="d2e5b-120">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="d2e5b-121">Property 语句</span><span class="sxs-lookup"><span data-stu-id="d2e5b-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="d2e5b-122">Get 语句</span><span class="sxs-lookup"><span data-stu-id="d2e5b-122">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
