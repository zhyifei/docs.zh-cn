---
title: 演练：启用拖放用户控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: a2aa1d09b922809f42fe14bd674c2a87b9e5a3f8
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747790"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="21cdb-102">演练：启用拖放用户控件</span><span class="sxs-lookup"><span data-stu-id="21cdb-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="21cdb-103">本演练演示如何创建可在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中参与拖放数据传输的自定义用户控件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="21cdb-104">在本演练中，你将创建自定义 WPF<xref:System.Windows.Controls.UserControl>表示圆形形状。</span><span class="sxs-lookup"><span data-stu-id="21cdb-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="21cdb-105">你将在该控件上实现可通过拖放进行数据传输的功能。</span><span class="sxs-lookup"><span data-stu-id="21cdb-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="21cdb-106">例如，如果从一个圆形控件拖到另一个圆形控件，则会将填充颜色数据从源圆形复制到目标圆形。</span><span class="sxs-lookup"><span data-stu-id="21cdb-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="21cdb-107">如果从到一个圆形控件拖<xref:System.Windows.Controls.TextBox>，填充颜色的字符串表示形式复制到<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="21cdb-108">您还将创建包含两个面板控件的小型应用程序和一个<xref:System.Windows.Controls.TextBox>测试拖放功能。</span><span class="sxs-lookup"><span data-stu-id="21cdb-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="21cdb-109">你将编写可使面板处理放置的圆形数据的代码，这样就可以将圆形从一个面板的 Children 集合移动或复制到其他面板。</span><span class="sxs-lookup"><span data-stu-id="21cdb-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="21cdb-110">本演练阐释了以下任务：</span><span class="sxs-lookup"><span data-stu-id="21cdb-110">This walkthrough illustrates the following tasks:</span></span>

-   <span data-ttu-id="21cdb-111">创建自定义用户控件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-111">Create a custom user control.</span></span>

-   <span data-ttu-id="21cdb-112">使用户控件成为拖动源。</span><span class="sxs-lookup"><span data-stu-id="21cdb-112">Enable the user control to be a drag source.</span></span>

-   <span data-ttu-id="21cdb-113">使用户控件成为拖放目标。</span><span class="sxs-lookup"><span data-stu-id="21cdb-113">Enable the user control to be a drop target.</span></span>

-   <span data-ttu-id="21cdb-114">使面板能够接收用户控件中放置的数据。</span><span class="sxs-lookup"><span data-stu-id="21cdb-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="21cdb-115">系统必备</span><span class="sxs-lookup"><span data-stu-id="21cdb-115">Prerequisites</span></span>

<span data-ttu-id="21cdb-116">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="21cdb-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="21cdb-117">创建应用程序项目</span><span class="sxs-lookup"><span data-stu-id="21cdb-117">Create the Application Project</span></span>
 <span data-ttu-id="21cdb-118">在本部分中，您将创建应用程序基础结构，其中包括主页，其中两个面板和<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1.  <span data-ttu-id="21cdb-119">在 Visual Basic 或 Visual C# 中创建名为 `DragDropExample` 的新 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="21cdb-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="21cdb-120">有关详细信息，请参见[演练：我第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="21cdb-120">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2.  <span data-ttu-id="21cdb-121">打开 MainWindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="21cdb-121">Open MainWindow.xaml.</span></span>

3.  <span data-ttu-id="21cdb-122">添加以下标记的开始和结束之间<xref:System.Windows.Controls.Grid>标记。</span><span class="sxs-lookup"><span data-stu-id="21cdb-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="21cdb-123">此标记将创建用于测试应用程序的用户界面。</span><span class="sxs-lookup"><span data-stu-id="21cdb-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="21cdb-124">向项目添加新的用户控件</span><span class="sxs-lookup"><span data-stu-id="21cdb-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="21cdb-125">本节将介绍如何向项目添加新的用户控件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-125">In this section, you will add a new user control to the project.</span></span>

1.  <span data-ttu-id="21cdb-126">在“项目”菜单中，选择“添加用户控件”。</span><span class="sxs-lookup"><span data-stu-id="21cdb-126">On the Project menu, select **Add User Control**.</span></span>

2.  <span data-ttu-id="21cdb-127">在中**添加新项**对话框框中，将名称更改为`Circle.xaml`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="21cdb-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="21cdb-128">Circle.xaml 及其代码隐藏内容将添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="21cdb-128">Circle.xaml and its code-behind is added to the project.</span></span>

