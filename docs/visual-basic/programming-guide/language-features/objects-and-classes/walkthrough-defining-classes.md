---
title: "定义类 (Visual Basic 中) |Microsoft 文档"
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
- execution, ending
- objects [Visual Basic], initializing
- Initialize event
- files, closing
- programs, quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event
- execution, stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
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
ms.openlocfilehash: 5b470b8ba9b60dfb1cd1bbb207e02217f5311c27
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="815d3-102">演练：定义类 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="815d3-102">Walkthrough: Defining Classes (Visual Basic)</span></span>
<span data-ttu-id="815d3-103">本演练演示如何定义类，您可以使用它来创建对象。</span><span class="sxs-lookup"><span data-stu-id="815d3-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="815d3-104">它还演示如何将属性和方法添加到新类，并演示如何初始化对象。</span><span class="sxs-lookup"><span data-stu-id="815d3-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-a-class"></a><span data-ttu-id="815d3-105">若要定义一个类</span><span class="sxs-lookup"><span data-stu-id="815d3-105">To define a class</span></span>  
  
1.  <span data-ttu-id="815d3-106">通过单击创建项目**新项目**上**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="815d3-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="815d3-107">此时将出现 **“新建项目”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="815d3-107">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="815d3-108">从列表中选择 Windows 应用程序[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]项目模板来显示新项目。</span><span class="sxs-lookup"><span data-stu-id="815d3-108">Select Windows Application from the list of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project templates to display the new project.</span></span>  
  
3.  <span data-ttu-id="815d3-109">将新类添加到项目中，通过单击**添加类**上**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="815d3-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="815d3-110">**添加新项**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="815d3-110">The **Add New Item** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="815d3-111">选择**类**模板。</span><span class="sxs-lookup"><span data-stu-id="815d3-111">Select the **Class** template.</span></span>  
  
5.  <span data-ttu-id="815d3-112">将新类命名`UserNameInfo.vb`，然后单击**添加**以显示新类的代码。</span><span class="sxs-lookup"><span data-stu-id="815d3-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     <span data-ttu-id="815d3-113">[!code-vb[VbVbalrOOP #&5;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="815d3-113">[!code-vb[VbVbalrOOP#5](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="815d3-114">您可以使用[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]**代码编辑器**将类添加到启动窗体中，通过键入`Class`关键字后跟新类的名称。</span><span class="sxs-lookup"><span data-stu-id="815d3-114">You can use the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="815d3-115">**代码编辑器**会提供相应`End Class`为您的语句。</span><span class="sxs-lookup"><span data-stu-id="815d3-115">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6.  <span data-ttu-id="815d3-116">通过添加下面的代码之间定义的类的私有字段`Class`和`End Class`语句︰</span><span class="sxs-lookup"><span data-stu-id="815d3-116">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     <span data-ttu-id="815d3-117">[!code-vb[VbVbalrOOP #&7;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="815d3-117">[!code-vb[VbVbalrOOP#7](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]</span></span>  
  
     <span data-ttu-id="815d3-118">声明该字段作为`Private`意味着它可以仅在类中使用。</span><span class="sxs-lookup"><span data-stu-id="815d3-118">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="815d3-119">您可以使字段成为可从类外部的通过使用访问修饰符，如`Public`提供更多的权限。</span><span class="sxs-lookup"><span data-stu-id="815d3-119">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="815d3-120">有关详细信息，请参阅[Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="815d3-120">For more information, see [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7.  <span data-ttu-id="815d3-121">通过添加下面的代码定义用于类的属性︰</span><span class="sxs-lookup"><span data-stu-id="815d3-121">Define a property for the class by adding the following code:</span></span>  
  
     <span data-ttu-id="815d3-122">[!code-vb[VbVbalrOOP #&8;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="815d3-122">[!code-vb[VbVbalrOOP#8](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]</span></span>  
  
8.  <span data-ttu-id="815d3-123">通过添加下面的代码定义为类的方法︰</span><span class="sxs-lookup"><span data-stu-id="815d3-123">Define a method for the class by adding the following code:</span></span>  
  
     <span data-ttu-id="815d3-124">[!code-vb[VbVbalrOOP #&9;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="815d3-124">[!code-vb[VbVbalrOOP#9](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]</span></span>  
  
9. <span data-ttu-id="815d3-125">通过添加一个名为过程定义参数化构造函数为新类`Sub New`:</span><span class="sxs-lookup"><span data-stu-id="815d3-125">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     <span data-ttu-id="815d3-126">[!code-vb[VbVbalrOOP #&10;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="815d3-126">[!code-vb[VbVbalrOOP#10](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]</span></span>  
  
     <span data-ttu-id="815d3-127">`Sub New`创建基于此类对象时自动调用构造函数。</span><span class="sxs-lookup"><span data-stu-id="815d3-127">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="815d3-128">此构造函数设置保存的用户名称的字段的值。</span><span class="sxs-lookup"><span data-stu-id="815d3-128">This constructor sets the value of the field that holds the user name.</span></span>  
  
### <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="815d3-129">若要创建一个按钮以测试类</span><span class="sxs-lookup"><span data-stu-id="815d3-129">To create a button to test the class</span></span>  
  
1.  <span data-ttu-id="815d3-130">通过右键单击在其名称更改为设计模式的启动窗体**解决方案资源管理器**，然后单击**视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="815d3-130">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="815d3-131">默认情况下，Windows 应用程序项目的启动窗体是名为 form1.vb。</span><span class="sxs-lookup"><span data-stu-id="815d3-131">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="815d3-132">然后，主窗体将出现。</span><span class="sxs-lookup"><span data-stu-id="815d3-132">The main form will then appear.</span></span>  
  
2.  <span data-ttu-id="815d3-133">向主窗体添加一个按钮并双击它以显示的代码`Button1_Click`事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="815d3-133">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="815d3-134">添加以下代码以调用测试过程︰</span><span class="sxs-lookup"><span data-stu-id="815d3-134">Add the following code to call the test procedure:</span></span>  
  
     <span data-ttu-id="815d3-135">[!code-vb[VbVbalrOOP #&12;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="815d3-135">[!code-vb[VbVbalrOOP#12](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]</span></span>  
  
### <a name="to-run-your-application"></a><span data-ttu-id="815d3-136">运行应用程序</span><span class="sxs-lookup"><span data-stu-id="815d3-136">To run your application</span></span>  
  
1.  <span data-ttu-id="815d3-137">通过按 F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="815d3-137">Run your application by pressing F5.</span></span> <span data-ttu-id="815d3-138">单击要调用测试过程的窗体上的按钮。</span><span class="sxs-lookup"><span data-stu-id="815d3-138">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="815d3-139">它将显示一条消息表明原始`UserName`是"MOORE，BOBBY"，因为该过程调用`Capitalize`对象的方法。</span><span class="sxs-lookup"><span data-stu-id="815d3-139">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2.  <span data-ttu-id="815d3-140">单击**确定**关闭消息框。</span><span class="sxs-lookup"><span data-stu-id="815d3-140">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="815d3-141">`Button1 Click`过程将更改的值`UserName`属性，并显示的新值的一条消息表明`UserName`是"Worden，Joe"。</span><span class="sxs-lookup"><span data-stu-id="815d3-141">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="815d3-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="815d3-142">See Also</span></span>  
 <span data-ttu-id="815d3-143">[面向对象的编程](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2) </span><span class="sxs-lookup"><span data-stu-id="815d3-143">[Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2) </span></span>  
<span data-ttu-id="815d3-144"> [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span><span class="sxs-lookup"><span data-stu-id="815d3-144"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span></span>

