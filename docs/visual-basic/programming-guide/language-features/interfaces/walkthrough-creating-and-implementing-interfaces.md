---
title: "创建和实现接口 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08bf6dc7344d4f83c8ab1908fdeb29eb4a53e142
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="50d72-102">演练：创建和实现接口 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50d72-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>
<span data-ttu-id="50d72-103">接口描述的属性、 方法和事件，特征，但保留最多结构或类的实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="50d72-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="50d72-104">本演练演示如何声明和实现接口。</span><span class="sxs-lookup"><span data-stu-id="50d72-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50d72-105">本演练不提供有关如何创建用户界面的信息。</span><span class="sxs-lookup"><span data-stu-id="50d72-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-an-interface"></a><span data-ttu-id="50d72-106">若要定义一个接口</span><span class="sxs-lookup"><span data-stu-id="50d72-106">To define an interface</span></span>  
  
1.  <span data-ttu-id="50d72-107">打开一个新的 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="50d72-107">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="50d72-108">向项目添加新的模块，通过单击**添加模块**上**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="50d72-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="50d72-109">命名新模块`Module1.vb`单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="50d72-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="50d72-110">显示新的模块的代码。</span><span class="sxs-lookup"><span data-stu-id="50d72-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="50d72-111">定义一个接口，该接口名为`TestInterface`内`Module1`通过键入`Interface TestInterface`之间`Module`和`End Module`语句，并按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="50d72-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="50d72-112">**代码编辑器**缩进`Interface`关键字，并将添加`End Interface`语句来形成代码块。</span><span class="sxs-lookup"><span data-stu-id="50d72-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="50d72-113">通过将下面的代码之间定义属性、 方法和事件接口`Interface`和`End Interface`语句：</span><span class="sxs-lookup"><span data-stu-id="50d72-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a><span data-ttu-id="50d72-114">实现</span><span class="sxs-lookup"><span data-stu-id="50d72-114">Implementation</span></span>  
 <span data-ttu-id="50d72-115">你可能注意到用于声明的接口成员的语法是不同于用于声明类成员声明的语法。</span><span class="sxs-lookup"><span data-stu-id="50d72-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="50d72-116">这种差异反映接口不能包含实现代码的情况。</span><span class="sxs-lookup"><span data-stu-id="50d72-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
#### <a name="to-implement-the-interface"></a><span data-ttu-id="50d72-117">若要实现接口</span><span class="sxs-lookup"><span data-stu-id="50d72-117">To implement the interface</span></span>  
  
1.  <span data-ttu-id="50d72-118">添加一个名为类`ImplementationClass`通过添加以下语句到`Module1`后面`End Interface`语句之前`End Module`语句，并按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="50d72-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     <span data-ttu-id="50d72-119">如果你正在集成的开发环境中中,**代码编辑器**提供一条匹配`End Class`语句时按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="50d72-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="50d72-120">添加以下`Implements`语句`ImplementationClass`，命名的类接口实现：</span><span class="sxs-lookup"><span data-stu-id="50d72-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     <span data-ttu-id="50d72-121">当分别列出类或结构的顶部其他项的`Implements`语句指示类或结构实现的接口。</span><span class="sxs-lookup"><span data-stu-id="50d72-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="50d72-122">如果你正在集成的开发环境中中,**代码编辑器**实现所需的类成员`TestInterface`时按 ENTER，并且你可以跳过下一步。</span><span class="sxs-lookup"><span data-stu-id="50d72-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="50d72-123">如果你未在集成的开发环境中工作，则必须实现该接口的所有成员`MyInterface`。</span><span class="sxs-lookup"><span data-stu-id="50d72-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="50d72-124">以下代码添加到`ImplementationClass`实现`Event1`， `Method1`，和`Prop1`:</span><span class="sxs-lookup"><span data-stu-id="50d72-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     <span data-ttu-id="50d72-125">`Implements`语句指定的接口和所实现的接口成员。</span><span class="sxs-lookup"><span data-stu-id="50d72-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="50d72-126">完成的定义`Prop1`通过将私有字段添加到存储的属性值的类中：</span><span class="sxs-lookup"><span data-stu-id="50d72-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     <span data-ttu-id="50d72-127">返回的值`pval`从属性 get 访问器。</span><span class="sxs-lookup"><span data-stu-id="50d72-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     <span data-ttu-id="50d72-128">设置的值`pval`在属性 set 访问器。</span><span class="sxs-lookup"><span data-stu-id="50d72-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  <span data-ttu-id="50d72-129">完成的定义`Method1`通过添加下面的代码。</span><span class="sxs-lookup"><span data-stu-id="50d72-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="50d72-130">若要测试的接口的实现</span><span class="sxs-lookup"><span data-stu-id="50d72-130">To test the implementation of the interface</span></span>  
  
1.  <span data-ttu-id="50d72-131">右键单击你的项目中的启动窗体**解决方案资源管理器**，然后单击**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="50d72-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="50d72-132">编辑器将显示为启动窗体的类。</span><span class="sxs-lookup"><span data-stu-id="50d72-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="50d72-133">默认情况下，启动窗体称为`Form1`。</span><span class="sxs-lookup"><span data-stu-id="50d72-133">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="50d72-134">添加以下`testInstance`字段`Form1`类：</span><span class="sxs-lookup"><span data-stu-id="50d72-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     <span data-ttu-id="50d72-135">通过声明`testInstance`作为`WithEvents`、`Form1`类可以处理其事件。</span><span class="sxs-lookup"><span data-stu-id="50d72-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="50d72-136">添加到以下事件处理程序`Form1`类来处理引发的事件`testInstance`:</span><span class="sxs-lookup"><span data-stu-id="50d72-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  <span data-ttu-id="50d72-137">添加一个名为子例程`Test`到`Form1`类，以测试实现类：</span><span class="sxs-lookup"><span data-stu-id="50d72-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     <span data-ttu-id="50d72-138">`Test`过程创建的类的实现实例`MyInterface`，将分配到该实例`testInstance`字段中，设置一个属性，并运行通过接口的方法。</span><span class="sxs-lookup"><span data-stu-id="50d72-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="50d72-139">添加代码来调用`Test`过程从`Form1 Load`启动窗体的过程：</span><span class="sxs-lookup"><span data-stu-id="50d72-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  <span data-ttu-id="50d72-140">运行`Test`过程通过按 F5。</span><span class="sxs-lookup"><span data-stu-id="50d72-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="50d72-141">将显示消息"Prop1 已设置为 9"。</span><span class="sxs-lookup"><span data-stu-id="50d72-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="50d72-142">之后你单击确定，显示"Method1 X 参数为 5"的消息。</span><span class="sxs-lookup"><span data-stu-id="50d72-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="50d72-143">单击确定，并显示"事件处理程序捕获事件"的消息。</span><span class="sxs-lookup"><span data-stu-id="50d72-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d72-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50d72-144">See Also</span></span>  
 [<span data-ttu-id="50d72-145">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="50d72-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="50d72-146">接口</span><span class="sxs-lookup"><span data-stu-id="50d72-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [<span data-ttu-id="50d72-147">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="50d72-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="50d72-148">Event 语句</span><span class="sxs-lookup"><span data-stu-id="50d72-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