3.  <span data-ttu-id="21cdb-129">打开 Circle.xaml。</span><span class="sxs-lookup"><span data-stu-id="21cdb-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="21cdb-130">此文件将包含用户控件的用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="21cdb-130">This file will contain the user interface elements of the user control.</span></span>

4.  <span data-ttu-id="21cdb-131">将以下标记添加到根<xref:System.Windows.Controls.Grid>若要创建将蓝色圆形作为其 UI 的简单用户控件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5.  <span data-ttu-id="21cdb-132">打开 Circle.xaml.cs 或 Circle.xaml.vb。</span><span class="sxs-lookup"><span data-stu-id="21cdb-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6.  <span data-ttu-id="21cdb-133">在 C# 中，在默认构造函数后面添加以下代码以创建复制构造函数。</span><span class="sxs-lookup"><span data-stu-id="21cdb-133">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="21cdb-134">在 Visual Basic 中，添加以下代码以同时创建默认构造函数和复制构造函数。</span><span class="sxs-lookup"><span data-stu-id="21cdb-134">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>

     <span data-ttu-id="21cdb-135">若要允许复制用户控件，需在代码隐藏文件中添加复制构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="21cdb-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="21cdb-136">在简化的圆形用户控件中，将只复制该用户控件的填充和大小。</span><span class="sxs-lookup"><span data-stu-id="21cdb-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="21cdb-137">将用户控件添加到主窗口</span><span class="sxs-lookup"><span data-stu-id="21cdb-137">Add the user control to the main window</span></span>

1.  <span data-ttu-id="21cdb-138">打开 MainWindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="21cdb-138">Open MainWindow.xaml.</span></span>

