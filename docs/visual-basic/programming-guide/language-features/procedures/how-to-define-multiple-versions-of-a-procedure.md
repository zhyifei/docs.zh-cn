---
title: 如何：定义多个版本的过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: c31c9ad05af04aec5dc41790aea530c62611f500
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841160"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="55633-102">如何：定义多个版本的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55633-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="55633-103">你可以通过多个版本中定义的过程*重载*它为每个版本使用相同名称但不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="55633-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="55633-104">重载的目的是定义一个过程的几个密切相关的版本而无需将它们按名称区分开。</span><span class="sxs-lookup"><span data-stu-id="55633-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="55633-105">有关更多信息，请参见 [Procedure Overloading](./procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="55633-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="55633-106">若要定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="55633-106">To define multiple versions of a procedure</span></span>  
  
1.  <span data-ttu-id="55633-107">编写`Sub`或`Function`你想要定义的过程的每个版本的声明语句。</span><span class="sxs-lookup"><span data-stu-id="55633-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="55633-108">在每个声明中使用相同的过程名称。</span><span class="sxs-lookup"><span data-stu-id="55633-108">Use the same procedure name in every declaration.</span></span>  
  
2.  <span data-ttu-id="55633-109">前加上`Sub`或`Function`具有每个声明中的关键字[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="55633-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="55633-110">可以选择性地省略`Overloads`在声明中，但如果您将其包含在任何声明，您必须将其包括在每个声明。</span><span class="sxs-lookup"><span data-stu-id="55633-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3.  <span data-ttu-id="55633-111">以下每个声明语句中，编写过程代码以处理其中调用代码提供该版本的参数列表匹配的实参的特定情况。</span><span class="sxs-lookup"><span data-stu-id="55633-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="55633-112">无需测试提供的参数调用的代码具有控制权。</span><span class="sxs-lookup"><span data-stu-id="55633-112">You do not have to test for which parameters the calling code has supplied.</span></span> <span data-ttu-id="55633-113">Visual Basic 将控制传递给您的过程的匹配版本。</span><span class="sxs-lookup"><span data-stu-id="55633-113">Visual Basic passes control to the matching version of your procedure.</span></span>  
  
4.  <span data-ttu-id="55633-114">终止与过程的每个版本`End Sub`或`End Function`语句作为相应。</span><span class="sxs-lookup"><span data-stu-id="55633-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55633-115">示例</span><span class="sxs-lookup"><span data-stu-id="55633-115">Example</span></span>  
 <span data-ttu-id="55633-116">下面的示例定义`Sub`过程发送针对客户的帐户余额的事务。</span><span class="sxs-lookup"><span data-stu-id="55633-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="55633-117">它使用`Overloads`关键字来定义两个版本的过程中，一个接受由名称和其他客户的帐号。</span><span class="sxs-lookup"><span data-stu-id="55633-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 <span data-ttu-id="55633-118">调用代码可以获取为客户标识号`String`或`Integer`，然后在任一情况下使用相同的调用语句。</span><span class="sxs-lookup"><span data-stu-id="55633-118">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="55633-119">有关如何调用这些版本的信息`post`过程中，请参阅[如何：调用重载的过程](./how-to-call-an-overloaded-procedure.md)。</span><span class="sxs-lookup"><span data-stu-id="55633-119">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55633-120">编译代码</span><span class="sxs-lookup"><span data-stu-id="55633-120">Compiling the Code</span></span>  
 <span data-ttu-id="55633-121">请确保每个重载版本都有相同的过程名称但不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="55633-121">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55633-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="55633-122">See also</span></span>

- [<span data-ttu-id="55633-123">过程</span><span class="sxs-lookup"><span data-stu-id="55633-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="55633-124">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="55633-124">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="55633-125">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="55633-125">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="55633-126">如何：重载带有可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="55633-126">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="55633-127">如何：重载的参数数量不确定的过程</span><span class="sxs-lookup"><span data-stu-id="55633-127">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="55633-128">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="55633-128">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="55633-129">重载决策</span><span class="sxs-lookup"><span data-stu-id="55633-129">Overload Resolution</span></span>](./overload-resolution.md)
