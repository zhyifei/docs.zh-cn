---
title: 创建和实现接口 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: faed4d3c9498938e022daf821dd0aefbcbcf2e8d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322025"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="efcfa-102">演练：创建和实现接口 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efcfa-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="efcfa-103">接口描述特征的属性、 方法和事件，但保留最多结构或类的实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="efcfa-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="efcfa-104">本演练演示如何声明和实现接口。</span><span class="sxs-lookup"><span data-stu-id="efcfa-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efcfa-105">本演练不提供有关如何创建用户界面的信息。</span><span class="sxs-lookup"><span data-stu-id="efcfa-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="efcfa-106">若要定义一个接口</span><span class="sxs-lookup"><span data-stu-id="efcfa-106">To define an interface</span></span>
  
1. <span data-ttu-id="efcfa-107">打开一个新的 Visual Basic Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="efcfa-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="efcfa-108">将新模块添加到项目中，通过单击**添加模块**上**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="efcfa-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="efcfa-109">命名新模块`Module1.vb`然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="efcfa-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="efcfa-110">显示新的模块的代码。</span><span class="sxs-lookup"><span data-stu-id="efcfa-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="efcfa-111">定义一个名为的接口`TestInterface`内`Module1`通过键入`Interface TestInterface`之间`Module`和`End Module`语句，并按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="efcfa-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="efcfa-112">**代码编辑器**缩进`Interface`关键字，并将添加`End Interface`语句以形成一个代码块。</span><span class="sxs-lookup"><span data-stu-id="efcfa-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="efcfa-113">通过将下面的代码之间定义属性、 方法和事件接口`Interface`和`End Interface`语句：</span><span class="sxs-lookup"><span data-stu-id="efcfa-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="efcfa-114">实现</span><span class="sxs-lookup"><span data-stu-id="efcfa-114">Implementation</span></span>

 <span data-ttu-id="efcfa-115">你可能会发现用于声明接口成员的语法不同于用来声明类成员的语法。</span><span class="sxs-lookup"><span data-stu-id="efcfa-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="efcfa-116">这一区别反映了这一事实，接口不能包含实现代码。</span><span class="sxs-lookup"><span data-stu-id="efcfa-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="efcfa-117">若要实现接口</span><span class="sxs-lookup"><span data-stu-id="efcfa-117">To implement the interface</span></span>
  
1. <span data-ttu-id="efcfa-118">添加名为的类`ImplementationClass`通过将添加到下面的语句`Module1`后面`End Interface`语句之前`End Module`语句，并按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="efcfa-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="efcfa-119">如果你正在使用集成的开发环境**代码编辑器**提供一条匹配`End Class`语句时按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="efcfa-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="efcfa-120">添加以下`Implements`语句`ImplementationClass`，命名的类接口实现：</span><span class="sxs-lookup"><span data-stu-id="efcfa-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="efcfa-121">当分别列出了在类或结构的顶部的其他项的`Implements`语句指示类或结构实现的接口。</span><span class="sxs-lookup"><span data-stu-id="efcfa-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="efcfa-122">如果你正在使用集成的开发环境**代码编辑器**实现所需的类成员`TestInterface`时按 enter 键，并且你可以跳过下一步。</span><span class="sxs-lookup"><span data-stu-id="efcfa-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="efcfa-123">如果不使用集成的开发环境中，则必须实现该接口的所有成员`MyInterface`。</span><span class="sxs-lookup"><span data-stu-id="efcfa-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="efcfa-124">将以下代码添加到`ImplementationClass`来实现`Event1`， `Method1`，和`Prop1`:</span><span class="sxs-lookup"><span data-stu-id="efcfa-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="efcfa-125">`Implements`语句命名的接口和实现的接口成员。</span><span class="sxs-lookup"><span data-stu-id="efcfa-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="efcfa-126">完成的定义`Prop1`通过将私有字段添加到存储的属性值的类中：</span><span class="sxs-lookup"><span data-stu-id="efcfa-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="efcfa-127">返回的值`pval`从属性 get 访问器。</span><span class="sxs-lookup"><span data-stu-id="efcfa-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="efcfa-128">值设置`pval`在属性 set 访问器。</span><span class="sxs-lookup"><span data-stu-id="efcfa-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="efcfa-129">完成的定义`Method1`通过添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="efcfa-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="efcfa-130">若要测试接口的实现</span><span class="sxs-lookup"><span data-stu-id="efcfa-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="efcfa-131">右键单击你的项目中的启动窗体**解决方案资源管理器**，然后单击**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="efcfa-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="efcfa-132">编辑器会显示启动窗体的类。</span><span class="sxs-lookup"><span data-stu-id="efcfa-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="efcfa-133">默认情况下，启动窗体称为`Form1`。</span><span class="sxs-lookup"><span data-stu-id="efcfa-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="efcfa-134">添加以下`testInstance`字段改为`Form1`类：</span><span class="sxs-lookup"><span data-stu-id="efcfa-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="efcfa-135">通过声明`testInstance`作为`WithEvents`，则`Form1`类可以处理其事件。</span><span class="sxs-lookup"><span data-stu-id="efcfa-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="efcfa-136">添加到以下事件处理程序`Form1`类来处理引发的事件`testInstance`:</span><span class="sxs-lookup"><span data-stu-id="efcfa-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="efcfa-137">添加一个名为子例程`Test`到`Form1`类，以测试实现类：</span><span class="sxs-lookup"><span data-stu-id="efcfa-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="efcfa-138">`Test`过程将创建实现的类的实例`MyInterface`，将分配到该实例`testInstance`字段中，设置属性，并通过界面运行某个方法。</span><span class="sxs-lookup"><span data-stu-id="efcfa-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="efcfa-139">添加代码以调用`Test`过程从`Form1 Load`启动窗体的过程：</span><span class="sxs-lookup"><span data-stu-id="efcfa-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="efcfa-140">运行`Test`过程通过按 F5。</span><span class="sxs-lookup"><span data-stu-id="efcfa-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="efcfa-141">显示消息"Prop1 已设置为 9"。</span><span class="sxs-lookup"><span data-stu-id="efcfa-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="efcfa-142">之后，单击确定，显示"Method1 X 参数是 5"的消息。</span><span class="sxs-lookup"><span data-stu-id="efcfa-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="efcfa-143">单击确定，并显示"事件处理程序捕获到事件"的消息。</span><span class="sxs-lookup"><span data-stu-id="efcfa-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efcfa-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="efcfa-144">See also</span></span>

- [<span data-ttu-id="efcfa-145">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="efcfa-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="efcfa-146">接口</span><span class="sxs-lookup"><span data-stu-id="efcfa-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="efcfa-147">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="efcfa-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="efcfa-148">Event 语句</span><span class="sxs-lookup"><span data-stu-id="efcfa-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