2.  <span data-ttu-id="21cdb-139">将以下 XAML 添加到起始<xref:System.Windows.Window>标记以创建对当前应用程序的 XML 命名空间引用。</span><span class="sxs-lookup"><span data-stu-id="21cdb-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```
    xmlns:local="clr-namespace:DragDropExample"
    ```

3.  <span data-ttu-id="21cdb-140">在第一个<xref:System.Windows.Controls.StackPanel>，添加以下 XAML 在第一个面板中创建圆形用户控件的两个实例。</span><span class="sxs-lookup"><span data-stu-id="21cdb-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="21cdb-141">此面板的完整 XAML 如下所示。</span><span class="sxs-lookup"><span data-stu-id="21cdb-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="21cdb-142">在用户控件中实现拖动源事件</span><span class="sxs-lookup"><span data-stu-id="21cdb-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="21cdb-143">在本部分中，你将重写<xref:System.Windows.UIElement.OnMouseMove%2A>方法并启动拖放操作。</span><span class="sxs-lookup"><span data-stu-id="21cdb-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="21cdb-144">如果已开始拖动 （按下鼠标按钮并移动鼠标），将打包到传输的数据<xref:System.Windows.DataObject>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="21cdb-145">在这种情况下，圆形控件将打包三个数据项：其填充颜色的字符串表示形式、其高度的双精度表示形式以及其自身的副本。</span><span class="sxs-lookup"><span data-stu-id="21cdb-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="21cdb-146">启动拖放操作</span><span class="sxs-lookup"><span data-stu-id="21cdb-146">To initiate a drag-and-drop operation</span></span>

1.  <span data-ttu-id="21cdb-147">打开 Circle.xaml.cs 或 Circle.xaml.vb。</span><span class="sxs-lookup"><span data-stu-id="21cdb-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="21cdb-148">添加以下<xref:System.Windows.UIElement.OnMouseMove%2A>替代，以便提供类处理<xref:System.Windows.UIElement.MouseMove>事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="21cdb-149">这<xref:System.Windows.UIElement.OnMouseMove%2A>替代执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="21cdb-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="21cdb-150">检查移动鼠标时是否按下了鼠标左键。</span><span class="sxs-lookup"><span data-stu-id="21cdb-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    -   <span data-ttu-id="21cdb-151">将圆形数据打包到<xref:System.Windows.DataObject>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="21cdb-152">在这种情况下，圆形控件将打包三个数据项：其填充颜色的字符串表示形式、其高度的双精度表示形式以及其自身的副本。</span><span class="sxs-lookup"><span data-stu-id="21cdb-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    -   <span data-ttu-id="21cdb-153">调用静态<xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType>方法启动拖放操作。</span><span class="sxs-lookup"><span data-stu-id="21cdb-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="21cdb-154">传递到以下三个参数<xref:System.Windows.DragDrop.DoDragDrop%2A>方法：</span><span class="sxs-lookup"><span data-stu-id="21cdb-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        -   <span data-ttu-id="21cdb-155">`dragSource` – 对此控件的引用。</span><span class="sxs-lookup"><span data-stu-id="21cdb-155">`dragSource` – A reference to this control.</span></span>

        -   <span data-ttu-id="21cdb-156">`data` –<xref:System.Windows.DataObject>前面的代码中创建。</span><span class="sxs-lookup"><span data-stu-id="21cdb-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        -   <span data-ttu-id="21cdb-157">`allowedEffects` – 允许的拖放操作，即<xref:System.Windows.DragDropEffects.Copy>或<xref:System.Windows.DragDropEffects.Move>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3.  <span data-ttu-id="21cdb-158">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="21cdb-158">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="21cdb-159">单击其中一个圆形控件并将其拖到面板、 另一个圆形和<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="21cdb-160">当上拖动<xref:System.Windows.Controls.TextBox>，光标发生变化，以指示移动。</span><span class="sxs-lookup"><span data-stu-id="21cdb-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5.  <span data-ttu-id="21cdb-161">同时通过拖动圆形<xref:System.Windows.Controls.TextBox>，按**Ctrl**密钥。</span><span class="sxs-lookup"><span data-stu-id="21cdb-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="21cdb-162">请注意光标是如何更改以指示复制的。</span><span class="sxs-lookup"><span data-stu-id="21cdb-162">Notice how the cursor changes to indicate a copy.</span></span>

6.  <span data-ttu-id="21cdb-163">拖放到上的一个圆圈<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="21cdb-164">圆形填充颜色的字符串表示形式追加到<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="21cdb-165">![圆形填充颜色的字符串表示形式](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="21cdb-165">![String representation of Circle's fill color](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="21cdb-166">默认情况下，光标会在拖放操作过程中更改，以指示放置数据会产生的效果。</span><span class="sxs-lookup"><span data-stu-id="21cdb-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="21cdb-167">你可以自定义提供给用户，通过处理反馈<xref:System.Windows.UIElement.GiveFeedback>事件和设置不同光标。</span><span class="sxs-lookup"><span data-stu-id="21cdb-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="21cdb-168">向用户提供反馈</span><span class="sxs-lookup"><span data-stu-id="21cdb-168">Give feedback to the user</span></span>

1.  <span data-ttu-id="21cdb-169">打开 Circle.xaml.cs 或 Circle.xaml.vb。</span><span class="sxs-lookup"><span data-stu-id="21cdb-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="21cdb-170">添加以下<xref:System.Windows.UIElement.OnGiveFeedback%2A>替代，以便提供类处理<xref:System.Windows.UIElement.GiveFeedback>事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="21cdb-171">这<xref:System.Windows.UIElement.OnGiveFeedback%2A>替代执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="21cdb-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="21cdb-172">检查<xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>拖放目标中设置的值<xref:System.Windows.UIElement.DragOver>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="21cdb-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    -   <span data-ttu-id="21cdb-173">设置基于自定义光标<xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>值。</span><span class="sxs-lookup"><span data-stu-id="21cdb-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="21cdb-174">该光标旨在向用户提供关于放置数据所产生的效果的可视反馈。</span><span class="sxs-lookup"><span data-stu-id="21cdb-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3.  <span data-ttu-id="21cdb-175">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="21cdb-175">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="21cdb-176">拖动其中一个圆形的面板，另一个圆形，通过控制和<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="21cdb-177">请注意，现在的光标是你在中指定的自定义光标<xref:System.Windows.UIElement.OnGiveFeedback%2A>重写。</span><span class="sxs-lookup"><span data-stu-id="21cdb-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="21cdb-178">![使用自定义光标拖放](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="21cdb-178">![Drag and drop with custom cursors](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5.  <span data-ttu-id="21cdb-179">选择的文本`green`从<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6.  <span data-ttu-id="21cdb-180">将 `green` 文本拖到一个圆形控件上。</span><span class="sxs-lookup"><span data-stu-id="21cdb-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="21cdb-181">请注意，将显示默认光标以指示拖放操作效果。</span><span class="sxs-lookup"><span data-stu-id="21cdb-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="21cdb-182">反馈光标始终由拖动源设置。</span><span class="sxs-lookup"><span data-stu-id="21cdb-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="21cdb-183">在用户控件中实现拖放目标事件</span><span class="sxs-lookup"><span data-stu-id="21cdb-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="21cdb-184">在本节中，你将指定用户控件为拖放目标，替代可使用户控件成为拖放目标的方法，并处理用户控件上放置的数据。</span><span class="sxs-lookup"><span data-stu-id="21cdb-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="21cdb-185">使用户控件成为拖放目标</span><span class="sxs-lookup"><span data-stu-id="21cdb-185">To enable the user control to be a drop target</span></span>

1.  <span data-ttu-id="21cdb-186">打开 Circle.xaml。</span><span class="sxs-lookup"><span data-stu-id="21cdb-186">Open Circle.xaml.</span></span>

2.  <span data-ttu-id="21cdb-187">在左括号<xref:System.Windows.Controls.UserControl>标记中，添加<xref:System.Windows.UIElement.AllowDrop%2A>属性并将其设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="21cdb-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="21cdb-188"><xref:System.Windows.UIElement.OnDrop%2A>时调用方法<xref:System.Windows.UIElement.AllowDrop%2A>属性设置为`true`和拖动源中的数据放置在圆形用户控件上。</span><span class="sxs-lookup"><span data-stu-id="21cdb-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="21cdb-189">在这种方法中，将处理已放置的数据，并将这些数据应用于圆形。</span><span class="sxs-lookup"><span data-stu-id="21cdb-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="21cdb-190">处理已放置的数据</span><span class="sxs-lookup"><span data-stu-id="21cdb-190">To process the dropped data</span></span>

1.  <span data-ttu-id="21cdb-191">打开 Circle.xaml.cs 或 Circle.xaml.vb。</span><span class="sxs-lookup"><span data-stu-id="21cdb-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="21cdb-192">添加以下<xref:System.Windows.UIElement.OnDrop%2A>替代，以便提供类处理<xref:System.Windows.UIElement.Drop>事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="21cdb-193">这<xref:System.Windows.UIElement.OnDrop%2A>替代执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="21cdb-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="21cdb-194">使用<xref:System.Windows.DataObject.GetDataPresent%2A>方法用于检查拖动的数据是否包含字符串对象。</span><span class="sxs-lookup"><span data-stu-id="21cdb-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    -   <span data-ttu-id="21cdb-195">使用<xref:System.Windows.DataObject.GetData%2A>方法提取字符串数据，如果存在。</span><span class="sxs-lookup"><span data-stu-id="21cdb-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    -   <span data-ttu-id="21cdb-196">使用<xref:System.Windows.Media.BrushConverter>尝试将字符串转换为<xref:System.Windows.Media.Brush>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    -   <span data-ttu-id="21cdb-197">如果转换成功，将应用到画笔<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Ellipse>提供圆形控件的 UI。</span><span class="sxs-lookup"><span data-stu-id="21cdb-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    -   <span data-ttu-id="21cdb-198">标记<xref:System.Windows.UIElement.Drop>为已处理的事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="21cdb-199">应将放置事件标记为已处理，这样接收此事件的其他元素才会知道圆形用户控件已处理了该事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3.  <span data-ttu-id="21cdb-200">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="21cdb-200">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="21cdb-201">选择的文本`green`在<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5.  <span data-ttu-id="21cdb-202">将文本拖放到一个圆形控件上。</span><span class="sxs-lookup"><span data-stu-id="21cdb-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="21cdb-203">该圆形会从蓝色变为绿色。</span><span class="sxs-lookup"><span data-stu-id="21cdb-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="21cdb-204">![将字符串转换为画笔](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="21cdb-204">![Convert a string to a brush](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6.  <span data-ttu-id="21cdb-205">键入的文本`green`在<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7.  <span data-ttu-id="21cdb-206">选择的文本`gre`在<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8.  <span data-ttu-id="21cdb-207">将其拖放到一个圆形控件上。</span><span class="sxs-lookup"><span data-stu-id="21cdb-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="21cdb-208">请注意，光标会更改以指示允许放置，但圆形的颜色不会更改，因为 `gre` 不是有效颜色。</span><span class="sxs-lookup"><span data-stu-id="21cdb-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="21cdb-209">从绿色圆形控件拖放到蓝色圆形控件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="21cdb-210">该圆形会从蓝色变为绿色。</span><span class="sxs-lookup"><span data-stu-id="21cdb-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="21cdb-211">请注意，显示的光标取决于是否<xref:System.Windows.Controls.TextBox>还是圆形作为拖动源。</span><span class="sxs-lookup"><span data-stu-id="21cdb-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="21cdb-212">设置<xref:System.Windows.UIElement.AllowDrop%2A>属性设置为`true`和处理放置的数据是只需要启用要拖放目标的元素。</span><span class="sxs-lookup"><span data-stu-id="21cdb-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="21cdb-213">但是，若要提供更好的用户体验，您还应处理<xref:System.Windows.UIElement.DragEnter>， <xref:System.Windows.UIElement.DragLeave>，和<xref:System.Windows.UIElement.DragOver>事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="21cdb-214">在这些事件中，你可以在放置数据前执行检查并向用户提供其他反馈。</span><span class="sxs-lookup"><span data-stu-id="21cdb-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="21cdb-215">将数据拖动到圆形用户控件上时，该控件应通知拖动源它是否可以处理所拖动的数据。</span><span class="sxs-lookup"><span data-stu-id="21cdb-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="21cdb-216">如果该控件不知如何处理这些数据，则它应拒绝放置。</span><span class="sxs-lookup"><span data-stu-id="21cdb-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="21cdb-217">若要执行此操作，你将处理<xref:System.Windows.UIElement.DragOver>事件并设置<xref:System.Windows.DragEventArgs.Effects%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="21cdb-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="21cdb-218">验证是否允许数据放置</span><span class="sxs-lookup"><span data-stu-id="21cdb-218">To verify that the data drop is allowed</span></span>

1.  <span data-ttu-id="21cdb-219">打开 Circle.xaml.cs 或 Circle.xaml.vb。</span><span class="sxs-lookup"><span data-stu-id="21cdb-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="21cdb-220">添加以下<xref:System.Windows.UIElement.OnDragOver%2A>替代，以便提供类处理<xref:System.Windows.UIElement.DragOver>事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="21cdb-221">这<xref:System.Windows.UIElement.OnDragOver%2A>替代执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="21cdb-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="21cdb-222">将 <xref:System.Windows.DragEventArgs.Effects%2A> 属性设置为 <xref:System.Windows.DragDropEffects.None>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    -   <span data-ttu-id="21cdb-223">执行在中执行的相同检查<xref:System.Windows.UIElement.OnDrop%2A>方法，以确定圆形用户控件是否可以处理拖动的数据。</span><span class="sxs-lookup"><span data-stu-id="21cdb-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    -   <span data-ttu-id="21cdb-224">如果用户控件可以处理数据，设置<xref:System.Windows.DragEventArgs.Effects%2A>属性设置为<xref:System.Windows.DragDropEffects.Copy>或<xref:System.Windows.DragDropEffects.Move>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3.  <span data-ttu-id="21cdb-225">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="21cdb-225">Press **F5** to build and run the application.</span></span>

4.  <span data-ttu-id="21cdb-226">选择的文本`gre`在<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5.  <span data-ttu-id="21cdb-227">将文本拖到一个圆形控件上。</span><span class="sxs-lookup"><span data-stu-id="21cdb-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="21cdb-228">请注意，光标此时会更改以指示不允许放置，因为 `gre` 不是有效颜色。</span><span class="sxs-lookup"><span data-stu-id="21cdb-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="21cdb-229">可通过应用拖放操作预览进一步增强用户体验。</span><span class="sxs-lookup"><span data-stu-id="21cdb-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="21cdb-230">对于圆形用户控件，您将重写<xref:System.Windows.UIElement.OnDragEnter%2A>和<xref:System.Windows.UIElement.OnDragLeave%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="21cdb-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="21cdb-231">当将数据拖动控件当前的背景上<xref:System.Windows.Shapes.Shape.Fill%2A>保存在一个占位符变量中。</span><span class="sxs-lookup"><span data-stu-id="21cdb-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="21cdb-232">然后转换为画笔并应用于字符串<xref:System.Windows.Shapes.Ellipse>提供圆形 UI。</span><span class="sxs-lookup"><span data-stu-id="21cdb-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="21cdb-233">如果将数据拖动出该圆形而没有放置，原始<xref:System.Windows.Shapes.Shape.Fill%2A>值重新应用于该圆形。</span><span class="sxs-lookup"><span data-stu-id="21cdb-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="21cdb-234">预览拖放操作的效果</span><span class="sxs-lookup"><span data-stu-id="21cdb-234">To preview the effects of the drag-and-drop operation</span></span>

1.  <span data-ttu-id="21cdb-235">打开 Circle.xaml.cs 或 Circle.xaml.vb。</span><span class="sxs-lookup"><span data-stu-id="21cdb-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2.  <span data-ttu-id="21cdb-236">在圆形类中，声明一个私有<xref:System.Windows.Media.Brush>名为变量`_previousFill`并将其初始化`null`。</span><span class="sxs-lookup"><span data-stu-id="21cdb-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3.  <span data-ttu-id="21cdb-237">添加以下<xref:System.Windows.UIElement.OnDragEnter%2A>替代，以便提供类处理<xref:System.Windows.UIElement.DragEnter>事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="21cdb-238">这<xref:System.Windows.UIElement.OnDragEnter%2A>替代执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="21cdb-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="21cdb-239">将保存<xref:System.Windows.Shapes.Shape.Fill%2A>的属性<xref:System.Windows.Shapes.Ellipse>中`_previousFill`变量。</span><span class="sxs-lookup"><span data-stu-id="21cdb-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    -   <span data-ttu-id="21cdb-240">执行在中执行的相同检查<xref:System.Windows.UIElement.OnDrop%2A>方法，以确定数据是否可以转换为<xref:System.Windows.Media.Brush>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    -   <span data-ttu-id="21cdb-241">如果数据转换为有效<xref:System.Windows.Media.Brush>，将其应用于<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Ellipse>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4.  <span data-ttu-id="21cdb-242">添加以下<xref:System.Windows.UIElement.OnDragLeave%2A>替代，以便提供类处理<xref:System.Windows.UIElement.DragLeave>事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="21cdb-243">这<xref:System.Windows.UIElement.OnDragLeave%2A>替代执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="21cdb-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    -   <span data-ttu-id="21cdb-244">适用<xref:System.Windows.Media.Brush>以保存`_previousFill`变量<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Ellipse>提供圆形用户控件的 UI。</span><span class="sxs-lookup"><span data-stu-id="21cdb-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5.  <span data-ttu-id="21cdb-245">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="21cdb-245">Press **F5** to build and run the application.</span></span>

6.  <span data-ttu-id="21cdb-246">选择的文本`green`在<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7.  <span data-ttu-id="21cdb-247">将该文本拖到一个圆形控件上而不放置。</span><span class="sxs-lookup"><span data-stu-id="21cdb-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="21cdb-248">该圆形会从蓝色变为绿色。</span><span class="sxs-lookup"><span data-stu-id="21cdb-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="21cdb-249">![预览拖放操作的效果](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="21cdb-249">![Preview the effects of a drag&#45;and&#45;drop operation](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8.  <span data-ttu-id="21cdb-250">将文本拖离该圆形控件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="21cdb-251">该圆形会从绿色变回蓝色。</span><span class="sxs-lookup"><span data-stu-id="21cdb-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="21cdb-252">使面板能够接收放置的数据</span><span class="sxs-lookup"><span data-stu-id="21cdb-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="21cdb-253">在本部分中，允许承载圆形用户控件，使其作为拖动圆形数据的放置目标的面板。</span><span class="sxs-lookup"><span data-stu-id="21cdb-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="21cdb-254">将实现的代码，使你可以将圆形从一个面板移动到另一个，或通过按下创建一个圆形控件的副本**Ctrl**拖放圆形时键。</span><span class="sxs-lookup"><span data-stu-id="21cdb-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1.  <span data-ttu-id="21cdb-255">打开 MainWindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="21cdb-255">Open MainWindow.xaml.</span></span>

2.  <span data-ttu-id="21cdb-256">以下 XAML 中的每个中所示<xref:System.Windows.Controls.StackPanel>控件，则添加的处理程序<xref:System.Windows.UIElement.DragOver>和<xref:System.Windows.UIElement.Drop>事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="21cdb-257">名称<xref:System.Windows.UIElement.DragOver>事件处理程序`panel_DragOver`，并将命名<xref:System.Windows.UIElement.Drop>事件处理程序`panel_Drop`。</span><span class="sxs-lookup"><span data-stu-id="21cdb-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3.  <span data-ttu-id="21cdb-258">打开 MainWindows.xaml.cs 或 MainWindow.xaml.vb。</span><span class="sxs-lookup"><span data-stu-id="21cdb-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4.  <span data-ttu-id="21cdb-259">添加以下代码为<xref:System.Windows.UIElement.DragOver>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="21cdb-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="21cdb-260">这<xref:System.Windows.UIElement.DragOver>事件处理程序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="21cdb-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    -   <span data-ttu-id="21cdb-261">检查拖动的数据包含已打包的中的"对象"数据<xref:System.Windows.DataObject>由圆形用户控件，并对的调用中传递<xref:System.Windows.DragDrop.DoDragDrop%2A>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    -   <span data-ttu-id="21cdb-262">如果"对象"数据存在，检查是否**Ctrl**按下键。</span><span class="sxs-lookup"><span data-stu-id="21cdb-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    -   <span data-ttu-id="21cdb-263">如果**Ctrl**按下键，集<xref:System.Windows.DragEventArgs.Effects%2A>属性设置为<xref:System.Windows.DragDropEffects.Copy>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="21cdb-264">否则，设置<xref:System.Windows.DragEventArgs.Effects%2A>属性设置为<xref:System.Windows.DragDropEffects.Move>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5.  <span data-ttu-id="21cdb-265">添加以下代码为<xref:System.Windows.UIElement.Drop>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="21cdb-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="21cdb-266">这<xref:System.Windows.UIElement.Drop>事件处理程序执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="21cdb-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    -   <span data-ttu-id="21cdb-267">检查是否<xref:System.Windows.UIElement.Drop>已处理事件。</span><span class="sxs-lookup"><span data-stu-id="21cdb-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="21cdb-268">例如，如果一个圆形放置在另一圈的句柄<xref:System.Windows.UIElement.Drop>事件，您不希望包含还处理该圆形的面板。</span><span class="sxs-lookup"><span data-stu-id="21cdb-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    -   <span data-ttu-id="21cdb-269">如果<xref:System.Windows.UIElement.Drop>不处理事件，检查是否**Ctrl**按下键。</span><span class="sxs-lookup"><span data-stu-id="21cdb-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    -   <span data-ttu-id="21cdb-270">如果**Ctrl**按下键时<xref:System.Windows.UIElement.Drop>发生，会复制该圆形控件并将其添加到<xref:System.Windows.Controls.Panel.Children%2A>的集合<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    -   <span data-ttu-id="21cdb-271">如果**Ctrl**未按下键，将移动从圆<xref:System.Windows.Controls.Panel.Children%2A>到其父面板的集合<xref:System.Windows.Controls.Panel.Children%2A>面板已被删除的集合。</span><span class="sxs-lookup"><span data-stu-id="21cdb-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    -   <span data-ttu-id="21cdb-272">集<xref:System.Windows.DragEventArgs.Effects%2A>属性以通知<xref:System.Windows.DragDrop.DoDragDrop%2A>方法是否执行了移动或复制操作。</span><span class="sxs-lookup"><span data-stu-id="21cdb-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6.  <span data-ttu-id="21cdb-273">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="21cdb-273">Press **F5** to build and run the application.</span></span>

7.  <span data-ttu-id="21cdb-274">选择的文本`green`从<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="21cdb-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8.  <span data-ttu-id="21cdb-275">将文本拖放到一个圆形控件上。</span><span class="sxs-lookup"><span data-stu-id="21cdb-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="21cdb-276">将一个圆形控件从左面板拖放到右面板。</span><span class="sxs-lookup"><span data-stu-id="21cdb-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="21cdb-277">该圆形会从<xref:System.Windows.Controls.Panel.Children%2A>左面板中的集合并添加到右侧面板的 Children 集合。</span><span class="sxs-lookup"><span data-stu-id="21cdb-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="21cdb-278">从面板到另一个面板将一个圆形控件拖放时按**Ctrl**密钥。</span><span class="sxs-lookup"><span data-stu-id="21cdb-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="21cdb-279">将复制该圆形并将副本添加到<xref:System.Windows.Controls.Panel.Children%2A>接收面板的集合。</span><span class="sxs-lookup"><span data-stu-id="21cdb-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="21cdb-280">![按住 Ctrl 键的同时拖动圆形](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="21cdb-280">![Dragging a Circle while pressing the CTRL key](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="21cdb-281">请参阅</span><span class="sxs-lookup"><span data-stu-id="21cdb-281">See also</span></span>

- [<span data-ttu-id="21cdb-282">拖放概述</span><span class="sxs-lookup"><span data-stu-id="21cdb-282">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)