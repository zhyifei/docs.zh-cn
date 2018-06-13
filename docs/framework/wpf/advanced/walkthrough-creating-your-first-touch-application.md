---
title: 演练：创建您的第一个触控应用程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
ms.openlocfilehash: 94a97c30179f7a8231426e31b8cacc364629ffc3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548346"
---
# <a name="walkthrough-creating-your-first-touch-application"></a><span data-ttu-id="2fd54-102">演练：创建您的第一个触控应用程序</span><span class="sxs-lookup"><span data-stu-id="2fd54-102">Walkthrough: Creating Your First Touch Application</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="2fd54-103"> 允许应用程序响应触摸屏。</span><span class="sxs-lookup"><span data-stu-id="2fd54-103"> enables applications to respond to touch.</span></span> <span data-ttu-id="2fd54-104">例如，你可以通过使用一个与应用程序交互或多个手指触摸式设备，如本演练中创建的应用程序使用户能够移动，请触摸屏上调整大小，或通过使用触摸旋转单个对象。</span><span class="sxs-lookup"><span data-stu-id="2fd54-104">For example, you can interact with an application by using one or more fingers on a touch-sensitive device, such as a touchscreen This walkthrough creates an application that enables the user to move, resize, or rotate a single object by using touch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2fd54-105">系统必备</span><span class="sxs-lookup"><span data-stu-id="2fd54-105">Prerequisites</span></span>  
 <span data-ttu-id="2fd54-106">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="2fd54-106">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)]<span data-ttu-id="2fd54-107">。</span><span class="sxs-lookup"><span data-stu-id="2fd54-107">.</span></span>  
  
-   <span data-ttu-id="2fd54-108">Windows 7。</span><span class="sxs-lookup"><span data-stu-id="2fd54-108">Windows 7.</span></span>  
  
