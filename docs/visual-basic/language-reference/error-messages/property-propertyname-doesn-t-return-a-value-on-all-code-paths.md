---
title: 属性 &#39;&lt;propertyname&gt;&#39; 没有 &#39; 在所有代码路径上返回值的 t
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c9ef5b2ac62412f5684cbc78ab6bebf6bc7b6752
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="317d5-102">属性 &#39;&lt;propertyname&gt;&#39; 没有 &#39; 在所有代码路径上返回值的 t</span><span class="sxs-lookup"><span data-stu-id="317d5-102">Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="317d5-103">属性\<属性名称 > 没有在所有代码路径上返回一个值。</span><span class="sxs-lookup"><span data-stu-id="317d5-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="317d5-104">使用该结果时，可能会在运行时发生 null 引用异常。</span><span class="sxs-lookup"><span data-stu-id="317d5-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="317d5-105">属性`Get`过程有至少一个通过其代码不会返回一个值的可能路径。</span><span class="sxs-lookup"><span data-stu-id="317d5-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="317d5-106">你可以从属性返回一个值`Get`处于以下任一过程：</span><span class="sxs-lookup"><span data-stu-id="317d5-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="317d5-107">将值分配到属性名称，然后执行`Exit Property`语句。</span><span class="sxs-lookup"><span data-stu-id="317d5-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="317d5-108">将值分配到属性名称，然后执行`End Get`语句。</span><span class="sxs-lookup"><span data-stu-id="317d5-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="317d5-109">包括中的值[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="317d5-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="317d5-110">如果控制权传递给`Exit Property`或`End Get`并且你具有未分配到属性名称的任何值`Get`过程返回的属性的数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="317d5-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="317d5-111">有关详细信息，请参阅"行为" [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="317d5-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="317d5-112">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="317d5-112">By default, this message is a warning.</span></span> <span data-ttu-id="317d5-113">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="317d5-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="317d5-114">**错误 ID:** BC42107</span><span class="sxs-lookup"><span data-stu-id="317d5-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="317d5-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="317d5-115">To correct this error</span></span>  
  
-   <span data-ttu-id="317d5-116">请检查控制流逻辑并确保导致返回每个语句之前赋值。</span><span class="sxs-lookup"><span data-stu-id="317d5-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="317d5-117">很容易地保证每个返回从过程返回一个值，如果始终使用`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="317d5-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="317d5-118">如果你这样做，请在之前的最后一个语句`End Get`应`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="317d5-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="317d5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="317d5-119">See Also</span></span>  
 [<span data-ttu-id="317d5-120">属性过程</span><span class="sxs-lookup"><span data-stu-id="317d5-120">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="317d5-121">Property 语句</span><span class="sxs-lookup"><span data-stu-id="317d5-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="317d5-122">Get 语句</span><span class="sxs-lookup"><span data-stu-id="317d5-122">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
