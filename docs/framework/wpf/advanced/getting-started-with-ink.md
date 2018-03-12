---
title: "墨迹入门"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74227ebe815e971087569ff39ac0a3479c1b0d14
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="getting-started-with-ink"></a>墨迹入门
将数字墨迹合并到你的应用程序是比以往更容易。 墨迹已从正在实现完全集成到编程的 COM 和 Windows 窗体方法的必然结果发展[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 不需要安装单独的 Sdk 或运行时库。  
  
## <a name="prerequisites"></a>系统必备  
 若要使用下面的示例，必须首先安装 Microsoft Visual Studio 2005 和[!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]。 还必须了解如何编写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的应用程序。 有关详细信息，有关如何开始使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，请参阅[演练： 我第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)。  
  
## <a name="quick-start"></a>快速入门  
 本部分可帮助您编写一个简单[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]收集墨迹的应用程序。  
  
 如果你尚未这样做，安装 Microsoft Visual Studio 2005 和[!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序通常必须进行编译之后，你可以查看它们，即使它们包含完全的[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。 但是，[!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]包括设计的应用程序，XamlPad，加快的实现过程[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-基于 UI。 该应用程序可用于查看和修补本文档中的第一个几个示例。 创建的过程编译的应用程序从[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]在本文档的后面介绍。  
  
 若要启动 XAMLPad，请单击**启动**菜单上，指向**所有程序**，指向**Microsoft Windows SDK**，指向**工具**，然后单击**XAMLPad**。 在呈现窗格中，XAMLPad 呈现代码窗格中编写的 XAML 代码。 你可以编辑 XAML 代码中，并且所做的更改立即出现在呈现窗格中。  
  
#### <a name="got-ink"></a>如何获取墨迹？  
 若要启动你的第一个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]支持墨迹应用程序：  
  
1.  Open Microsoft Visual Studio 2005  
  
2.  创建一个新**Windows 应用程序 (WPF)**  
  
3.  类型`<InkCanvas/>`之间`<Grid>`标记  
  
4.  按**F5**以启动调试器中的应用程序  
  
5.  使用触笔或鼠标，编写**你好 world**窗口中  
  
 已写入墨迹等效于"你好 world"应用程序仅 12 击键次数 ！  
  
#### <a name="spice-up-your-application"></a>增强你的应用程序  
 让我们利用的一些功能[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。  将打开之间的所有内容\<窗口 > 标记和结束\</Window > 替换为以下标记，以获取墨迹图面上的渐变画笔背景标记。  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a>使用动画  
 为了更加有趣，让我们动态渐变画笔的颜色显示。 添加以下[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]之后，结束`</InkCanvas>`标记但在关闭前`</Page>`标记。  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a>添加一些代码隐藏 XAML  
 尽管 XAML 使得变得非常轻松地设计用户界面，任何实际的应用程序将需要添加代码来处理事件。 下面是放大墨迹响应来自鼠标右键单击一个简单示例：  
  
 设置`MouseRightButtonUp`中的处理程序你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 在 Visual Studio 的解决方案资源管理器中，展开 Windows1.xaml 并打开代码隐藏文件，Window1.xaml.cs 或 Window1.xaml.vb 如果正在使用 Visual Basic。 添加以下事件处理程序代码：  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 现在，运行你的应用程序。 添加一些墨迹然后用鼠标右键单击或执行触笔与按下保持等效。  
  
#### <a name="using-procedural-code-instead-of-xaml"></a>使用过程代码，而不 XAML  
 你可以访问所有[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的过程性代码的功能。 下面是"Hello 墨迹 World"应用程序[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，不使用任何[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]根本。 将下面的代码粘贴到 Visual Studio 中的空控制台应用程序。 添加引用 PresentationCore 和 PresentationFramework，WindowsBase 程序集，并生成应用程序按**F5**:  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 [数字墨迹](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [收集墨迹](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [手写识别](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [存储墨迹](../../../../docs/framework/wpf/advanced/storing-ink.md)
