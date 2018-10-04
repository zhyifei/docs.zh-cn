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
ms.openlocfilehash: 935999fd5ada93bedebb38462f9faa93b8ec923f
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48781474"
---
# <a name="walkthrough-creating-your-first-touch-application"></a><span data-ttu-id="39d4f-102">演练：创建您的第一个触控应用程序</span><span class="sxs-lookup"><span data-stu-id="39d4f-102">Walkthrough: Creating Your First Touch Application</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="39d4f-103">使应用程序能够响应触摸。</span><span class="sxs-lookup"><span data-stu-id="39d4f-103"> enables applications to respond to touch.</span></span> <span data-ttu-id="39d4f-104">例如，可以使用一个与应用程序交互或敏式设备，如本演练中创建该应用程序，用户可以移动，触摸屏上的多个手指重设大小，或使用触摸来旋转的单个对象。</span><span class="sxs-lookup"><span data-stu-id="39d4f-104">For example, you can interact with an application by using one or more fingers on a touch-sensitive device, such as a touchscreen This walkthrough creates an application that enables the user to move, resize, or rotate a single object by using touch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="39d4f-105">系统必备</span><span class="sxs-lookup"><span data-stu-id="39d4f-105">Prerequisites</span></span>  
 <span data-ttu-id="39d4f-106">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="39d4f-106">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="39d4f-107">Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="39d4f-107">Visual Studio.</span></span>  
  
-   <span data-ttu-id="39d4f-108">接受触控输入，如触摸屏，支持 Windows 触摸设备。</span><span class="sxs-lookup"><span data-stu-id="39d4f-108">A device that accepts touch input, such as a touchscreen, that supports Windows Touch.</span></span>  
  
 <span data-ttu-id="39d4f-109">此外，应该基本了解如何创建中的应用程序的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，尤其是如何订阅和处理事件。</span><span class="sxs-lookup"><span data-stu-id="39d4f-109">Additionally, you should have a basic understanding of how to create an application in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especially how to subscribe to and handle an event.</span></span> <span data-ttu-id="39d4f-110">有关详细信息，请参阅[演练：我的第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="39d4f-110">For more information, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="creating-the-application"></a><span data-ttu-id="39d4f-111">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="39d4f-111">Creating the Application</span></span>  
  
#### <a name="to-create-the-application"></a><span data-ttu-id="39d4f-112">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="39d4f-112">To create the application</span></span>  
  
1.  <span data-ttu-id="39d4f-113">在 Visual Basic 或 Visual C# 中创建名为 `BasicManipulation` 的新 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="39d4f-113">Create a new WPF Application project in Visual Basic or Visual C# named `BasicManipulation`.</span></span> <span data-ttu-id="39d4f-114">有关详细信息，请参阅[如何：创建新的 WPF 应用程序项目](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)。</span><span class="sxs-lookup"><span data-stu-id="39d4f-114">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="39d4f-115">MainWindow.xaml 的内容替换为以下 XAML。</span><span class="sxs-lookup"><span data-stu-id="39d4f-115">Replace the contents of MainWindow.xaml with the following XAML.</span></span>  
  
     <span data-ttu-id="39d4f-116">此标记将创建一个简单的应用程序包含一个红色<xref:System.Windows.Shapes.Rectangle>上<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="39d4f-116">This markup creates a simple application that contains a red <xref:System.Windows.Shapes.Rectangle> on a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="39d4f-117"><xref:System.Windows.UIElement.IsManipulationEnabled%2A>属性的<xref:System.Windows.Shapes.Rectangle>设置为 true，以便它将接收操作事件。</span><span class="sxs-lookup"><span data-stu-id="39d4f-117">The <xref:System.Windows.UIElement.IsManipulationEnabled%2A> property of the <xref:System.Windows.Shapes.Rectangle> is set to true so that it will receive manipulation events.</span></span> <span data-ttu-id="39d4f-118">应用程序订阅<xref:System.Windows.UIElement.ManipulationStarting>， <xref:System.Windows.UIElement.ManipulationDelta>，和<xref:System.Windows.UIElement.ManipulationInertiaStarting>事件。</span><span class="sxs-lookup"><span data-stu-id="39d4f-118">The application subscribes to the <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, and <xref:System.Windows.UIElement.ManipulationInertiaStarting> events.</span></span> <span data-ttu-id="39d4f-119">这些事件包含的逻辑移动<xref:System.Windows.Shapes.Rectangle>用户处理。</span><span class="sxs-lookup"><span data-stu-id="39d4f-119">These events contain the logic to move the <xref:System.Windows.Shapes.Rectangle> when the user manipulates it.</span></span>  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  <span data-ttu-id="39d4f-120">如果使用的 Visual Basic 中，在 MainWindow.xaml 的第一行中，替换`x:Class="BasicManipulation.MainWindow"`与`x:Class="MainWindow"`。</span><span class="sxs-lookup"><span data-stu-id="39d4f-120">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="BasicManipulation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
4.  <span data-ttu-id="39d4f-121">在中`MainWindow`类中，添加以下<xref:System.Windows.UIElement.ManipulationStarting>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="39d4f-121">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationStarting> event handler.</span></span>  
  
     <span data-ttu-id="39d4f-122"><xref:System.Windows.UIElement.ManipulationStarting>事件发生时[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]检测到触控输入开始操作对象。</span><span class="sxs-lookup"><span data-stu-id="39d4f-122">The <xref:System.Windows.UIElement.ManipulationStarting> event occurs when [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] detects that touch input begins to manipulate an object.</span></span> <span data-ttu-id="39d4f-123">该代码指定操作位置应为相对于<xref:System.Windows.Window>通过设置<xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="39d4f-123">The code specifies that the position of the manipulation should be relative to the <xref:System.Windows.Window> by setting the <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> property.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]

