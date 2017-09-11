---
title: "如何︰ 定义多个版本的过程 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, defining
- Visual Basic code, procedures
- procedures, overloading
- procedures, multiple versions
- procedure overloading, multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
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
ms.openlocfilehash: f4296ba3a78316b70011bcca18f7071716f3c90d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="eb178-102">如何：定义一个过程的多个版本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb178-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="eb178-103">可以通过多个版本中定义的过程*重载*它在每个版本使用相同的名称但不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="eb178-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="eb178-104">重载的目的是定义一个过程的几个密切相关的版本而无需将它们按名称区分开来。</span><span class="sxs-lookup"><span data-stu-id="eb178-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="eb178-105">有关详细信息，请参阅[过程重载](./procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="eb178-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="eb178-106">若要定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="eb178-106">To define multiple versions of a procedure</span></span>  
  
1.  <span data-ttu-id="eb178-107">编写`Sub`或`Function`你想要定义该过程的每个版本的声明语句。</span><span class="sxs-lookup"><span data-stu-id="eb178-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="eb178-108">在每个声明中使用相同的过程名称。</span><span class="sxs-lookup"><span data-stu-id="eb178-108">Use the same procedure name in every declaration.</span></span>  
  
2.  <span data-ttu-id="eb178-109">在前面上`Sub`或`Function`关键字在与每个声明[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="eb178-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="eb178-110">（可选） 可以省略`Overloads`在声明中，但如果您将其包括在任何声明，您必须将其包括在每个声明。</span><span class="sxs-lookup"><span data-stu-id="eb178-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3.  <span data-ttu-id="eb178-111">后面每个声明语句中，编写过程代码以处理调用的代码提供了该版本的参数列表匹配的参数的特定情况。</span><span class="sxs-lookup"><span data-stu-id="eb178-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="eb178-112">无需测试提供的参数调用的代码具有控制权。</span><span class="sxs-lookup"><span data-stu-id="eb178-112">You do not have to test for which parameters the calling code has supplied.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="eb178-113">将控制权传递给您的过程中匹配的版本。</span><span class="sxs-lookup"><span data-stu-id="eb178-113"> passes control to the matching version of your procedure.</span></span>  
  
4.  <span data-ttu-id="eb178-114">终止与该过程的每个版本`End Sub`或`End Function`根据语句。</span><span class="sxs-lookup"><span data-stu-id="eb178-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb178-115">示例</span><span class="sxs-lookup"><span data-stu-id="eb178-115">Example</span></span>  
 <span data-ttu-id="eb178-116">下面的示例定义`Sub`过程来针对客户的帐户余额发送一个事务。</span><span class="sxs-lookup"><span data-stu-id="eb178-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="eb178-117">它使用`Overloads`关键字来定义两个版本的过程中，一个接受按帐户名称和其他客户。</span><span class="sxs-lookup"><span data-stu-id="eb178-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 <span data-ttu-id="eb178-118">[!code-vb[VbVbcnProcedures #&72;](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="eb178-118">[!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]</span></span>  
  
 <span data-ttu-id="eb178-119">调用代码可以获取客户标识为`String`或`Integer`，然后在任一情况下使用相同的调用语句。</span><span class="sxs-lookup"><span data-stu-id="eb178-119">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="eb178-120">有关如何以调用这些版本的信息`post`的过程中，请参阅[如何︰ 调用重载过程](./how-to-call-an-overloaded-procedure.md)。</span><span class="sxs-lookup"><span data-stu-id="eb178-120">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eb178-121">编译代码</span><span class="sxs-lookup"><span data-stu-id="eb178-121">Compiling the Code</span></span>  
 <span data-ttu-id="eb178-122">请确保每个重载版本具有相同的过程名称但不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="eb178-122">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb178-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb178-123">See Also</span></span>  
 <span data-ttu-id="eb178-124">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="eb178-124">[Procedures](./index.md) </span></span>  
<span data-ttu-id="eb178-125"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="eb178-125"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="eb178-126"> [故障排除过程](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="eb178-126"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="eb178-127"> [如何︰ 重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="eb178-127"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="eb178-128"> [如何︰ 重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="eb178-128"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="eb178-129"> [重载过程注意事项](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="eb178-129"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="eb178-130"> [重载决策](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="eb178-130"> [Overload Resolution](./overload-resolution.md)</span></span>
