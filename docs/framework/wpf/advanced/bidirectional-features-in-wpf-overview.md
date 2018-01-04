---
title: "WPF 中的双向功能概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b50d98d5f02a59a013d7577f0e312e6ffde35690
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="bidirectional-features-in-wpf-overview"></a>WPF 中的双向功能概述
与其他任何开发平台，不同[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]具有支持的双向内容快速开发的许多功能，例如，混合的左到右和向右键都处于同一文档的数据。 同时，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]创建的用户的需要双向功能，如阿拉伯语和希伯来语用户了绝佳的体验。  
  
 以下各节结合一些示例阐释了如何获得双向内容的最佳显示效果，并对许多双向功能进行了说明。 使用的大多数示例[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]，不过你可以轻松地将应用到的概念[!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]或[!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)]代码。  
  

  
<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 定义中的内容流方向的基本属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序是<xref:System.Windows.FrameworkElement.FlowDirection%2A>。 此属性可以设置为两个枚举值之一，<xref:System.Windows.FlowDirection.LeftToRight>或<xref:System.Windows.FlowDirection.RightToLeft>。 属性可供所有[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]从继承元素<xref:System.Windows.FrameworkElement>。  
  
 下面的示例设置的流动方向<xref:System.Windows.Controls.TextBox>元素。  
  
 **从左向右的流方向**  
  
 [!code-xaml[LTRRTL#LTR](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **从右向左的流方向**  
  
 [!code-xaml[LTRRTL#RTL](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 下图显示了前面代码的呈现方式。  
  
 **阐释 FlowDirection 的图形**  
  
 ![TextBlock 对齐](../../../../docs/framework/wpf/advanced/media/lefttorightrighttoleft.PNG "LefttoRightRighttoLeft")  
  
 中的某个元素[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]树将继承<xref:System.Windows.FrameworkElement.FlowDirection%2A>从其容器。 在下面的示例中，<xref:System.Windows.Controls.TextBlock>位于<xref:System.Windows.Controls.Grid>，后者位于<xref:System.Windows.Window>。 设置<xref:System.Windows.FrameworkElement.FlowDirection%2A>为<xref:System.Windows.Window>意味着将为其设置<xref:System.Windows.Controls.Grid>和<xref:System.Windows.Controls.TextBlock>以及。  
  
 下面的示例演示了如何设置<xref:System.Windows.FrameworkElement.FlowDirection%2A>。  
  
 [!code-xaml[FlowDirection#FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 顶级<xref:System.Windows.Window>具有<xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>，因此它所包含的所有元素也都继承同一<xref:System.Windows.FrameworkElement.FlowDirection%2A>。 为了使元素能够重写指定<xref:System.Windows.FrameworkElement.FlowDirection%2A>它必须添加显式方向更改，例如，第二个<xref:System.Windows.Controls.TextBlock>在前面的示例更改为<xref:System.Windows.FlowDirection.LeftToRight>。 如果没有<xref:System.Windows.FrameworkElement.FlowDirection%2A>定义，则默认值<xref:System.Windows.FlowDirection.LeftToRight>适用。  
  
 下图显示了上一个示例的输出。  
  
 **阐释显式分配的 FlowDirection 的图形**  
  
 ![流方向图](../../../../docs/framework/wpf/advanced/media/flowdir.PNG "FlowDir")  
  
<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 许多开发平台，如[!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)]，[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]和 Java 为双向内容开发提供特殊支持。 如的标记语言[!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)]提供必要的标记，例如在任何所需的方向中, 显示文本的内容的编写器[!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)]4.0 标记、"dir"接受"rtl"或"ltr"作为值。 此标记是类似于<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性，但<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性的工作布局文本内容更高级的方式，可以用于文本以外的内容。  
  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]、<xref:System.Windows.Documents.FlowDocument>是一种多功能[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]可以托管的文本、 表、 图像和其他元素组合的元素。 以下各节中的示例均使用此元素。  
  
 将文本添加到<xref:System.Windows.Documents.FlowDocument>可以按多种方法。 若要这样做，一种简单的方法是通过<xref:System.Windows.Documents.Paragraph>这是一个块级别元素，用于组内容，如文本。 将文本添加到内联级别的元素的示例使用<xref:System.Windows.Documents.Span>和<xref:System.Windows.Documents.Run>。 <xref:System.Windows.Documents.Span>是用于对其他内联元素，进行分组的内联级别流内容元素时<xref:System.Windows.Documents.Run>是内联级别流内容元素旨在包含一连串无格式文本。 A<xref:System.Windows.Documents.Span>可以包含多个<xref:System.Windows.Documents.Run>元素。  
  
 第一个文档示例包含具有大量的网络共享的名称; 的文档例如`\\server1\folder\file.ext`。 无论此网络链接是包含在阿拉伯语文档还是英语文档中，建议始终以相同的方式显示它。 下图显示了该链接以阿拉伯数字表示<xref:System.Windows.FlowDirection.RightToLeft>文档。  
  
 **阐释如何使用 Span 元素的图形**  
  
 ![从右向左显示的文档](../../../../docs/framework/wpf/advanced/media/flowdocument.PNG "FlowDocument")  
  
 由于文本是<xref:System.Windows.FlowDirection.RightToLeft>，因此所有特殊字符，如"\\"，将按从右到左的顺序文本分隔。 那样会导致不正确的顺序显示的链接，因此若要解决此问题，文本必须嵌入保留单独<xref:System.Windows.Documents.Run>流动<xref:System.Windows.FlowDirection.LeftToRight>。 而不是让单独<xref:System.Windows.Documents.Run>对于每种语言，更好的方法要解决此问题是将较少使用英文文本嵌入到较大的阿拉伯语<xref:System.Windows.Documents.Span>。  
  
 下图阐释了这一点。  
  
 **阐释在 Span 元素中使用嵌入的 Run 元素的图形**  
  
 ![XamlPad 屏幕截图](../../../../docs/framework/wpf/advanced/media/runspan.PNG "RunSpan")  
  
 下面的示例演示如何使用<xref:System.Windows.Documents.Run>和<xref:System.Windows.Documents.Span>在文档中的元素。  
  
 [!code-xaml[RunSpan#RunSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Span 元素  
 <xref:System.Windows.Documents.Span>元素的工作方式为具有不同流方向的文本之间的边界分隔符。  即使<xref:System.Windows.Documents.Span>流方向相同的元素将被视为具有不同的双向作用域，这意味着<xref:System.Windows.Documents.Span>在容器的元素顺序<xref:System.Windows.FlowDirection>中的内容<xref:System.Windows.Documents.Span>元素遵循<xref:System.Windows.FlowDirection>的<xref:System.Windows.Documents.Span>。  
  
 下图显示了多个流方向<xref:System.Windows.Controls.TextBlock>元素。  
  
 **阐释多个 TextBlock 中的 FlowDirection 的图形**  
  
 ![具有不同流方向的文本块](../../../../docs/framework/wpf/advanced/media/span.PNG "Span")  
  
 下面的示例演示如何使用<xref:System.Windows.Documents.Span>和<xref:System.Windows.Documents.Run>元素以生成在上一图中显示的结果。  
  
 [!code-xaml[Span#Span](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 在<xref:System.Windows.Controls.TextBlock>在示例中，元素<xref:System.Windows.Documents.Span>元素的布局根据<xref:System.Windows.FlowDirection>其父项，但在每个文本<xref:System.Windows.Documents.Span>元素根据其自己的流<xref:System.Windows.FlowDirection>。 这适用于拉丁语和阿拉伯语，也适用于任何其他语言。  
  
### <a name="adding-xmllang"></a>添加 xml:lang  
 下图显示了另一个示例使用数字和算术表达式，如`"200.0+21.4=221.4"`。 请注意，只有<xref:System.Windows.FlowDirection>设置。  
  
 **仅通过 FlowDirection 显示数字的图形**  
  
 ![从右向左流动的数字](../../../../docs/framework/wpf/advanced/media/langattribute.PNG "LangAttribute")  
  
 此应用程序的用户将失望由输出中，即使<xref:System.Windows.FlowDirection>正确无误数字都不形状也不同于阿拉伯数字应调整。  
  
 XAML 元素可以包括[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]属性 (`xml:lang`)，它定义每个元素的语言。 此外支持 XAML[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]语言原则凭此`xml:lang`应用于在树中的父元素的值由子元素。 在前面的示例中，因为没有为定义一种语言<xref:System.Windows.Documents.Run>元素或其任何顶级级的元素，默认值`xml:lang`所使用的即`en-US`xaml。 内部的数字形状算法[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]选择数字中的相应语言 – 在此情况下为英语。 若要使阿拉伯语数字呈现正确`xml:lang`需要设置。  
  
 下图显示了示例具有`xml:lang`添加。  
  
 **阐释如何使用 xml:lang 属性的图形**  
  
 ![从右向左流动的阿拉伯语数字](../../../../docs/framework/wpf/advanced/media/langattribute2.PNG "LangAttribute2")  
  
 下面的示例添加`xml:lang`到应用程序。  
  
 [!code-xaml[LangAttribute#LangAttribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 请注意，许多语言具有不同`xml:lang`具体取决于目标区域，例如，值`"ar-SA"`和`"ar-EG"`表示两种变体阿拉伯语。 前面的示例说明了你需要同时定义`xml:lang`和<xref:System.Windows.FlowDirection>值。  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>非文本元素的 FlowDirection  
 <xref:System.Windows.FlowDirection>定义不仅文本流动方式中的文本元素，但还的几乎所有其他流向[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]元素。 下图显示<xref:System.Windows.Controls.ToolBar>使用水平<xref:System.Windows.Media.LinearGradientBrush>绘制其背景。  
  
 **演示从左向右渐变的工具栏的图形**  
  
 ![渐变屏幕截图](../../../../docs/framework/wpf/advanced/media/gradient.PNG "Gradient")  
  
 设置后<xref:System.Windows.FlowDirection>到<xref:System.Windows.FlowDirection.RightToLeft>，不仅<xref:System.Windows.Controls.ToolBar>按钮排列从右到左，但即使<xref:System.Windows.Media.LinearGradientBrush>将沿其偏移量，从右到左流动。  
  
 下图显示了重新调整<xref:System.Windows.Media.LinearGradientBrush>。  
  
 **演示工具栏从右到左渐变的图形**  
  
 ![从右到左流动的渐变](../../../../docs/framework/wpf/advanced/media/gradient2-wpf.PNG "Gradient2_WPF")  
  
 下面的示例绘制<xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>。 (若要绘制它从左到右，删除<xref:System.Windows.FlowDirection>属性<xref:System.Windows.Controls.ToolBar>。  
  
 [!code-xaml[Gradient#Gradient](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>FlowDirection 异常  
 有少数情况下其中<xref:System.Windows.FlowDirection>与预期不符。 本部分介绍其中两种异常。  
  
 **Image**  
  
 <xref:System.Windows.Controls.Image>表示显示图像的控件。 在[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]可与<xref:System.Windows.Controls.Image.Source%2A>定义的属性[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]的<xref:System.Windows.Controls.Image>以显示。  
  
 与其他不同[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]元素，<xref:System.Windows.Controls.Image>不会继承<xref:System.Windows.FlowDirection>从容器。 但是，如果<xref:System.Windows.FlowDirection>显式设置为<xref:System.Windows.FlowDirection.RightToLeft>、<xref:System.Windows.Controls.Image>水平翻转的方式显示。 这可作为一种便捷功能提供给双向内容的开发人员，因为在某些情况下，水平翻转图像会达到所需的效果。  
  
 下图显示了一个翻转<xref:System.Windows.Controls.Image>。  
  
 **阐释翻转后的图像的图形**  
  
 ![XamlPad 屏幕截图](../../../../docs/framework/wpf/advanced/media/image.PNG "Image")  
  
 下面的示例演示<xref:System.Windows.Controls.Image>无法继承<xref:System.Windows.FlowDirection>从<xref:System.Windows.Controls.StackPanel>包含它。 **请注意**必须具有名为的文件**ms_logo.jpg**要运行此示例的 C:\ 驱动器上。  
  
 [!code-xaml[Image#Image](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **请注意**包含在下载文件是**ms_logo.jpg**文件。 该代码假定 .jpg 文件不在项目中，而是位于 C:\ 驱动器中的某个位置。 必须将 .jpg 从项目文件复制到 C:\ 驱动器或更改代码才能在项目内查找该文件。 若要执行此更改`Source="file://c:/ms_logo.jpg"`到`Source="ms_logo.jpg"`。  
  
 **Path**  
  
 除了<xref:System.Windows.Controls.Image>，另一个有趣的元素是<xref:System.Windows.Shapes.Path>。 Path 是可用于绘制一系列连接的直线和曲线的对象。 它的行为方式类似于<xref:System.Windows.Controls.Image>有关其<xref:System.Windows.FlowDirection>; 例如其<xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.FlowDirection>是水平镜子，反映其<xref:System.Windows.FlowDirection.LeftToRight>一个。 但是，与不同<xref:System.Windows.Controls.Image>，<xref:System.Windows.Shapes.Path>继承其<xref:System.Windows.FlowDirection>从容器和一个不需要显式指定。  
  
 下面的示例使用 3 条线绘制简单的箭头。 第一个箭头继承<xref:System.Windows.FlowDirection.RightToLeft>流方向从<xref:System.Windows.Controls.StackPanel>，以便其起点和终点测量右侧的根。 第二个箭头具有显式<xref:System.Windows.FlowDirection.RightToLeft><xref:System.Windows.FlowDirection>还启动右侧。 但第三个箭头的起始根位于左侧。 有关详细信息，请参阅绘制<xref:System.Windows.Media.LineGeometry>和<xref:System.Windows.Media.GeometryGroup>。  
  
 [!code-xaml[Paths#Paths](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 下图显示了上一个示例的输出。  
  
 **阐释使用 Path 元素绘制的箭头的图形**  
  
 ![路径](../../../../docs/framework/wpf/advanced/media/paths.PNG "Paths")  
  
 <xref:System.Windows.Controls.Image>和<xref:System.Windows.Shapes.Path>两个示例说明了如何[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]使用<xref:System.Windows.FlowDirection>。 旁边布局[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]按特定方向的容器内的元素<xref:System.Windows.FlowDirection>可以用于元素如<xref:System.Windows.Controls.InkPresenter>其呈现图面上的墨迹<xref:System.Windows.Media.LinearGradientBrush>， <xref:System.Windows.Media.RadialGradientBrush>。 在你的内容，以模拟从左到右的行为，需要右到左行为时，反之亦然，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]提供该功能。  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>数字替换  
 从历史上看，[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]已支持通过允许同时保持在不同的区域设置，之间统一这些数字的内部存储，例如，数字将存储在不同区域性相同的数字形状的表示形式的数字替换其已知十六进制值，如 0x40、 0x41，但根据所选语言显示。  
  
 这具有允许处理数字值，而无需将它们从一种语言转换为另一个应用程序，例如用户可以打开[!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)]电子表格中本地化阿拉伯语[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]，看到以阿拉伯语，形状的数字，但在中打开它欧洲版本[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]并查看欧洲表示形式相同的数字。 这对其他符号（如逗号分隔符和百分比符号）来说也是必需的，因为在同一文档中它们通常随数字一起出现。  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 沿承了这一传统，并为此功能提供了进一步支持，以允许更多的用户对使用替换的时间和方式进行控制。 虽然此功能适用于任何语言，但它对双向内容尤其有用；由于应用程序可能会在各种区域性下运行，因此针对特定语言来设置数字形状通常是应用程序开发人员所面临的难题。  
  
 控制如何执行数字替换的核心属性的工作原理[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]是<xref:System.Windows.Media.NumberSubstitution.Substitution%2A>依赖项属性。 <xref:System.Windows.Media.NumberSubstitution>类指定文本中的数字的显示方式。 它有三个定义其行为的公共属性。 下面概括了其中的每个属性。  
  
 **CultureSource：**  
  
 此属性指定如何确定数字的区域性。 它采用三个之一<xref:System.Windows.Media.NumberCultureSource>枚举值。  
  
-   重写： 数字区域性是<xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A>属性。  
  
-   Text：数字区域性是文本运行的区域性。 在标记中，这将是`xml:lang`，或其别名`Language`属性 (<xref:System.Windows.FrameworkElement.Language%2A>或<xref:System.Windows.FrameworkContentElement.Language%2A>)。 此外，它是派生自的类的默认值<xref:System.Windows.FrameworkContentElement>。 此类类包括<xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>， <xref:System.Windows.Documents.Table?displayProperty=nameWithType>， <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> ，依此类推。  
  
-   User：数字区域性是当前线程的区域性。 此属性是所有的子类的默认值<xref:System.Windows.FrameworkElement>如<xref:System.Windows.Controls.Page>，<xref:System.Windows.Window>和<xref:System.Windows.Controls.TextBlock>。  
  
 **CultureOverride**：  
  
 <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A>仅当使用属性<xref:System.Windows.Media.NumberSubstitution.CultureSource%2A>属性设置为<xref:System.Windows.Media.NumberCultureSource.Override>，否则忽略。 该属性指定数字区域性。 值为`null`，默认值为解释为 EN-US。  
  
 **Substitution**：  
  
 此属性指定要执行的数字替换类型。 它采用以下之一<xref:System.Windows.Media.NumberSubstitutionMethod>枚举值。  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: 替换方法根据数字区域性确定<xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType>属性。 这是默认设置。  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Context>： 如果数字区域性为阿拉伯语或波斯区域性，它指定位数取决于上下文。  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.European>： 数字始终为欧洲数字呈现。  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>： 有关与指定的区域性的数字区域性使用的国家/地区的数字呈现数字<xref:System.Globalization.CultureInfo.NumberFormat%2A>。  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>： 数字呈现数字区域性使用传统的数字。 对于大多数区域性中，这是与相同<xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>。 但是，<xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>导致对某些阿拉伯语区域性拉丁文数字，而此值将导致对所有阿拉伯语区域性阿拉伯数字。  
  
 这些值对双向内容开发人员意味着什么？ 在大多数情况下，开发人员可能需要仅定义<xref:System.Windows.FlowDirection>以及每个文本的语言[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]元素，例如`Language="ar-SA"`和<xref:System.Windows.Media.NumberSubstitution>逻辑负责显示根据正确号[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 下面的示例演示如何使用阿拉伯语和英语中的数字[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]在 Arabic 的版本中运行的应用程序[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]。  
  
 [!code-xaml[Numbers#Numbers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 下图显示上一示例的输出，如果你正在运行的 Arabic 版本[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]。  
  
 **演示显示的阿拉伯数字和英文数字**  
  
 ![具有数字的 XamlPad 屏幕截图](../../../../docs/framework/wpf/advanced/media/numbers.PNG "Numbers")  
  
 <xref:System.Windows.FlowDirection>已重要在这种情况下设置因为<xref:System.Windows.FlowDirection>到<xref:System.Windows.FlowDirection.LeftToRight>改为将产生欧洲数字。 以下各节介绍如何在整个文档内统一显示数字。 如果未在阿拉伯语版 Windows 上运行此示例，所有数字都将显示为欧洲数字。  
  
 **定义替换规则**  
  
 在实际的应用程序中，可能需要以编程方式设置语言。 例如，你想要设置`xml:lang`要使用的系统的相同属性[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，或可能更改具体取决于应用程序状态的语言。  
  
 如果你想要更改根据应用程序的状态，请提供其他功能的使用[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。  
  
 首先，设置应用程序组件的`NumberSubstitution.CultureSource="Text"`。 使用此设置可以确保设置不是来自[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]的文本元素"用户"作为默认值，如<xref:System.Windows.Controls.TextBlock>。  
  
 例如:  
  
||  
|-|  
|`<TextBlock`<br /><br /> `Name="text1" NumberSubstitution.CultureSource="Text">`<br /><br /> `1234+5679=6913`<br /><br /> `</TextBlock>`|  
  
 在相应[!INCLUDE[TLA2#tla_lhcshrp](../../../../includes/tla2sharptla-lhcshrp-md.md)]代码中，设置`Language`属性例如，若要`"ar-SA"`。  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");`|  
  
 如果你需要设置`Language`属性设置为当前用户的[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]语言使用下面的代码。  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage(`<br /><br /> `System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);`|  
  
 <xref:System.Globalization.CultureInfo.CurrentCulture%2A>表示在运行时使用当前线程的当前区域性。  
  
 你最终[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]示例应类似于下面的示例。  
  
 [!code-xaml[Numbers2#Numbers2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 你最终[!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]应类似于以下示例。  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 下图演示用于任一编程语言的窗口的外观。  
  
 **显示阿拉伯数字的图形**  
  
 ![阿拉伯数字](../../../../docs/framework/wpf/advanced/media/numbers2.PNG "Numbers2")  
  
 **使用 Substitution 属性**  
  
 在工作方式数字替换[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]取决于这两种语言的文本元素并将其<xref:System.Windows.FlowDirection>。 如果<xref:System.Windows.FlowDirection>从左到右，然后会呈现欧洲数字。 但是如果它前面阿拉伯语文本，或具有的语言设置为"ar"和<xref:System.Windows.FlowDirection>是<xref:System.Windows.FlowDirection.RightToLeft>，阿拉伯数字会改为呈现。  
  
 但在某些情况下，建议创建统一的应用程序，例如适用于所有用户的欧洲数字。 或在阿拉伯数字<xref:System.Windows.Documents.Table>具有特定的单元格<xref:System.Windows.Style>。 一个执行操作简单方法是使用<xref:System.Windows.Media.NumberSubstitution.Substitution%2A>属性。  
  
 在下面的示例中，第一个<xref:System.Windows.Controls.TextBlock>没有<xref:System.Windows.Media.NumberSubstitution.Substitution%2A>设置属性，因此该算法按预期方式显示阿拉伯数字。 但是在第二个<xref:System.Windows.Controls.TextBlock>，替换设置为欧洲重写默认替换为阿拉伯数字，并且显示欧洲数字。  
  
 [!code-xaml[Numbers3#Numbers3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
