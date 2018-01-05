---
title: "墨迹入门"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c977e8a4a23f9739541cf28d9e34ad9e8db1daf0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-with-ink"></a><span data-ttu-id="3d6a0-102">墨迹入门</span><span class="sxs-lookup"><span data-stu-id="3d6a0-102">Getting Started with Ink</span></span>
<span data-ttu-id="3d6a0-103">将数字墨迹合并到你的应用程序是比以往更容易。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-103">Incorporating digital ink into your applications is easier than ever.</span></span> <span data-ttu-id="3d6a0-104">墨迹已从正在实现完全集成到编程的 COM 和 Windows 窗体方法的必然结果发展[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-104">Ink has evolved from being a corollary to the COM and Windows Forms method of programming to achieving full integration into the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="3d6a0-105">不需要安装单独的 Sdk 或运行时库。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-105">You do not need to install separate SDKs or runtime libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3d6a0-106">系统必备</span><span class="sxs-lookup"><span data-stu-id="3d6a0-106">Prerequisites</span></span>  
 <span data-ttu-id="3d6a0-107">若要使用下面的示例，必须首先安装 Microsoft Visual Studio 2005 和[!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-107">To use the following examples, you must first install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="3d6a0-108">还必须了解如何编写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-108">You should also understand how to write applications for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="3d6a0-109">有关详细信息，有关如何开始使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，请参阅[演练： 我第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-109">For more information about getting started with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="quick-start"></a><span data-ttu-id="3d6a0-110">快速入门</span><span class="sxs-lookup"><span data-stu-id="3d6a0-110">Quick Start</span></span>  
 <span data-ttu-id="3d6a0-111">本部分可帮助您编写一个简单[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]收集墨迹的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-111">This section helps you write a simple [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that collects ink.</span></span>  
  
 <span data-ttu-id="3d6a0-112">如果你尚未这样做，安装 Microsoft Visual Studio 2005 和[!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-112">If you haven't already done so, install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="3d6a0-113">应用程序通常必须进行编译之后，你可以查看它们，即使它们包含完全的[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-113"> applications usually must be compiled before you can view them, even if they consist entirely of [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="3d6a0-114">但是，[!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]包括设计的应用程序，XamlPad，加快的实现过程[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-基于 UI。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-114">However, the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] includes an application, XamlPad, designed to speed up the process of implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-based UI.</span></span> <span data-ttu-id="3d6a0-115">该应用程序可用于查看和修补本文档中的第一个几个示例。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-115">You can use that application to view and tinker with the first few samples in this document.</span></span> <span data-ttu-id="3d6a0-116">创建的过程编译的应用程序从[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]在本文档的后面介绍。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-116">The process of creating compiled applications from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is covered later in this document.</span></span>  
  
 <span data-ttu-id="3d6a0-117">若要启动 XAMLPad，请单击**启动**菜单上，指向**所有程序**，指向**Microsoft Winndows SDK**，指向**工具**，然后单击**XAMLPad**。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-117">To launch XAMLPad, click the **Start** menu, point to **All Programs**, point to **Microsoft Winndows SDK**, point to **Tools**, and click **XAMLPad**.</span></span> <span data-ttu-id="3d6a0-118">在呈现窗格中，XAMLPad 呈现代码窗格中编写的 XAML 代码。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-118">In the rendering pane, XAMLPad renders the XAML code written in the code pane.</span></span> <span data-ttu-id="3d6a0-119">你可以编辑 XAML 代码中，并且所做的更改立即出现在呈现窗格中。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-119">You can edit the XAML code, and the changes immediately appear in the rendering pane.</span></span>  
  
#### <a name="got-ink"></a><span data-ttu-id="3d6a0-120">如何获取墨迹？</span><span class="sxs-lookup"><span data-stu-id="3d6a0-120">Got Ink?</span></span>  
 <span data-ttu-id="3d6a0-121">若要启动你的第一个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]支持墨迹应用程序：</span><span class="sxs-lookup"><span data-stu-id="3d6a0-121">To start your first [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that supports ink:</span></span>  
  
1.  <span data-ttu-id="3d6a0-122">打开 Microsoft Visual Studio 2005</span><span class="sxs-lookup"><span data-stu-id="3d6a0-122">Open Microsoft Visual Studio 2005</span></span>  
  
2.  <span data-ttu-id="3d6a0-123">创建一个新**Windows 应用程序 (WPF)**</span><span class="sxs-lookup"><span data-stu-id="3d6a0-123">Create a new **Windows Application (WPF)**</span></span>  
  
3.  <span data-ttu-id="3d6a0-124">类型`<InkCanvas/>`之间`<Grid>`标记</span><span class="sxs-lookup"><span data-stu-id="3d6a0-124">Type `<InkCanvas/>` between the `<Grid>` tags</span></span>  
  
4.  <span data-ttu-id="3d6a0-125">按**F5**以启动调试器中的应用程序</span><span class="sxs-lookup"><span data-stu-id="3d6a0-125">Press **F5** to launch your application in the debugger</span></span>  
  
5.  <span data-ttu-id="3d6a0-126">使用触笔或鼠标，编写**你好 world**窗口中</span><span class="sxs-lookup"><span data-stu-id="3d6a0-126">Using a stylus or mouse, write **hello world** in the window</span></span>  
  
 <span data-ttu-id="3d6a0-127">已写入墨迹等效于"你好 world"应用程序仅 12 击键次数 ！</span><span class="sxs-lookup"><span data-stu-id="3d6a0-127">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>  
  
#### <a name="spice-up-your-application"></a><span data-ttu-id="3d6a0-128">增强你的应用程序</span><span class="sxs-lookup"><span data-stu-id="3d6a0-128">Spice Up Your Application</span></span>  
 <span data-ttu-id="3d6a0-129">让我们利用的一些功能[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-129">Let’s take advantage of some features of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  <span data-ttu-id="3d6a0-130">将打开之间的所有内容\<窗口 > 标记和结束\</Window > 替换为以下标记，以获取墨迹图面上的渐变画笔背景标记。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-130">Replace everything between the opening \<Window> and closing \</Window> tags with the following markup to get a gradient brush background on your inking surface.</span></span>  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a><span data-ttu-id="3d6a0-131">使用动画</span><span class="sxs-lookup"><span data-stu-id="3d6a0-131">Using Animation</span></span>  
 <span data-ttu-id="3d6a0-132">为了更加有趣，让我们动态渐变画笔的颜色显示。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-132">For fun, let's animate the colors of the gradient brush.</span></span> <span data-ttu-id="3d6a0-133">添加以下[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]之后，结束`</InkCanvas>`标记但在关闭前`</Page>`标记。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-133">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] after the closing `</InkCanvas>` tag but before the closing `</Page>` tag.</span></span>  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a><span data-ttu-id="3d6a0-134">添加一些代码隐藏 XAML</span><span class="sxs-lookup"><span data-stu-id="3d6a0-134">Adding Some Code Behind the XAML</span></span>  
 <span data-ttu-id="3d6a0-135">尽管 XAML 使得变得非常轻松地设计用户界面，任何实际的应用程序将需要添加代码来处理事件。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-135">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="3d6a0-136">下面是放大墨迹响应来自鼠标右键单击一个简单示例：</span><span class="sxs-lookup"><span data-stu-id="3d6a0-136">Here is a simple example that zooms in on the ink in response to a right-click from a mouse:</span></span>  
  
 <span data-ttu-id="3d6a0-137">设置`MouseRightButtonUp`中的处理程序你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3d6a0-137">Set the `MouseRightButtonUp` handler in your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span></span>  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 <span data-ttu-id="3d6a0-138">在 Visual Studio 的解决方案资源管理器中，展开 Windows1.xaml 并打开代码隐藏文件，Window1.xaml.cs 或 Window1.xaml.vb 如果正在使用 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-138">In Visual Studio’s Solution Explorer, expand Windows1.xaml and open the code-behind file, Window1.xaml.cs or Window1.xaml.vb if you are using Visual Basic.</span></span> <span data-ttu-id="3d6a0-139">添加以下事件处理程序代码：</span><span class="sxs-lookup"><span data-stu-id="3d6a0-139">Add the following event handler code:</span></span>  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 <span data-ttu-id="3d6a0-140">现在，运行你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-140">Now, run your application.</span></span> <span data-ttu-id="3d6a0-141">添加一些墨迹然后用鼠标右键单击或执行触笔与按下保持等效。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-141">Add some ink and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>  
  
#### <a name="using-procedural-code-instead-of-xaml"></a><span data-ttu-id="3d6a0-142">使用过程代码，而不 XAML</span><span class="sxs-lookup"><span data-stu-id="3d6a0-142">Using Procedural Code Instead of XAML</span></span>  
 <span data-ttu-id="3d6a0-143">你可以访问所有[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的过程性代码的功能。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-143">You can access all [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] features from procedural code.</span></span> <span data-ttu-id="3d6a0-144">下面是"Hello 墨迹 World"应用程序[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，不使用任何[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]根本。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-144">Here is a "Hello Ink World" application for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] that doesn’t use any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] at all.</span></span> <span data-ttu-id="3d6a0-145">将下面的代码粘贴到 Visual Studio 中的空控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d6a0-145">Paste the code below into an empty Console Application in Visual Studio.</span></span> <span data-ttu-id="3d6a0-146">添加引用 PresentationCore 和 PresentationFramework，WindowsBase 程序集，并生成应用程序按**F5**:</span><span class="sxs-lookup"><span data-stu-id="3d6a0-146">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies, and build the application by pressing **F5**:</span></span>  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3d6a0-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d6a0-147">See Also</span></span>  
 [<span data-ttu-id="3d6a0-148">数字墨迹</span><span class="sxs-lookup"><span data-stu-id="3d6a0-148">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [<span data-ttu-id="3d6a0-149">收集墨迹</span><span class="sxs-lookup"><span data-stu-id="3d6a0-149">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [<span data-ttu-id="3d6a0-150">手写识别</span><span class="sxs-lookup"><span data-stu-id="3d6a0-150">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [<span data-ttu-id="3d6a0-151">存储墨迹</span><span class="sxs-lookup"><span data-stu-id="3d6a0-151">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)
