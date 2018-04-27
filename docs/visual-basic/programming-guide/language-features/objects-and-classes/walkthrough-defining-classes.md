---
title: 定义类 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9fc173ad853755c4b02a13abc0a80229bebffe64
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="b49b4-102">演练：定义类 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49b4-102">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="b49b4-103">本演练演示如何定义类，你可以使用它来创建对象。</span><span class="sxs-lookup"><span data-stu-id="b49b4-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="b49b4-104">它还演示如何将属性和方法添加到新的类，并演示如何初始化的对象。</span><span class="sxs-lookup"><span data-stu-id="b49b4-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="b49b4-105">若要定义的类</span><span class="sxs-lookup"><span data-stu-id="b49b4-105">To define a class</span></span>
  
1.  <span data-ttu-id="b49b4-106">通过单击创建项目**新项目**上**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="b49b4-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="b49b4-107">此时将出现 “新建项目” 对话框。</span><span class="sxs-lookup"><span data-stu-id="b49b4-107">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="b49b4-108">从 Visual Basic 项目模板，以显示新的项目列表中选择 Windows 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b49b4-108">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3.  <span data-ttu-id="b49b4-109">将新类添加到项目中，通过单击**添加类**上**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="b49b4-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="b49b4-110">“添加新项”对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="b49b4-110">The **Add New Item** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="b49b4-111">选择**类**模板。</span><span class="sxs-lookup"><span data-stu-id="b49b4-111">Select the **Class** template.</span></span>  
  
5.  <span data-ttu-id="b49b4-112">将新类`UserNameInfo.vb`，然后单击**添加**以显示新的类的代码。</span><span class="sxs-lookup"><span data-stu-id="b49b4-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  <span data-ttu-id="b49b4-113">你可以使用 Visual Basic**代码编辑器**将类添加到启动窗体中，通过键入`Class`关键字后跟新类的名称。</span><span class="sxs-lookup"><span data-stu-id="b49b4-113">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="b49b4-114">**代码编辑器**提供相应`End Class`为你的语句。</span><span class="sxs-lookup"><span data-stu-id="b49b4-114">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6.  <span data-ttu-id="b49b4-115">通过添加下面的代码之间定义类的私有字段`Class`和`End Class`语句：</span><span class="sxs-lookup"><span data-stu-id="b49b4-115">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="b49b4-116">声明为字段`Private`意味着它可以仅在类内使用。</span><span class="sxs-lookup"><span data-stu-id="b49b4-116">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="b49b4-117">你可以使字段成为可从类外部的通过使用访问修饰符，如`Public`提供访问权限多。</span><span class="sxs-lookup"><span data-stu-id="b49b4-117">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="b49b4-118">有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="b49b4-118">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7.  <span data-ttu-id="b49b4-119">通过添加下面的代码中定义类的属性：</span><span class="sxs-lookup"><span data-stu-id="b49b4-119">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8.  <span data-ttu-id="b49b4-120">通过添加下面的代码中定义的类方法：</span><span class="sxs-lookup"><span data-stu-id="b49b4-120">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="b49b4-121">通过添加名为的过程中定义新类的参数化构造函数`Sub New`:</span><span class="sxs-lookup"><span data-stu-id="b49b4-121">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="b49b4-122">`Sub New`创建基于此类对象时自动调用构造函数。</span><span class="sxs-lookup"><span data-stu-id="b49b4-122">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="b49b4-123">此构造函数设置保留的用户名的字段的值。</span><span class="sxs-lookup"><span data-stu-id="b49b4-123">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="b49b4-124">若要创建一个按钮以测试类</span><span class="sxs-lookup"><span data-stu-id="b49b4-124">To create a button to test the class</span></span>
  
1.  <span data-ttu-id="b49b4-125">将启动窗体更改为设计模式中，右键单击其名称中的**解决方案资源管理器**，然后单击**视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="b49b4-125">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="b49b4-126">默认情况下，Windows 应用程序项目的启动窗体名为 form1.vb。</span><span class="sxs-lookup"><span data-stu-id="b49b4-126">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="b49b4-127">随后将显示主窗体。</span><span class="sxs-lookup"><span data-stu-id="b49b4-127">The main form will then appear.</span></span>  
  
2.  <span data-ttu-id="b49b4-128">向主窗体添加一个按钮并双击它以显示的代码`Button1_Click`事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b49b4-128">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="b49b4-129">添加以下代码以调用测试过程：</span><span class="sxs-lookup"><span data-stu-id="b49b4-129">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="b49b4-130">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="b49b4-130">To run your application</span></span>
  
1.  <span data-ttu-id="b49b4-131">按 F5 运行你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b49b4-131">Run your application by pressing F5.</span></span> <span data-ttu-id="b49b4-132">单击要调用的测试过程的窗体上的按钮。</span><span class="sxs-lookup"><span data-stu-id="b49b4-132">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="b49b4-133">它将显示一条消息表明原始`UserName`是"兵 BOBBY"，因为调用该过程`Capitalize`对象的方法。</span><span class="sxs-lookup"><span data-stu-id="b49b4-133">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2.  <span data-ttu-id="b49b4-134">单击**确定**关闭消息框。</span><span class="sxs-lookup"><span data-stu-id="b49b4-134">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="b49b4-135">`Button1 Click`过程更改的值`UserName`属性并显示的新值的消息，指出`UserName`是"Worden，Joe"。</span><span class="sxs-lookup"><span data-stu-id="b49b4-135">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b49b4-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="b49b4-136">See also</span></span>

[<span data-ttu-id="b49b4-137">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49b4-137">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)  
[<span data-ttu-id="b49b4-138">对象和类</span><span class="sxs-lookup"><span data-stu-id="b49b4-138">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)