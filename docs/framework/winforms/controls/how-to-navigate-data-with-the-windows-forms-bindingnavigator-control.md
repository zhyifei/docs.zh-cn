---
title: 如何：使用 Windows 窗体 BindingNavigator 控件导航数据
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingNavigator control [Windows Forms], navigating data
- data [Windows Forms], navigating
- data navigation
- examples [Windows Forms], BindingNavigator control
ms.assetid: 0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99ed6b7232dd80733fea3c9f36722b0722dc1525
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-navigate-data-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="12c07-102">如何：使用 Windows 窗体 BindingNavigator 控件导航数据</span><span class="sxs-lookup"><span data-stu-id="12c07-102">How to: Navigate Data with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="12c07-103">Windows 窗体提供 <xref:System.Windows.Forms.BindingNavigator> 控件，开发人员可通过该控件在他们创建的窗体上为最终用户提供简单的数据导航和用户界面操作。</span><span class="sxs-lookup"><span data-stu-id="12c07-103">The advent of the <xref:System.Windows.Forms.BindingNavigator> control in Windows Forms enables developers to provide end users with a simple data navigation and manipulation user interface on the forms they create.</span></span>  
  
 <span data-ttu-id="12c07-104"><xref:System.Windows.Forms.BindingNavigator> 控件是一个 <xref:System.Windows.Forms.ToolStrip> 控件，该控件上带有预配置为导航到数据集中第一条、最后一条、下一条和上一条记录的按钮，而且还有用于添加和删除记录的按钮。</span><span class="sxs-lookup"><span data-stu-id="12c07-104">The <xref:System.Windows.Forms.BindingNavigator> control is a <xref:System.Windows.Forms.ToolStrip> control with buttons preconfigured for navigation to the first, last, next, and previous record in a data set, as well as buttons to add and delete records.</span></span> <span data-ttu-id="12c07-105">将按钮添加到 <xref:System.Windows.Forms.BindingNavigator> 控件非常简单，因为它是一个 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="12c07-105">Adding buttons to the <xref:System.Windows.Forms.BindingNavigator> control is easy, because it is a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  <span data-ttu-id="12c07-106">另请参阅[如何：向 Windows 窗体 BindingNavigator 控件添加“加载”、“保存”和“取消”按钮](http://msdn.microsoft.com/library/safa4957\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="12c07-106">Also see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](http://msdn.microsoft.com/library/safa4957\(v=vs.110\)).</span></span>  
  
 <span data-ttu-id="12c07-107">对于 <xref:System.Windows.Forms.BindingNavigator> 控件上的每个按钮，都有一个对应的 <xref:System.Windows.Forms.BindingSource> 组件成员，以编程方式允许相同的功能。</span><span class="sxs-lookup"><span data-stu-id="12c07-107">For each button on the <xref:System.Windows.Forms.BindingNavigator> control, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically allows the same functionality.</span></span> <span data-ttu-id="12c07-108">例如，<xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> 按钮对应 <xref:System.Windows.Forms.BindingSource> 组件的 <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> 方法，<xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> 按钮对应 <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> 方法，依次类推。</span><span class="sxs-lookup"><span data-stu-id="12c07-108">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span> <span data-ttu-id="12c07-109">这样，启用 <xref:System.Windows.Forms.BindingNavigator> 控件导航数据记录就如同在窗体上将其 <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> 属性设置为适当的 <xref:System.Windows.Forms.BindingSource> 组件一样简单。</span><span class="sxs-lookup"><span data-stu-id="12c07-109">As a result, enabling the <xref:System.Windows.Forms.BindingNavigator> control to navigate data records is a simple as setting its <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the appropriate <xref:System.Windows.Forms.BindingSource> component on the form.</span></span>  
  
### <a name="to-set-up-the-bindingnavigator-control"></a><span data-ttu-id="12c07-110">设置 BindingNavigator 控件</span><span class="sxs-lookup"><span data-stu-id="12c07-110">To set up the BindingNavigator control</span></span>  
  
1.  <span data-ttu-id="12c07-111">添加一个名为 `bindingSource1` 的 <xref:System.Windows.Forms.BindingSource> 组件和两个分别名为 `textBox1` 和 `textBox2` 的 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="12c07-111">Add a <xref:System.Windows.Forms.BindingSource> component named `bindingSource1` and two <xref:System.Windows.Forms.TextBox> controls named `textBox1` and `textBox2`.</span></span>  
  
2.  <span data-ttu-id="12c07-112">将 `bindingSource1` 绑定到数据，并将文本框控件绑定到 `bindingSource1`。</span><span class="sxs-lookup"><span data-stu-id="12c07-112">Bind `bindingSource1` to data, and the textbox controls to `bindingSource1`.</span></span> <span data-ttu-id="12c07-113">若要执行此操作，请将下面的代码粘贴到窗体中，并从窗体的构造函数调用 `LoadData` 或调用 <xref:System.Windows.Forms.Form.Load> 事件处理方法中。</span><span class="sxs-lookup"><span data-stu-id="12c07-113">To do this, paste the following code into your form and call `LoadData` from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="12c07-114">将名为 `bindingNavigator1` 的 <xref:System.Windows.Forms.BindingNavigator> 控件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="12c07-114">Add a <xref:System.Windows.Forms.BindingNavigator> control named `bindingNavigator1` to your form.</span></span>  
  
4.  <span data-ttu-id="12c07-115">将 `bindingNavigator1`的 <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> 属性设置为 `bindingSource1`。</span><span class="sxs-lookup"><span data-stu-id="12c07-115">Set the <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property for `bindingNavigator1` to `bindingSource1`.</span></span> <span data-ttu-id="12c07-116">可以使用设计器或用代码执行此操作。</span><span class="sxs-lookup"><span data-stu-id="12c07-116">You can do this with the designer or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="12c07-117">示例</span><span class="sxs-lookup"><span data-stu-id="12c07-117">Example</span></span>  
 <span data-ttu-id="12c07-118">下面的代码示例是前面所列步骤的完整示例。</span><span class="sxs-lookup"><span data-stu-id="12c07-118">The following code example is the complete example for the steps listed previously.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="12c07-119">编译代码</span><span class="sxs-lookup"><span data-stu-id="12c07-119">Compiling the Code</span></span>  
 <span data-ttu-id="12c07-120">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="12c07-120">This example requires:</span></span>  
  
-   <span data-ttu-id="12c07-121">对 System、System.Data、System.Drawing、System.Windows.Forms 和 System.Xml 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="12c07-121">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="12c07-122">为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="12c07-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="12c07-123">你也可以通过将代码粘贴到新项目中生成 Visual Studio 中的此示例。</span><span class="sxs-lookup"><span data-stu-id="12c07-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="12c07-124">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="12c07-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c07-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="12c07-125">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [<span data-ttu-id="12c07-126">BindingNavigator 控件</span><span class="sxs-lookup"><span data-stu-id="12c07-126">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="12c07-127">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="12c07-127">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