5.  <span data-ttu-id="39d4f-124">在中`MainWindow`类中，添加以下<xref:System.Windows.Input.ManipulationDelta>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="39d4f-124">In the `MainWindow` class, add the following <xref:System.Windows.Input.ManipulationDelta> event handler.</span></span>

     <span data-ttu-id="39d4f-125"><xref:System.Windows.Input.ManipulationDelta>事件发生时触摸输入更改位置，并可在操作过程中出现多次。</span><span class="sxs-lookup"><span data-stu-id="39d4f-125">The <xref:System.Windows.Input.ManipulationDelta> event occurs when the touch input changes position and can occur multiple times during a manipulation.</span></span> <span data-ttu-id="39d4f-126">引发一个手指后，也会发生该事件。</span><span class="sxs-lookup"><span data-stu-id="39d4f-126">The event can also occur after a finger is raised.</span></span> <span data-ttu-id="39d4f-127">例如，如果用户在屏幕上拖动手指<xref:System.Windows.Input.ManipulationDelta>事件发生多次在手指移动时。</span><span class="sxs-lookup"><span data-stu-id="39d4f-127">For example, if the user drags a finger across a screen, the <xref:System.Windows.Input.ManipulationDelta> event occurs multiple times as the finger moves.</span></span> <span data-ttu-id="39d4f-128">当用户将手指从屏幕上，<xref:System.Windows.Input.ManipulationDelta>事件会不断发生，以模拟惯性。</span><span class="sxs-lookup"><span data-stu-id="39d4f-128">When the user raises a finger from the screen, the <xref:System.Windows.Input.ManipulationDelta> event keeps occurring to simulate inertia.</span></span>

     <span data-ttu-id="39d4f-129">此代码适用<xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A>到<xref:System.Windows.UIElement.RenderTransform%2A>的<xref:System.Windows.Shapes.Rectangle>可将其移动用户在将移动触控输入。</span><span class="sxs-lookup"><span data-stu-id="39d4f-129">The code applies the <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> to the <xref:System.Windows.UIElement.RenderTransform%2A> of the <xref:System.Windows.Shapes.Rectangle> to move it as the user moves the touch input.</span></span> <span data-ttu-id="39d4f-130">它还会检查是否<xref:System.Windows.Shapes.Rectangle>的界限外<xref:System.Windows.Window>在惯性期间在事件发生时。</span><span class="sxs-lookup"><span data-stu-id="39d4f-130">It also checks whether the <xref:System.Windows.Shapes.Rectangle> is outside the bounds of the <xref:System.Windows.Window> when the event occurs during inertia.</span></span> <span data-ttu-id="39d4f-131">因此，在应用程序调用<xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType>方法来结束操作。</span><span class="sxs-lookup"><span data-stu-id="39d4f-131">If so, the application calls the <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> method to end the manipulation.</span></span>

     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]