-   <span data-ttu-id="2fd54-109">接受触摸屏输入，如触摸屏，能够支持 Windows 触摸屏的设备。</span><span class="sxs-lookup"><span data-stu-id="2fd54-109">A device that accepts touch input, such as a touchscreen, that supports Windows Touch.</span></span>  
  
 <span data-ttu-id="2fd54-110">此外，应该基本了解如何创建中的应用程序的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，尤其是如何订阅和处理事件。</span><span class="sxs-lookup"><span data-stu-id="2fd54-110">Additionally, you should have a basic understanding of how to create an application in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especially how to subscribe to and handle an event.</span></span> <span data-ttu-id="2fd54-111">有关详细信息，请参阅[演练： 我第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd54-111">For more information, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="creating-the-application"></a><span data-ttu-id="2fd54-112">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="2fd54-112">Creating the Application</span></span>  
  
#### <a name="to-create-the-application"></a><span data-ttu-id="2fd54-113">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="2fd54-113">To create the application</span></span>  
  
1.  <span data-ttu-id="2fd54-114">在 Visual Basic 或 Visual C# 中创建名为 `BasicManipulation` 的新 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="2fd54-114">Create a new WPF Application project in Visual Basic or Visual C# named `BasicManipulation`.</span></span> <span data-ttu-id="2fd54-115">有关详细信息，请参阅[如何：创建新的 WPF 应用程序项目](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)。</span><span class="sxs-lookup"><span data-stu-id="2fd54-115">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="2fd54-116">MainWindow.xaml 的内容替换为以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="2fd54-116">Replace the contents of MainWindow.xaml with the following XAML.</span></span>  
  
     <span data-ttu-id="2fd54-117">此标记创建的简单应用程序包含一个红色<xref:System.Windows.Shapes.Rectangle>上<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="2fd54-117">This markup creates a simple application that contains a red <xref:System.Windows.Shapes.Rectangle> on a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="2fd54-118"><xref:System.Windows.UIElement.IsManipulationEnabled%2A>属性<xref:System.Windows.Shapes.Rectangle>设置为 true，因此，它将收到操作事件。</span><span class="sxs-lookup"><span data-stu-id="2fd54-118">The <xref:System.Windows.UIElement.IsManipulationEnabled%2A> property of the <xref:System.Windows.Shapes.Rectangle> is set to true so that it will receive manipulation events.</span></span> <span data-ttu-id="2fd54-119">应用程序订阅<xref:System.Windows.UIElement.ManipulationStarting>， <xref:System.Windows.UIElement.ManipulationDelta>，和<xref:System.Windows.UIElement.ManipulationInertiaStarting>事件。</span><span class="sxs-lookup"><span data-stu-id="2fd54-119">The application subscribes to the <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, and <xref:System.Windows.UIElement.ManipulationInertiaStarting> events.</span></span> <span data-ttu-id="2fd54-120">这些事件包含要移动的逻辑<xref:System.Windows.Shapes.Rectangle>用户处理。</span><span class="sxs-lookup"><span data-stu-id="2fd54-120">These events contain the logic to move the <xref:System.Windows.Shapes.Rectangle> when the user manipulates it.</span></span>  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  <span data-ttu-id="2fd54-121">如果使用的 Visual Basic 中，在 MainWindow.xaml 的第一行中，将`x:Class="BasicManipulation.MainWindow"`与`x:Class="MainWindow"`。</span><span class="sxs-lookup"><span data-stu-id="2fd54-121">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="BasicManipulation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
4.  <span data-ttu-id="2fd54-122">在`MainWindow`类中，添加以下<xref:System.Windows.UIElement.ManipulationStarting>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2fd54-122">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationStarting> event handler.</span></span>  
  
     <span data-ttu-id="2fd54-123"><xref:System.Windows.UIElement.ManipulationStarting>事件发生时[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]检测到触控输入开始的对象执行操作。</span><span class="sxs-lookup"><span data-stu-id="2fd54-123">The <xref:System.Windows.UIElement.ManipulationStarting> event occurs when [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] detects that touch input begins to manipulate an object.</span></span> <span data-ttu-id="2fd54-124">该代码指定操作的位置应为相对于<xref:System.Windows.Window>通过设置<xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="2fd54-124">The code specifies that the position of the manipulation should be relative to the <xref:System.Windows.Window> by setting the <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> property.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  <span data-ttu-id="2fd54-125">在`MainWindow`类中，添加以下<xref:System.Windows.Input.ManipulationDelta>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2fd54-125">In the `MainWindow` class, add the following <xref:System.Windows.Input.ManipulationDelta> event handler.</span></span>  
  
     <span data-ttu-id="2fd54-126"><xref:System.Windows.Input.ManipulationDelta>触摸输入更改位置，并且可以在操作过程中发生多次时发生事件。</span><span class="sxs-lookup"><span data-stu-id="2fd54-126">The <xref:System.Windows.Input.ManipulationDelta> event occurs when the touch input changes position and can occur multiple times during a manipulation.</span></span> <span data-ttu-id="2fd54-127">引发手指后，也可能发生此事件。</span><span class="sxs-lookup"><span data-stu-id="2fd54-127">The event can also occur after a finger is raised.</span></span> <span data-ttu-id="2fd54-128">例如，如果用户在屏幕上拖动手指<xref:System.Windows.Input.ManipulationDelta>事件在手指移动时出现多次。</span><span class="sxs-lookup"><span data-stu-id="2fd54-128">For example, if the user drags a finger across a screen, the <xref:System.Windows.Input.ManipulationDelta> event occurs multiple times as the finger moves.</span></span> <span data-ttu-id="2fd54-129">当用户悬停在屏幕中，为指<xref:System.Windows.Input.ManipulationDelta>事件会不断发生以模拟惯性。</span><span class="sxs-lookup"><span data-stu-id="2fd54-129">When the user raises a finger from the screen, the <xref:System.Windows.Input.ManipulationDelta> event keeps occurring to simulate inertia.</span></span>  
  
     <span data-ttu-id="2fd54-130">该代码将应用<xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A>到<xref:System.Windows.UIElement.RenderTransform%2A>的<xref:System.Windows.Shapes.Rectangle>将其移动在用户移动触控输入。</span><span class="sxs-lookup"><span data-stu-id="2fd54-130">The code applies the <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> to the <xref:System.Windows.UIElement.RenderTransform%2A> of the <xref:System.Windows.Shapes.Rectangle> to move it as the user moves the touch input.</span></span> <span data-ttu-id="2fd54-131">它还检查是否<xref:System.Windows.Shapes.Rectangle>超出数组界限的<xref:System.Windows.Window>事件惯性过程中发生时。</span><span class="sxs-lookup"><span data-stu-id="2fd54-131">It also checks whether the <xref:System.Windows.Shapes.Rectangle> is outside the bounds of the <xref:System.Windows.Window> when the event occurs during inertia.</span></span> <span data-ttu-id="2fd54-132">如果是，应用程序调用<xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType>方法来结束操作。</span><span class="sxs-lookup"><span data-stu-id="2fd54-132">If so, the application calls the <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> method to end the manipulation.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  <span data-ttu-id="2fd54-133">在`MainWindow`类中，添加以下<xref:System.Windows.UIElement.ManipulationInertiaStarting>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2fd54-133">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationInertiaStarting> event handler.</span></span>  
  
     <span data-ttu-id="2fd54-134"><xref:System.Windows.UIElement.ManipulationInertiaStarting>用户悬停在屏幕中的所有指时发生事件。</span><span class="sxs-lookup"><span data-stu-id="2fd54-134">The <xref:System.Windows.UIElement.ManipulationInertiaStarting> event occurs when the user raises all fingers from the screen.</span></span> <span data-ttu-id="2fd54-135">该代码设置的初始速度和减速移动、 扩展以及在该矩形的旋转。</span><span class="sxs-lookup"><span data-stu-id="2fd54-135">The code sets the initial velocity and deceleration for the movement, expansion, and rotation of the rectangle.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  <span data-ttu-id="2fd54-136">生成并运行该项目。</span><span class="sxs-lookup"><span data-stu-id="2fd54-136">Build and run the project.</span></span>  
  
     <span data-ttu-id="2fd54-137">你应看到在窗口中显示一个红色正方形。</span><span class="sxs-lookup"><span data-stu-id="2fd54-137">You should see a red square appear in the window.</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="2fd54-138">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="2fd54-138">Testing the Application</span></span>  
 <span data-ttu-id="2fd54-139">若要测试应用程序，请尝试执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="2fd54-139">To test the application, try the following manipulations.</span></span> <span data-ttu-id="2fd54-140">请注意你可以执行多个以下项之一在同一时间进行操作。</span><span class="sxs-lookup"><span data-stu-id="2fd54-140">Note that you can do more than one of the following at the same time.</span></span>  
  
-   <span data-ttu-id="2fd54-141">若要移动<xref:System.Windows.Shapes.Rectangle>，置于手指<xref:System.Windows.Shapes.Rectangle>和在屏幕上移动上方的手指。</span><span class="sxs-lookup"><span data-stu-id="2fd54-141">To move the <xref:System.Windows.Shapes.Rectangle>, put a finger on the <xref:System.Windows.Shapes.Rectangle> and move the finger across the screen.</span></span>  
  
-   <span data-ttu-id="2fd54-142">若要调整大小<xref:System.Windows.Shapes.Rectangle>，放入两根手指<xref:System.Windows.Shapes.Rectangle>并移动指，或将其彼此。</span><span class="sxs-lookup"><span data-stu-id="2fd54-142">To resize the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and move the fingers closer together or farther apart from each other.</span></span>  
  
-   <span data-ttu-id="2fd54-143">要旋转<xref:System.Windows.Shapes.Rectangle>，放入两根手指<xref:System.Windows.Shapes.Rectangle>并旋转相互环绕指。</span><span class="sxs-lookup"><span data-stu-id="2fd54-143">To rotate the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and rotate the fingers around each other.</span></span>  
  
 <span data-ttu-id="2fd54-144">若要使惯性，快速执行上一操作时引发手指从屏幕。</span><span class="sxs-lookup"><span data-stu-id="2fd54-144">To cause inertia, quickly raise your fingers from the screen as you perform the previous manipulations.</span></span> <span data-ttu-id="2fd54-145"><xref:System.Windows.Shapes.Rectangle>将继续移动、 调整大小，或旋转它停止前几秒钟。</span><span class="sxs-lookup"><span data-stu-id="2fd54-145">The <xref:System.Windows.Shapes.Rectangle> will continue to move, resize, or rotate for a few seconds before it stops.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd54-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fd54-146">See Also</span></span>  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
