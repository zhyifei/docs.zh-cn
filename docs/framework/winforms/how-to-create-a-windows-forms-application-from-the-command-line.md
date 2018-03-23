---
title: 如何： 从命令行创建 Windows 窗体应用程序
ms.date: 03/14/2018
ms.prod: .net-framework
ms.technology:
- dotnet-winforms
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: 79fda0f5f455cbac50c0c1b51f0cd3bef4c5bfbc
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a><span data-ttu-id="0adfd-102">如何： 从命令行创建 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="0adfd-102">How to: Create a Windows Forms application from the command line</span></span>
<span data-ttu-id="0adfd-103">下面的过程介绍从命令行创建和运行 Windows 窗体应用程序所必须完成的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="0adfd-103">The following procedures describe the basic steps that you must complete to create and run a Windows Forms application from the command line.</span></span> <span data-ttu-id="0adfd-104">在 Visual Studio 中没有对这些过程的扩展支持。</span><span class="sxs-lookup"><span data-stu-id="0adfd-104">There is extensive support for these procedures in Visual Studio.</span></span>  <span data-ttu-id="0adfd-105">另请参阅[演练： 创建简单的 Windows 窗体](http://msdn.microsoft.com/library/z9w2f38k\(v=vs.100\))。</span><span class="sxs-lookup"><span data-stu-id="0adfd-105">Also see [Walkthrough: Creating a Simple Windows Form](http://msdn.microsoft.com/library/z9w2f38k\(v=vs.100\)).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="0adfd-106">过程</span><span class="sxs-lookup"><span data-stu-id="0adfd-106">Procedure</span></span>  
  
#### <a name="to-create-the-form"></a><span data-ttu-id="0adfd-107">若要创建窗体</span><span class="sxs-lookup"><span data-stu-id="0adfd-107">To create the form</span></span>  
  
1.  <span data-ttu-id="0adfd-108">在空代码文件中，键入下面的导入或 Using 语句：</span><span class="sxs-lookup"><span data-stu-id="0adfd-108">In an empty code file, type the following import or using statements:</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2.  <span data-ttu-id="0adfd-109">声明一个从 Form 类继承的名为 `Form1` 的类。</span><span class="sxs-lookup"><span data-stu-id="0adfd-109">Declare a class named `Form1` that inherits from the Form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3.  <span data-ttu-id="0adfd-110">为 `Form1` 创建默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="0adfd-110">Create a default constructor for `Form1`.</span></span>  
  
     <span data-ttu-id="0adfd-111">将在后续过程中向构造函数添加更多代码。</span><span class="sxs-lookup"><span data-stu-id="0adfd-111">You will add more code to the constructor in a subsequent procedure.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4.  <span data-ttu-id="0adfd-112">将 `Main` 方法添加到类。</span><span class="sxs-lookup"><span data-stu-id="0adfd-112">Add a `Main` method to the class.</span></span>  
  
    1.  <span data-ttu-id="0adfd-113">应用<xref:System.STAThreadAttribute>与 C#`Main`方法，以指定你的 Windows 窗体应用程序是单线程单元。</span><span class="sxs-lookup"><span data-stu-id="0adfd-113">Apply the <xref:System.STAThreadAttribute> to the C# `Main` method to specify your Windows Forms application is a single-threaded apartment.</span></span> <span data-ttu-id="0adfd-114">（该属性不需要在 Visual Basic 中，由于 Windows 窗体应用程序开发与 Visual Basic 使用单线程单元模型默认情况下。）</span><span class="sxs-lookup"><span data-stu-id="0adfd-114">(The attribute is not necessary in Visual Basic, since Windows forms applications developed with Visual Basic use a single-threaded apartment model by default.)</span></span>  
  
    2.  <span data-ttu-id="0adfd-115">调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>将操作系统样式应用于你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0adfd-115">Call <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> to apply operating system styles to your application.</span></span>  
  
    3.  <span data-ttu-id="0adfd-116">创建一个窗体实例，并运行。</span><span class="sxs-lookup"><span data-stu-id="0adfd-116">Create an instance of the form and run it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a><span data-ttu-id="0adfd-117">编译并运行该应用程序</span><span class="sxs-lookup"><span data-stu-id="0adfd-117">To compile and run the application</span></span>  
  
1.  <span data-ttu-id="0adfd-118">在.NET Framework 命令提示符处，导航到创建 `Form1` 类的目录。</span><span class="sxs-lookup"><span data-stu-id="0adfd-118">At the .NET Framework command prompt, navigate to the directory you created the `Form1` class.</span></span>  
  
2.  <span data-ttu-id="0adfd-119">编译该窗体。</span><span class="sxs-lookup"><span data-stu-id="0adfd-119">Compile the form.</span></span>  
  
    -   <span data-ttu-id="0adfd-120">如果你使用的 C#，请键入： `csc form1.cs`</span><span class="sxs-lookup"><span data-stu-id="0adfd-120">If you are using C#, type: `csc form1.cs`</span></span>  
  
         `-or-`  
  
    -   <span data-ttu-id="0adfd-121">如果你在使用 Visual Basic 中，类型： `vbc form1.vb`</span><span class="sxs-lookup"><span data-stu-id="0adfd-121">If you are using Visual Basic, type: `vbc form1.vb`</span></span>  
  
3.  <span data-ttu-id="0adfd-122">在命令提示符下键入： `Form1.exe`</span><span class="sxs-lookup"><span data-stu-id="0adfd-122">At the command prompt, type: `Form1.exe`</span></span>  
  
## <a name="adding-a-control-and-handling-an-event"></a><span data-ttu-id="0adfd-123">添加控件并处理事件</span><span class="sxs-lookup"><span data-stu-id="0adfd-123">Adding a Control and Handling an Event</span></span>  
 <span data-ttu-id="0adfd-124">上一过程中的步骤演示了如何只创建一个可编译和运行的基本 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="0adfd-124">The previous procedure steps demonstrated how to just create a basic Windows Form that compiles and runs.</span></span> <span data-ttu-id="0adfd-125">下一个过程中将显示如何创建控件并将其添加到窗体中，以及如何处理控件的事件。</span><span class="sxs-lookup"><span data-stu-id="0adfd-125">The next procedure will show you how to create and add a control to the form, and handle an event for the control.</span></span> <span data-ttu-id="0adfd-126">你可以将其添加到 Windows 窗体控件的详细信息，请参阅[Windows 窗体控件](../../../docs/framework/winforms/controls/index.md)。</span><span class="sxs-lookup"><span data-stu-id="0adfd-126">For more information about the controls you can add to Windows Forms, see [Windows Forms Controls](../../../docs/framework/winforms/controls/index.md).</span></span>  
  
 <span data-ttu-id="0adfd-127">除了解如何创建 Windows 窗体应用程序外，还应了解基于事件的编程以及如何处理用户输入。</span><span class="sxs-lookup"><span data-stu-id="0adfd-127">In addition to understanding how to create Windows Forms applications, you should understand event-based programming and how to handle user input.</span></span> <span data-ttu-id="0adfd-128">有关详细信息，请参阅[Windows 窗体中创建事件处理程序](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)，和[处理用户输入](../../../docs/framework/winforms/controls/handling-user-input.md)</span><span class="sxs-lookup"><span data-stu-id="0adfd-128">For more information, see [Creating Event Handlers in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md), and [Handling User Input](../../../docs/framework/winforms/controls/handling-user-input.md)</span></span>  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a><span data-ttu-id="0adfd-129">若要声明一个按钮控件和处理其 click 事件</span><span class="sxs-lookup"><span data-stu-id="0adfd-129">To declare a button control and handle its click event</span></span>  
  
1.  <span data-ttu-id="0adfd-130">请声明一个名为 `button1` 的按钮控件。</span><span class="sxs-lookup"><span data-stu-id="0adfd-130">Declare a button control named `button1`.</span></span>  
  
2.  <span data-ttu-id="0adfd-131">在构造函数中，创建按钮，并设置其 <xref:System.Windows.Forms.Control.Size%2A>、<xref:System.Windows.Forms.Control.Location%2A> 和 <xref:System.Windows.Forms.Control.Text%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0adfd-131">In the constructor, create the button and set its <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Text%2A> properties.</span></span>  
  
3.  <span data-ttu-id="0adfd-132">向窗体添加按钮。</span><span class="sxs-lookup"><span data-stu-id="0adfd-132">Add the button to the form.</span></span>  
  
     <span data-ttu-id="0adfd-133">下面的代码示例演示如何声明按钮操作。</span><span class="sxs-lookup"><span data-stu-id="0adfd-133">The following code example demonstrates how to declare the button control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="0adfd-134">创建一个方法来处理该按钮的 <xref:System.Windows.Forms.Control.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="0adfd-134">Create a method to handle the <xref:System.Windows.Forms.Control.Click> event for the button.</span></span>  
  
5.  <span data-ttu-id="0adfd-135">在 Click 事件处理程序中，显示带有消息“Hello World”的 <xref:System.Windows.Forms.MessageBox>。</span><span class="sxs-lookup"><span data-stu-id="0adfd-135">In the click event handler, display a <xref:System.Windows.Forms.MessageBox> with the message, "Hello World".</span></span>  
  
     <span data-ttu-id="0adfd-136">下面的代码示例演示如何处理按钮控件的 Click 事件。</span><span class="sxs-lookup"><span data-stu-id="0adfd-136">The following code example demonstrates how to handle the button control's click event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6.  <span data-ttu-id="0adfd-137">将 <xref:System.Windows.Forms.Control.Click> 事件与创建的方法相关联。</span><span class="sxs-lookup"><span data-stu-id="0adfd-137">Associate the <xref:System.Windows.Forms.Control.Click> event with the method you created.</span></span>  
  
     <span data-ttu-id="0adfd-138">下面的代码示例演示如何将事件与方法相关联。</span><span class="sxs-lookup"><span data-stu-id="0adfd-138">The following code example demonstrates how to associate the event with the method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7.  <span data-ttu-id="0adfd-139">编译并运行该应用程序，如之前过程中所述。</span><span class="sxs-lookup"><span data-stu-id="0adfd-139">Compile and run the application as described in the previous procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0adfd-140">示例</span><span class="sxs-lookup"><span data-stu-id="0adfd-140">Example</span></span>  
 <span data-ttu-id="0adfd-141">以下代码示例是上一过程的完整示例。</span><span class="sxs-lookup"><span data-stu-id="0adfd-141">Following code example is the complete example from the previous procedures.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0adfd-142">编译代码</span><span class="sxs-lookup"><span data-stu-id="0adfd-142">Compiling the Code</span></span>  
  
-   <span data-ttu-id="0adfd-143">若要编译代码，请遵循处理过程中描述如何编译和运行应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="0adfd-143">To compile the code, follow the instructions in the proceeding procedure that describe how to compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0adfd-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0adfd-144">See Also</span></span>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Control>  
 [<span data-ttu-id="0adfd-145">更改 Windows 窗体外观</span><span class="sxs-lookup"><span data-stu-id="0adfd-145">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 [<span data-ttu-id="0adfd-146">增强 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="0adfd-146">Enhancing Windows Forms Applications</span></span>](../../../docs/framework/winforms/advanced/index.md)  
 [<span data-ttu-id="0adfd-147">Windows 窗体入门</span><span class="sxs-lookup"><span data-stu-id="0adfd-147">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