6.  <span data-ttu-id="39d4f-132">在中`MainWindow`类中，添加以下<xref:System.Windows.UIElement.ManipulationInertiaStarting>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="39d4f-132">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationInertiaStarting> event handler.</span></span>

     <span data-ttu-id="39d4f-133"><xref:System.Windows.UIElement.ManipulationInertiaStarting>事件发生时用户将所有手指从屏幕。</span><span class="sxs-lookup"><span data-stu-id="39d4f-133">The <xref:System.Windows.UIElement.ManipulationInertiaStarting> event occurs when the user raises all fingers from the screen.</span></span> <span data-ttu-id="39d4f-134">该代码设置初始速度和为移动、 扩展和旋转矩形的减速度。</span><span class="sxs-lookup"><span data-stu-id="39d4f-134">The code sets the initial velocity and deceleration for the movement, expansion, and rotation of the rectangle.</span></span>

     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]

7.  <span data-ttu-id="39d4f-135">生成并运行该项目。</span><span class="sxs-lookup"><span data-stu-id="39d4f-135">Build and run the project.</span></span>

     <span data-ttu-id="39d4f-136">应会看到窗口中显示一个红色方块。</span><span class="sxs-lookup"><span data-stu-id="39d4f-136">You should see a red square appear in the window.</span></span>

## <a name="testing-the-application"></a><span data-ttu-id="39d4f-137">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="39d4f-137">Testing the Application</span></span>
 <span data-ttu-id="39d4f-138">若要测试应用程序，请尝试以下操作。</span><span class="sxs-lookup"><span data-stu-id="39d4f-138">To test the application, try the following manipulations.</span></span> <span data-ttu-id="39d4f-139">请注意，您可以多个以下项之一在同一时间。</span><span class="sxs-lookup"><span data-stu-id="39d4f-139">Note that you can do more than one of the following at the same time.</span></span>

-   <span data-ttu-id="39d4f-140">若要将移动<xref:System.Windows.Shapes.Rectangle>，将手指放<xref:System.Windows.Shapes.Rectangle>并在屏幕上移动手指。</span><span class="sxs-lookup"><span data-stu-id="39d4f-140">To move the <xref:System.Windows.Shapes.Rectangle>, put a finger on the <xref:System.Windows.Shapes.Rectangle> and move the finger across the screen.</span></span>

-   <span data-ttu-id="39d4f-141">若要调整大小<xref:System.Windows.Shapes.Rectangle>，将两根手指放<xref:System.Windows.Shapes.Rectangle>，并将手指，或将其彼此相差。</span><span class="sxs-lookup"><span data-stu-id="39d4f-141">To resize the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and move the fingers closer together or farther apart from each other.</span></span>

-   <span data-ttu-id="39d4f-142">若要旋转<xref:System.Windows.Shapes.Rectangle>，将两根手指放<xref:System.Windows.Shapes.Rectangle>和旋转相对于每个其他手指。</span><span class="sxs-lookup"><span data-stu-id="39d4f-142">To rotate the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and rotate the fingers around each other.</span></span>

 <span data-ttu-id="39d4f-143">若要导致延时，快速提升您将手指从屏幕执行上一操作。</span><span class="sxs-lookup"><span data-stu-id="39d4f-143">To cause inertia, quickly raise your fingers from the screen as you perform the previous manipulations.</span></span> <span data-ttu-id="39d4f-144"><xref:System.Windows.Shapes.Rectangle>将继续移动、 调整大小，或为几秒钟才会停止旋转。</span><span class="sxs-lookup"><span data-stu-id="39d4f-144">The <xref:System.Windows.Shapes.Rectangle> will continue to move, resize, or rotate for a few seconds before it stops.</span></span>

## <a name="see-also"></a><span data-ttu-id="39d4f-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="39d4f-145">See Also</span></span>

- <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>