---
title: "属性 &quot;&lt;propertyname&gt;并非在所有代码路径上都返回值 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
dev_langs:
- VB
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
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
ms.openlocfilehash: 64bacc2a2494160b3f9bbaec0915179f40735ef0
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="d9be6-102">属性 '&lt;propertyname&gt;并非在所有代码路径上都返回值</span><span class="sxs-lookup"><span data-stu-id="d9be6-102">Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="d9be6-103">属性 '\<propertyname&1;> 并非在所有代码路径上都返回值。</span><span class="sxs-lookup"><span data-stu-id="d9be6-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="d9be6-104">使用该结果时，可能会在运行时发生 null 引用异常。</span><span class="sxs-lookup"><span data-stu-id="d9be6-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="d9be6-105">一个属性`Get`过程具有至少一个可能不返回值的代码路径。</span><span class="sxs-lookup"><span data-stu-id="d9be6-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="d9be6-106">可以从属性中返回值`Get`处于以下任一过程︰</span><span class="sxs-lookup"><span data-stu-id="d9be6-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="d9be6-107">将值分配给属性名称，然后执行`Exit Property`语句。</span><span class="sxs-lookup"><span data-stu-id="d9be6-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="d9be6-108">将值分配给属性名称，然后执行`End Get`语句。</span><span class="sxs-lookup"><span data-stu-id="d9be6-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="d9be6-109">中包括值[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d9be6-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="d9be6-110">控制权将传递给`Exit Property`或`End Get`和您没有分配任何值的属性名称，`Get`过程返回的属性的数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="d9be6-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="d9be6-111">详细信息，请参阅"行为"中[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d9be6-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="d9be6-112">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="d9be6-112">By default, this message is a warning.</span></span> <span data-ttu-id="d9be6-113">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="d9be6-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d9be6-114">**错误 ID:** BC42107</span><span class="sxs-lookup"><span data-stu-id="d9be6-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d9be6-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d9be6-115">To correct this error</span></span>  
  
-   <span data-ttu-id="d9be6-116">控制流逻辑检查并确保导致返回每个语句之前赋值。</span><span class="sxs-lookup"><span data-stu-id="d9be6-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="d9be6-117">很容易地保证每一次返回从过程返回一个值，如果始终使用`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="d9be6-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="d9be6-118">如果这样做时之前, 的最后一个语句`End Get`应`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="d9be6-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9be6-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9be6-119">See Also</span></span>  
 <span data-ttu-id="d9be6-120">[属性过程](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="d9be6-120">[Property Procedures](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span></span>  
<span data-ttu-id="d9be6-121"> [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d9be6-121"> [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="d9be6-122"> [Get 语句](../../../visual-basic/language-reference/statements/get-statement.md)</span><span class="sxs-lookup"><span data-stu-id="d9be6-122"> [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)</span></span>
