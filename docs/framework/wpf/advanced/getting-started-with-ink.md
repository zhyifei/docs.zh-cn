---
title: 在 Visual Studio 中的 WPF 应用程序中创建 InkCanvas
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: eaaa8ad5273331941bc6915231460100e8ac24b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646235"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="e9a07-102">在 WPF 中的墨迹入门</span><span class="sxs-lookup"><span data-stu-id="e9a07-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="e9a07-103">Windows Presentation Foundation (WPF) 具有墨迹功能，可以轻松地将数字墨迹合并到您的应用程序功能。</span><span class="sxs-lookup"><span data-stu-id="e9a07-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9a07-104">系统必备</span><span class="sxs-lookup"><span data-stu-id="e9a07-104">Prerequisites</span></span>

<span data-ttu-id="e9a07-105">若要使用以下示例中，首先[安装 Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="e9a07-105">To use the following examples, first [install Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span></span> <span data-ttu-id="e9a07-106">它还有助于了解如何编写基本的 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9a07-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="e9a07-107">WPF 入门的帮助，请参阅[演练：我第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e9a07-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="e9a07-108">快速入门</span><span class="sxs-lookup"><span data-stu-id="e9a07-108">Quick Start</span></span>

<span data-ttu-id="e9a07-109">本部分可帮助您编写的简单的 WPF 应用程序收集墨迹。</span><span class="sxs-lookup"><span data-stu-id="e9a07-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="e9a07-110">如何获取墨迹</span><span class="sxs-lookup"><span data-stu-id="e9a07-110">Got Ink?</span></span>

<span data-ttu-id="e9a07-111">若要创建一个 WPF 应用程序的支持手写内容：</span><span class="sxs-lookup"><span data-stu-id="e9a07-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="e9a07-112">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e9a07-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="e9a07-113">创建一个新**WPF 应用**。</span><span class="sxs-lookup"><span data-stu-id="e9a07-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="e9a07-114">在中**新的项目**对话框中，展开**已安装** > **Visual C#** 或**Visual Basic**  >  **Windows 桌面**类别。</span><span class="sxs-lookup"><span data-stu-id="e9a07-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="e9a07-115">然后，选择**WPF 应用 (.NET Framework)** 应用模板。</span><span class="sxs-lookup"><span data-stu-id="e9a07-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="e9a07-116">输入一个名称，并选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e9a07-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="e9a07-117">Visual Studio 创建项目，并*MainWindow.xaml*设计器中打开。</span><span class="sxs-lookup"><span data-stu-id="e9a07-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="e9a07-118">类型`<InkCanvas/>`之间`<Grid>`标记。</span><span class="sxs-lookup"><span data-stu-id="e9a07-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![使用 InkCanvas 标记的 XAML 设计器](media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="e9a07-120">按**F5**若要在调试器中启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9a07-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="e9a07-121">使用触笔或鼠标，编写**你好世界**在窗口中。</span><span class="sxs-lookup"><span data-stu-id="e9a07-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="e9a07-122">您已编写具有仅 12 击键的"你好 world"应用程序的手写内容等效项 ！</span><span class="sxs-lookup"><span data-stu-id="e9a07-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="e9a07-123">您的应用程序的情趣</span><span class="sxs-lookup"><span data-stu-id="e9a07-123">Spice Up Your App</span></span>

<span data-ttu-id="e9a07-124">让我们来充分利用 WPF 的一些功能。</span><span class="sxs-lookup"><span data-stu-id="e9a07-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="e9a07-125">替换的所有内容的开始和结束之间\<窗口 > 使用以下标记的标记：</span><span class="sxs-lookup"><span data-stu-id="e9a07-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

<span data-ttu-id="e9a07-126">此 XAML 创建渐变画笔背景墨迹书写表面上。</span><span class="sxs-lookup"><span data-stu-id="e9a07-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![墨迹书写在 WPF 应用中的图面上的渐变颜色](media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="e9a07-128">添加一些代码隐藏 XAML</span><span class="sxs-lookup"><span data-stu-id="e9a07-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="e9a07-129">尽管 XAML 可以非常轻松地设计用户界面，任何实际的应用程序将需要添加代码以处理事件。</span><span class="sxs-lookup"><span data-stu-id="e9a07-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="e9a07-130">下面是一个简单示例，放大以响应来自鼠标右键单击的墨迹。</span><span class="sxs-lookup"><span data-stu-id="e9a07-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="e9a07-131">设置`MouseRightButtonUp`在 XAML 中的处理程序：</span><span class="sxs-lookup"><span data-stu-id="e9a07-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="e9a07-132">在中**解决方案资源管理器**，展开 MainWindow.xaml 并打开代码隐藏文件 （MainWindow.xaml.cs 或 MainWindow.xaml.vb）。</span><span class="sxs-lookup"><span data-stu-id="e9a07-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="e9a07-133">添加以下事件处理程序代码：</span><span class="sxs-lookup"><span data-stu-id="e9a07-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="e9a07-134">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9a07-134">Run the application.</span></span> <span data-ttu-id="e9a07-135">添加一些墨迹，然后用鼠标右键单击或执行与触笔按下保持等效。</span><span class="sxs-lookup"><span data-stu-id="e9a07-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="e9a07-136">用鼠标右键单击每个时间会放大显示。</span><span class="sxs-lookup"><span data-stu-id="e9a07-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="e9a07-137">使用程序代码而不是 XAML</span><span class="sxs-lookup"><span data-stu-id="e9a07-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="e9a07-138">可以从程序代码来访问所有 WPF 功能。</span><span class="sxs-lookup"><span data-stu-id="e9a07-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="e9a07-139">请按照下列步骤为根本不使用任何 XAML 的 WPF 创建"Hello 墨迹 World"应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9a07-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="e9a07-140">在 Visual Studio 中创建新的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="e9a07-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="e9a07-141">在中**新的项目**对话框中，展开**已安装** > **Visual C#** 或**Visual Basic**  >  **Windows 桌面**类别。</span><span class="sxs-lookup"><span data-stu-id="e9a07-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="e9a07-142">然后，选择**控制台应用 (.NET Framework)** 应用模板。</span><span class="sxs-lookup"><span data-stu-id="e9a07-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="e9a07-143">输入一个名称，并选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e9a07-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="e9a07-144">将以下代码粘贴到 Program.cs 或 Program.vb 文件：</span><span class="sxs-lookup"><span data-stu-id="e9a07-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="e9a07-145">通过右键单击添加对 PresentationCore、 PresentationFramework、 和 WindowsBase 程序集的引用**引用**中**解决方案资源管理器**，然后选择**添加引用**.</span><span class="sxs-lookup"><span data-stu-id="e9a07-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![引用管理器显示 PresentationCore 和 PresentationFramework](media/getting-started-with-ink/references.png)

1. <span data-ttu-id="e9a07-147">生成应用程序通过按**F5**。</span><span class="sxs-lookup"><span data-stu-id="e9a07-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9a07-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9a07-148">See also</span></span>

- [<span data-ttu-id="e9a07-149">数字墨迹</span><span class="sxs-lookup"><span data-stu-id="e9a07-149">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)
- [<span data-ttu-id="e9a07-150">收集墨迹</span><span class="sxs-lookup"><span data-stu-id="e9a07-150">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)
- [<span data-ttu-id="e9a07-151">手写识别</span><span class="sxs-lookup"><span data-stu-id="e9a07-151">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)
- [<span data-ttu-id="e9a07-152">存储墨迹</span><span class="sxs-lookup"><span data-stu-id="e9a07-152">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)
