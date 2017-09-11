---
title: "创建和实现接口 (Visual Basic 中) |Microsoft 文档"
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
- interfaces, walkthroughs
- interfaces, testing
- interface implementation, walkthrough
- interfaces, creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
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
ms.openlocfilehash: ef1ec16005bf0a7967d396054ae23c1023143c2a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="863ff-102">演练：创建和实现接口 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="863ff-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>
<span data-ttu-id="863ff-103">接口描述特征的属性、 方法和事件，但将留给了结构或类实现的细节。</span><span class="sxs-lookup"><span data-stu-id="863ff-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="863ff-104">本演练演示如何声明和实现接口。</span><span class="sxs-lookup"><span data-stu-id="863ff-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="863ff-105">本演练并不提供有关如何创建用户界面的信息。</span><span class="sxs-lookup"><span data-stu-id="863ff-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-an-interface"></a><span data-ttu-id="863ff-106">若要定义一个接口</span><span class="sxs-lookup"><span data-stu-id="863ff-106">To define an interface</span></span>  
  
1.  <span data-ttu-id="863ff-107">打开一个新[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="863ff-107">Open a new [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="863ff-108">向项目添加一个新模块，通过单击**添加模块**上**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="863ff-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="863ff-109">命名新模块`Module1.vb`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="863ff-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="863ff-110">显示新的模块的代码。</span><span class="sxs-lookup"><span data-stu-id="863ff-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="863ff-111">定义一个接口，该接口名为`TestInterface`内`Module1`通过键入`Interface TestInterface`之间`Module`和`End Module`语句，并按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="863ff-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="863ff-112">**代码编辑器**缩进`Interface`关键字，并将添加`End Interface`语句来形成一个代码块。</span><span class="sxs-lookup"><span data-stu-id="863ff-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="863ff-113">通过将下面的代码之间定义属性、 方法和事件的接口`Interface`和`End Interface`语句︰</span><span class="sxs-lookup"><span data-stu-id="863ff-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     <span data-ttu-id="863ff-114">[!code-vb[VbVbalrOOP #&98;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-114">[!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="863ff-115">实现</span><span class="sxs-lookup"><span data-stu-id="863ff-115">Implementation</span></span>  
 <span data-ttu-id="863ff-116">您可能注意到用来声明接口成员的语法是用来声明类成员声明语法不同。</span><span class="sxs-lookup"><span data-stu-id="863ff-116">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="863ff-117">这一区别反映接口不能包含实现代码的情况。</span><span class="sxs-lookup"><span data-stu-id="863ff-117">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
#### <a name="to-implement-the-interface"></a><span data-ttu-id="863ff-118">若要实现接口</span><span class="sxs-lookup"><span data-stu-id="863ff-118">To implement the interface</span></span>  
  
1.  <span data-ttu-id="863ff-119">添加一个名为类`ImplementationClass`通过添加下面的语句`Module1`后面`End Interface`语句之前`End Module`语句，并按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="863ff-119">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     <span data-ttu-id="863ff-120">[!code-vb[VbVbalrOOP #&99;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-120">[!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]</span></span>  
  
     <span data-ttu-id="863ff-121">如果您正在在集成的开发环境中，**代码编辑器**提供一条匹配`End Class`语句时按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="863ff-121">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="863ff-122">将以下代码添加`Implements`语句`ImplementationClass`，命名的类接口实现︰</span><span class="sxs-lookup"><span data-stu-id="863ff-122">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     <span data-ttu-id="863ff-123">[!code-vb[VbVbalrOOP #&100;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-123">[!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]</span></span>  
  
     <span data-ttu-id="863ff-124">在顶部的类或结构，其他项分开列出`Implements`语句指示类或结构实现的接口。</span><span class="sxs-lookup"><span data-stu-id="863ff-124">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="863ff-125">如果您正在在集成的开发环境中，**代码编辑器**实现所需的类成员`TestInterface`时按 enter 键，并且可以跳过下一步。</span><span class="sxs-lookup"><span data-stu-id="863ff-125">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="863ff-126">如果您没有使用使用集成的开发环境中，必须实现该接口的所有成员`MyInterface`。</span><span class="sxs-lookup"><span data-stu-id="863ff-126">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="863ff-127">添加以下代码到`ImplementationClass`实现`Event1`， `Method1`，和`Prop1`:</span><span class="sxs-lookup"><span data-stu-id="863ff-127">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     <span data-ttu-id="863ff-128">[!code-vb[VbVbalrOOP #&101;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-128">[!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]</span></span>  
  
     <span data-ttu-id="863ff-129">`Implements`语句指定的接口和实现的接口成员。</span><span class="sxs-lookup"><span data-stu-id="863ff-129">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="863ff-130">完成的定义`Prop1`通过将一个私有字段添加到存储的属性值的类中︰</span><span class="sxs-lookup"><span data-stu-id="863ff-130">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     <span data-ttu-id="863ff-131">[!code-vb[VbVbalrOOP #&102;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-131">[!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]</span></span>  
  
     <span data-ttu-id="863ff-132">返回的值`pval`从属性 get 访问器。</span><span class="sxs-lookup"><span data-stu-id="863ff-132">Return the value of the `pval` from the property get accessor.</span></span>  
  
     <span data-ttu-id="863ff-133">[!code-vb[VbVbalrOOP #&103;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-133">[!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]</span></span>  
  
     <span data-ttu-id="863ff-134">值设置`pval`在属性 set 访问器。</span><span class="sxs-lookup"><span data-stu-id="863ff-134">Set the value of `pval` in the property set accessor.</span></span>  
  
     <span data-ttu-id="863ff-135">[!code-vb[VbVbalrOOP #&104;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-135">[!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]</span></span>  
  
5.  <span data-ttu-id="863ff-136">完成的定义`Method1`通过添加下面的代码。</span><span class="sxs-lookup"><span data-stu-id="863ff-136">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     <span data-ttu-id="863ff-137">[!code-vb[VbVbalrOOP #&105;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-137">[!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]</span></span>  
  
#### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="863ff-138">若要测试该接口实现</span><span class="sxs-lookup"><span data-stu-id="863ff-138">To test the implementation of the interface</span></span>  
  
1.  <span data-ttu-id="863ff-139">用鼠标右键单击你的项目中的启动窗体**解决方案资源管理器**，然后单击**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="863ff-139">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="863ff-140">编辑器会显示启动窗体的类。</span><span class="sxs-lookup"><span data-stu-id="863ff-140">The editor displays the class for your startup form.</span></span> <span data-ttu-id="863ff-141">默认情况下，启动窗体称为`Form1`。</span><span class="sxs-lookup"><span data-stu-id="863ff-141">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="863ff-142">将以下代码添加`testInstance`字段拖至`Form1`类︰</span><span class="sxs-lookup"><span data-stu-id="863ff-142">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     <span data-ttu-id="863ff-143">[!code-vb[VbVbalrOOP #&120;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-143">[!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]</span></span>  
  
     <span data-ttu-id="863ff-144">通过声明`testInstance`作为`WithEvents`、`Form1`类可以处理其事件。</span><span class="sxs-lookup"><span data-stu-id="863ff-144">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="863ff-145">添加到以下事件处理程序`Form1`类来处理所引发的事件`testInstance`:</span><span class="sxs-lookup"><span data-stu-id="863ff-145">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     <span data-ttu-id="863ff-146">[!code-vb[VbVbalrOOP #&106;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-146">[!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]</span></span>  
  
4.  <span data-ttu-id="863ff-147">添加一个名为子例程`Test`到`Form1`类来测试实现类︰</span><span class="sxs-lookup"><span data-stu-id="863ff-147">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     <span data-ttu-id="863ff-148">[!code-vb[VbVbalrOOP #&107; 页](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-148">[!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]</span></span>  
  
     <span data-ttu-id="863ff-149">`Test`过程创建的实现的类实例`MyInterface`，将分配到该实例`testInstance`字段中，设置一个属性，并通过该接口运行一个方法。</span><span class="sxs-lookup"><span data-stu-id="863ff-149">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="863ff-150">添加代码以调用`Test`过程从`Form1 Load`启动窗体的过程︰</span><span class="sxs-lookup"><span data-stu-id="863ff-150">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     <span data-ttu-id="863ff-151">[!code-vb[VbVbalrOOP #&108;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="863ff-151">[!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]</span></span>  
  
6.  <span data-ttu-id="863ff-152">运行`Test`过程通过按 F5。</span><span class="sxs-lookup"><span data-stu-id="863ff-152">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="863ff-153">将显示消息"Prop1 已设置为 9"。</span><span class="sxs-lookup"><span data-stu-id="863ff-153">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="863ff-154">之后您单击确定，显示"Method1 X 参数 is 5"的消息。</span><span class="sxs-lookup"><span data-stu-id="863ff-154">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="863ff-155">单击确定，并显示"事件处理程序捕获事件"的消息。</span><span class="sxs-lookup"><span data-stu-id="863ff-155">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="863ff-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="863ff-156">See Also</span></span>  
 <span data-ttu-id="863ff-157">[Implements 语句](../../../../visual-basic/language-reference/statements/implements-statement.md) </span><span class="sxs-lookup"><span data-stu-id="863ff-157">[Implements Statement](../../../../visual-basic/language-reference/statements/implements-statement.md) </span></span>  
<span data-ttu-id="863ff-158"> [接口](../../../../visual-basic/programming-guide/language-features/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="863ff-158"> [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md) </span></span>  
<span data-ttu-id="863ff-159"> [Interface 语句](../../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="863ff-159"> [Interface Statement](../../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="863ff-160"> [Event 语句](../../../../visual-basic/language-reference/statements/event-statement.md)</span><span class="sxs-lookup"><span data-stu-id="863ff-160"> [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md)</span></span>

