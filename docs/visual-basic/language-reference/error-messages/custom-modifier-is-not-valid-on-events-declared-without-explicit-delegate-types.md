---
title: "&#39;自定义 &#39;修饰符声明而无需显式委托类型的事件上无效"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords: BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 844bd033ea05e373b04a04f80777af77179c1263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="5b330-102">&#39;自定义 &#39;修饰符声明而无需显式委托类型的事件上无效</span><span class="sxs-lookup"><span data-stu-id="5b330-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="5b330-103">与不同的非自定义事件，`Custom Event`声明要求`As`子句之后显式指定事件的委托类型的事件名称。</span><span class="sxs-lookup"><span data-stu-id="5b330-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="5b330-104">非自定义事件可以是定义使用`As`子句和显式委托类型，或一个参数列表立即在事件名称。</span><span class="sxs-lookup"><span data-stu-id="5b330-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="5b330-105">**错误 ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="5b330-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5b330-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="5b330-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="5b330-107">定义为自定义事件的委托，它具有相同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="5b330-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="5b330-108">例如，如果`Custom Event`定义了`Custom Event Test(ByVal sender As Object, ByVal i As Integer)`，则对应的委托将如下所示。</span><span class="sxs-lookup"><span data-stu-id="5b330-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  <span data-ttu-id="5b330-109">具有自定义事件的参数列表替换`As`子句，用于指定委托类型。</span><span class="sxs-lookup"><span data-stu-id="5b330-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="5b330-110">继续执行本示例中，`Custom Event`声明将被重写，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5b330-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="5b330-111">示例</span><span class="sxs-lookup"><span data-stu-id="5b330-111">Example</span></span>  
 <span data-ttu-id="5b330-112">此示例声明`Custom Event`，并指定所需`As`用的委托类型的子句。</span><span class="sxs-lookup"><span data-stu-id="5b330-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5b330-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b330-113">See Also</span></span>  
 [<span data-ttu-id="5b330-114">Event 语句</span><span class="sxs-lookup"><span data-stu-id="5b330-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="5b330-115">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="5b330-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="5b330-116">事件</span><span class="sxs-lookup"><span data-stu-id="5b330-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
