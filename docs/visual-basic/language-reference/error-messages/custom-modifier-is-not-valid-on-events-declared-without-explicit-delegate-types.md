---
title: “Custom”修饰符在未用显式委托类型声明的事件上无效
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: c1b57ccdaa9e04c837ecf7572bc164683a934b2d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273512"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="63a2d-102">“Custom”修饰符在未用显式委托类型声明的事件上无效</span><span class="sxs-lookup"><span data-stu-id="63a2d-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="63a2d-103">与不同的非自定义事件`Custom Event`声明要求`As`子句显式指定该事件的委托类型的事件名称后。</span><span class="sxs-lookup"><span data-stu-id="63a2d-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="63a2d-104">非自定义事件可以是定义使用`As`子句和显式委托类型，或一个参数列表立即在事件名称。</span><span class="sxs-lookup"><span data-stu-id="63a2d-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="63a2d-105">**错误 ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="63a2d-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="63a2d-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="63a2d-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="63a2d-107">定义为自定义事件的委托，它具有相同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="63a2d-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="63a2d-108">例如，如果`Custom Event`定义的`Custom Event Test(ByVal sender As Object, ByVal i As Integer)`，则对应的委托将如下所示。</span><span class="sxs-lookup"><span data-stu-id="63a2d-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  <span data-ttu-id="63a2d-109">自定义事件的参数列表替换`As`子句，用于指定委托类型。</span><span class="sxs-lookup"><span data-stu-id="63a2d-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="63a2d-110">继续执行该示例中，`Custom Event`声明将被重写，如下所示。</span><span class="sxs-lookup"><span data-stu-id="63a2d-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="63a2d-111">示例</span><span class="sxs-lookup"><span data-stu-id="63a2d-111">Example</span></span>  
 <span data-ttu-id="63a2d-112">此示例中声明`Custom Event`，并指定所需`As`与委托类型的子句。</span><span class="sxs-lookup"><span data-stu-id="63a2d-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="63a2d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="63a2d-113">See also</span></span>
- [<span data-ttu-id="63a2d-114">Event 语句</span><span class="sxs-lookup"><span data-stu-id="63a2d-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="63a2d-115">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="63a2d-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="63a2d-116">事件</span><span class="sxs-lookup"><span data-stu-id="63a2d-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
