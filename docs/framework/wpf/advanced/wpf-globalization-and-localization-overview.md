---
title: WPF 全球化和本地化概述
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6f2bc9021ca376b7b27f74efed6866a907b480ad
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2018
---
# <a name="wpf-globalization-and-localization-overview"></a>WPF 全球化和本地化概述
当你将自己的产品限制为只能通过一种语言使用时，便将潜在的客户群限制为全球 65 亿人口中的一小部分。 如果想让自己的应用程序被全球用户所接受，那么对产品进行经济而有效的本地化将是赢得更多客户的最好、最经济的方法。  
  
 此概述介绍全球化和本地化[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。 全球化是指设计和开发在多个地点执行的应用程序。 例如，全球化支持适用于不同区域性用户的本地化用户界面和区域数据。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了全球化的设计功能，包括自动布局、 附属程序集和本地化的属性和注释。
  
 本地化是针对应用程序所支持的特定区域性将应用程序资源转换为本地化版本的过程。 当您在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，使用中的 Api<xref:System.Windows.Markup.Localizer>命名空间。 这些 Api power [LocBaml 工具示例](http://go.microsoft.com/fwlink/?LinkID=160016)命令行工具。 有关如何生成和使用的信息，请参阅[本地化应用程序](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)。    
  
## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>在 WPF 中进行全球化和本地化的最佳做法  
 你可以充分利用内置的全球化和本地化功能[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]按照的 UI 设计和本部分提供的本地化相关提示。  
  
### <a name="best-practices-for-wpf-ui-design"></a>WPF UI 设计的最佳做法  
 当您设计[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]– 基于[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，请考虑实施这些最佳做法：  
  
-   编写你[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; 避免创建[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]在代码中。 当你创建你[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，通过内置的本地化 Api 将其公开。  
  
-   避免使用绝对位置和固定的大小进行布局内容;请改用相对或自动调整大小。
  
    -   使用<xref:System.Windows.Window.SizeToContent%2A>; 并使宽度和高度设置为`Auto`。  
  
    -   避免使用<xref:System.Windows.Controls.Canvas>进行布局[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]s。  
  
    -   使用<xref:System.Windows.Controls.Grid>及其大小共享功能。  
  
-   在边距中提供额外的空间，因为本地化文本通常需要更多空间。 额外空间为可能会延伸的字符预留了余地。  
  
-   启用<xref:System.Windows.Controls.TextBlock.TextWrapping%2A>上<xref:System.Windows.Controls.TextBlock>以免剪辑。
  
-   设置**xml: lang**属性。 此属性所描述的特定元素及其子元素的区域性。 此属性的值更改中的一些功能的行为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 例如，它可以更改断字、拼写检查、数字替换、复杂脚本成型和字体回退的行为。 请参阅[WPF 的全球化](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)有关设置的详细信息[xml: lang 在 XAML 中处理](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md)。  
  
-   创建自定义的复合字体，以获取更好地控制为不同语言使用的字体。 默认情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用 Windows\Fonts 目录中的 GlobalUserInterface.composite 字体。  
  
-   当你创建导航本地化的应用程序可能从右到左格式在区域性中显示文本，显式设置<xref:System.Windows.FlowDirection>的每个页，以确保页面不会继承<xref:System.Windows.FlowDirection>从<xref:System.Windows.Navigation.NavigationWindow>。  
  
-   在创建托管浏览器之外的独立导航应用程序时，设置<xref:System.Windows.Application.StartupUri%2A>初始应用程序<xref:System.Windows.Navigation.NavigationWindow>而不是到页面 (例如， `<Application StartupUri="NavigationWindow.xaml">`)。 这种设计使你能够更改<xref:System.Windows.FlowDirection>的窗口和导航栏。 有关详细信息及示例，请参阅[全球化主页示例](http://go.microsoft.com/fwlink/?LinkID=159990)。  
  
### <a name="best-practices-for-wpf-localization"></a>WPF 本地化的最佳做法  
 当本地化[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]– 基于应用程序，请考虑实施这些最佳做法：  
  
-   本地化注释用于为本地化人员提供额外的上下文。  
  
-   使用本地化属性来控制而不是有选择地省略本地化<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>元素上的属性。 请参阅[本地化属性和注释](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md)有关详细信息。  
  
-   使用**msbuild /t:updateuid**和**通过**添加并签<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>属性在你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 使用<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>属性，用于开发和本地化之间跟踪更改。 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性可以帮助您本地化新开发更改。 如果你手动添加<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>属性设置为[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，该任务是通常乏味并且不太准确。  
  
    -   无法编辑或更改<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>后你开始进行本地化的属性。  
  
    -   不要使用重复<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>（当你使用复制和粘贴命令，请记住此提示） 的属性。  
  
    -   设置`UltimateResourceFallback`AssemblyInfo.* 指定适当的语言为回退中的位置 (例如， `[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`)。  
  
         如果你决定通过省略主程序集中包括源代码语言`<UICulture>`标记在项目文件中，设置`UltimateResourceFallback`与主要而不是附属程序集的位置 (例如， `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`)。  
  
<a name="workflow_to_localize"></a>   
## <a name="localize-a-wpf-application"></a>对 WPF 应用程序进行本地化  
 当本地化[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序中，有几个选项。 例如，可以将可本地化的资源绑定到应用程序中[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]文件、 将可本地化文本存储在 resx 表，或让本地化人员使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件。 本部分介绍使用 XAML，提供以下几个好处的 BAML 形式的本地化工作流：  
  
-   可以在生成之后进行本地化。  
  
-   可以从较旧版本 XAML 的 BAML 形式更新到本地化的较新版本 XAML 的 BAML 形式，以便在开发的同时进行本地化。  
  
-   你可以验证原始源元素和语义在编译时由于 XAML 的 BAML 形式的已编译的形式[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
### <a name="localization-build-process"></a>本地化生成过程  
 当开发[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序，本地化的生成过程是，如下所示：  
  
-   开发人员创建和全球化[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。 在项目文件中，开发人员设置`<UICulture>en-US</UICulture>`以便编译应用程序后，生成非特定于语言的主程序集。 此程序集具有一个附属 .resources.dll 文件，其中包含所有可本地化的资源。 （可选） 在主程序集中保留源代码语言，因为我们本地化[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]支持从主程序集进行提取。  
  
-   当该文件编译为生成、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]转换为 XAML 的 BAML 形式。 非特定区域性`MyDialog.exe`和文化相关 （英语）`MyDialog.resources.dll`说英语的客户向发布的文件。  
  
### <a name="localization-workflow"></a>本地化工作流  
 在本地化过程开始后未本地化`MyDialog.resources.dll`生成文件。 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]元素和属性在原始[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]使用 XAML 的 BAML 形式为键 / 值对从提取[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]下<xref:System.Windows.Markup.Localizer>。 本地化人员使用键/值对来对应用程序进行本地化。 在本地化完成之后，可以从新值生成一个新的 .resource.dll。  
  
 键 / 值对的键是`x:Uid`值由开发人员在原始置于[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 这些`x:Uid`值启用[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]跟踪并将在本地化过程开发人员和本地化人员之间发生的更改合并。 例如，如果开发人员更改[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]在本地化人员开始本地化后，你可以合并已完成的本地化工作的开发更改，因此，最小转换工作将丢失。  
  
 下图显示了一个基于 XAML 的 BAML 形式的典型本地化工作流。 此图假定开发人员编写英语的应用程序。 开发人员创建 WPF 应用程序并将其全球化。 在项目文件中，开发人员设置`<UICulture>en-US</UICulture>`以便上生成，语言中性主程序集获取使用附属生成。 中所有可本地化的资源。 或者，因为 WPF 本地化 API 支持从主程序集进行提取，所以还可以保留主程序集中的源语言。 生成过程结束之后，XAML 会编译为 BAML。 将向说英语的客户提供非特定区域性的 MyDialog.exe.resources.dll。  
  
 ![本地化工作流](../../../../docs/framework/wpf/advanced/media/localizationworkflow.png "LocalizationWorkflow")  
  
 ![未本地化的工作流](../../../../docs/framework/wpf/advanced/media/localizationworkflow2.png "LocalizationWorkflow2")  
  
<a name="examples_of_localization"></a>   
## <a name="examples-of-wpf-localization"></a>WPF 本地化示例  
 本部分包含本地化的应用程序，以帮助你了解如何生成和本地化示例[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。  
  
#### <a name="run-dialog-box-example"></a>“运行”对话框示例  
 下图显示的输出**运行**对话框示例。  
  
 **英语：**  
  
 ![“运行”对话框](../../../../docs/framework/wpf/advanced/media/rundialogenglish.PNG "RunDialogEnglish")  
  
 **德语：**  
  
 ![德语“运行”对话框](../../../../docs/framework/wpf/advanced/media/rundialoggerman.PNG "RunDialogGerman")  
  
 **设计全球化“运行”对话框**  
  
 该示例产生**运行**对话框中，通过使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。 此对话框中相当于**运行**对话框中，可从[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]开始菜单。  
  
 生成全球化对话框的一些要点包括：  
  
 **自动布局**  
  
 *在 Window1.xaml 中：*  
  
 `<Window SizeToContent="WidthAndHeight">`  
  
 以前的 Window 属性会根据内容大小自动调整窗口大小。 此属性可以防止窗口切断在本地化之后大小增加的内容；它还可以在内容由于本地化而大小减小时删除不必要的空格。  
  
 `<Grid x:Uid="Grid_1">`  
  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性所需顺序[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]本地化[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]正常工作。  
  
 它们由[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]本地化[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]来跟踪更改之间的开发和本地化的[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性使您能够合并的较新版本[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]与较旧的本地化[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 你添加<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>属性通过运行**msbuild /t:updateuid 运行**命令 shell 中。 这是添加的推荐的方法<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>属性因为手动将它们添加为通常耗时且不太准确。 你可以检查是否<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>属性是否正确设置了通过运行**通过运行**。  
  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]使用结构化<xref:System.Windows.Controls.Grid>控制，这很有用要利用自动布局控件中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 请注意，对话框拆分成三行五列。 不是一种行和列定义具有固定的大小;因此，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]位于每个单元中的元素可以调整以适应增加和减少的大小在本地化过程。  
  
 [!code-xaml[GlobalizationRunDialog#GridColumnDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]  
  
 前两列其中**打开：**标签和<xref:System.Windows.Controls.ComboBox>位于使用 10%的[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]总宽度。  
  
 [!code-xaml[GlobalizationRunDialog#GridColumnDef2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]  
  
 请注意，此示例中使用的共享调整大小功能<xref:System.Windows.Controls.Grid>。 最后三个列由将自身放置在相同充分利用此<xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>。 正如属性名称所示，此属性允许不同的列采用相同大小。 因此，在将“Browse…” 本地化为更长的字符串“Durchsuchen…”时，所有按钮的宽度都会增加，而不是显示一个小的“OK”按钮和一个大得不相称的“Durchsuchen…” 按钮。  
  
 **Xml:lang**  
  
 `Xml:lang="en-US"`  
  
 请注意[xml: lang 在 XAML 中处理](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md)的根元素处放置[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 此属性描述给定元素及其子元素的区域性。 此值用于多个特征[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，应在本地化过程相应地更改。 此值会更改在断字以及对字词进行拼写检查时所使用的字典。 它还会影响数字的显示以及字体回退系统选择所用字体的方式。 最后，该属性会影响数值的显示方式，形成在复杂脚本中编写文本的方式。 默认值为“en-US”。  
  
 **生成附属资源程序集**  
  
 *在 .csproj 中：*  
  
 `<UICulture>en-US</UICulture>`  
  
 请注意添加`UICulture`值。 此值设置为有效<xref:System.Globalization.CultureInfo>例如 EN-US，生成项目的值将在其中生成具有所有可本地化的资源的附属程序集。  
  
 `<Resource Include="RunIcon.JPG">`  
  
 `<Localizable>False</Localizable>`  
  
 `</Resource>`  
  
 `RunIcon.JPG`不需要本地化，因为它应显示相同的所有区域性。 `Localizable` 设置为`false`，以便它仍然在语言中性主程序集而不是附属程序集。 所有编译资源的默认值是`Localizable`设置为`true`。  
  
 **本地化“运行”对话框**  
  
 **分析**  
  
 生成应用程序之后，对其进行本地化的第一步是将可本地化的资源从附属程序集中分析出来。 对于本主题的目的，使用示例 LocBaml 工具可在中找到[LocBaml 工具示例](http://go.microsoft.com/fwlink/?LinkID=160016)。 请注意，LocBaml 只是一个示例工具，用于帮助你了解有关如何生成适合你的本地化过程的本地化工具的入门知识。 使用 LocBaml，运行以下命令以分析： **LocBaml/分析 RunDialog.resources.dll /out:**生成"RunDialog.resources.dll.CSV"文件。  
  
 **本地化**  
  
 使用你喜欢的支持 Unicode 的 CSV 编辑器来编辑此文件。 筛选掉本地化类别为“None”的所有项。 应看到下面的项：  
  
|资源键|本地化类别|值|  
|-|-|-| 
|Button_1:System.Windows.Controls.Button.$Content|Button|确定|  
|Button_2:System.Windows.Controls.Button.$Content|Button|取消|  
|Button_3:System.Windows.Controls.Button.$Content|Button|浏览...|  
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|组合框||  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|Windows 将根据您所输入的名称，为您打开相应的程序、文件夹、文档或 Internet 资源。|  
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Text|打开:|  
|Window_1:System.Windows.Window.Title|标题|运行|  
  
 将该应用程序本地化为德语版本需要进行下面的翻译：  
  
|资源键|本地化类别|值|  
|-|-|-| 
|Button_1:System.Windows.Controls.Button.$Content|Button|确定|  
|Button_2:System.Windows.Controls.Button.$Content|Button|Abbrechen|  
|Button_3:System.Windows.Controls.Button.$Content|Button|Durchsuchen…|  
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|组合框||  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetresource an.|  
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|Text|Öffnen:|  
|Window_1:System.Windows.Window.Title|标题|运行|  
  
 **生成**  
  
 本地化的最后一步涉及创建新进行本地化的附属程序集。 可以使用下面的 LocBaml 命令完成此操作：  
  
 **LocBaml.exe /generate RunDialog.resources.dll /trans:RunDialog.resources.dll.CSV /out: . /cul:de-DE**  
  
 德语上[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]，如果此 resources.dll 放置在主程序集旁边的 DE-DE 文件夹中，此资源将自动加载而不是 EN-US 文件夹中的一个。 如果你没有德语版本的[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]要测试这一点，请将区域性设置为任何区域性[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]您正在使用 (即 EN-US)，并替换原始 resources.dll。  
  
 **附属资源加载**  
  
|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|  
|------------------|------------------------------------|------------------------------------|  
|代码|原始英语版 BAML|本地化的 BAML|  
|非特定区域性资源|其他英语资源|已本地化为德语的其他资源|  
  
 .NET framework 会自动选择要加载根据应用程序的哪些附属资源程序集`Thread.CurrentThread.CurrentUICulture`。 这将默认的区域性为你[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]OS。 因此，如果你使用的德语[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]，de-DE\MyDialog.resources.dll 加载时，如果你使用的英语[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]，en-US\MyDialog.resources.dll 加载。 通过在项目的 AssemblyInfo.* 中指定 NeutralResourcesLanguage，可以设置应用程序的最终回退资源。 例如，如果指定：  
  
 `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`  
  
 如果 de-DE\MyDialog.resources.dll 和 de\MyDialog.resources.dll 都不可用，则德语版 Windows 将使用 en-US\MyDialog.resources.dll。  
  
### <a name="microsoft-saudi-arabia-homepage"></a>Microsoft 沙特阿拉伯主页  
 下图显示了英语和阿拉伯语主页。 有关完整的示例生成这些图形[全球化主页示例](http://go.microsoft.com/fwlink/?LinkID=159990)。  
  
 **英语：**  
  
 ![英语页面](../../../../docs/framework/wpf/advanced/media/englishhomepage.jpg "EnglishHomepage")  
  
 **阿拉伯语：**  
  
 ![阿拉伯语页面](../../../../docs/framework/wpf/advanced/media/arabichomepage.jpg "ArabicHomepage")  
  
### <a name="designing-a-global-microsoft-homepage"></a>设计全球 Microsoft 主页  
 Microsoft 沙特阿拉伯网站的这个实体模型说明了针对从右向左布局语言提供的全球化功能。 希伯来语和阿拉伯语等语言有从右到左阅读顺序，因此的布局[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]通常必须布局方式大不相同小于其应有英语等从左到右语言中。 从从左到右布局语言本地化到从右到左布局语言可能相当困难，反之亦然。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 可使此类本地化工作变得更容易。  
  
 **FlowDirection**  
  
 *Homepage.xaml:*  
  
 [!code-xaml[GlobalizationHomepage#Homepage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]  
  
 请注意<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性<xref:System.Windows.Controls.Page>。 更改此属性设置为<xref:System.Windows.FlowDirection.RightToLeft>将更改<xref:System.Windows.FrameworkElement.FlowDirection%2A>的<xref:System.Windows.Controls.Page>及其子级元素，以便此布局[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]成为右到左，如阿拉伯语用户所期望的那样。 一个可以通过指定的显式重写继承行为<xref:System.Windows.FrameworkElement.FlowDirection%2A>的任何元素。 <xref:System.Windows.FrameworkElement.FlowDirection%2A>属性位于任何<xref:System.Windows.FrameworkElement>或文档相关的元素和的值隐式为<xref:System.Windows.FlowDirection.LeftToRight>。  
  
 观察，甚至背景渐变画笔被翻转正确时根<xref:System.Windows.FrameworkElement.FlowDirection%2A>更改：  
  
 **FlowDirection="LeftToRight"**  
  
 ![从左到右显示](../../../../docs/framework/wpf/advanced/media/lefttoright.PNG "LeftToRight")  
  
 **FlowDirection="RightToLeft"**  
  
 ![从右到左显示](../../../../docs/framework/wpf/advanced/media/righttoleft.PNG "RightToLeft")  
  
 **避免对面板和控件使用固定维度**  
  
 请阅读 Homepage.xaml，请注意，除了以外的固定的宽度和高度指定为整个[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]在顶部<xref:System.Windows.Controls.DockPanel>，没有任何其他固定的维度。 请勿使用固定尺寸，以防裁剪可能比源文本长的本地化文本。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 面板和控件将根据其所包含的内容自动调整大小。 大多数控件还具有最小和最大尺寸，设置这些尺寸可以加强控制（例如 MinWidth= "20"）。 与<xref:System.Windows.Controls.Grid>，你还可以通过使用设置相对宽度和高度 * (即宽度 ="0.25\*") 或使用共享功能其单元格大小。  
  
 **本地化注释**  
  
 在很多情况下，内容可能不太明确，难以翻译。 开发人员或设计人员可通过本地化注释为本地化人员提供额外的上下文和注释。 例如，下面的 Localization.Comments 阐明了字符“|”的用法。  
  
 [!code-xaml[GlobalizationHomepage#LocalizationComment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]  
  
 此注释将成为与 TextBlock_1 的内容以及在 LocBaml 工具的情况下关联 (请参阅[本地化应用程序](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md))，将可以看到它输出.csv 文件中的 TextBlock_1 行的第六个列中：  
  
|资源键|类别|可读性|可修改性|注释|值|  
|-|-|-|-|-|-|  
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|Text|true|true|此字符用作装饰性规则。|&#124;|  
  
 使用下面的语法可以将注释放置在任何元素的内容或属性上：  
  
 [!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]  
  
 **本地化特性**  
  
 通常，开发人员或本地化经理需要控制本地化人员能够阅读和修改的内容。 例如，可能不希望本地化人员翻译你公司的名称或法律用语。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了一些特性，使用这些特性可以设置元素的内容或属性（本地化工具可以使用这些内容或属性锁定、隐藏元素或对元素进行排序）的可读性、可修改性和类别。 有关详细信息，请参阅<xref:System.Windows.Localization.Attributes%2A>。 此示例中 LocBaml 工具仅输出这些特性的值。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件对这些特性都使用默认值，但可以替代这些默认值。 例如，下面的示例重写的默认本地化属性`TextBlock_1`和设置对本地化人员内容可读，但不可修改。  
  
 [!code-xaml[LocalizationComAtt#LocalizationAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]  
  
 除了可读性和可修改性特性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供的常见 UI 类别枚举 (<xref:System.Windows.LocalizationCategory>) 可用来为本地化人员提供更多上下文。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]平台控件的默认类别可以中重写[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]以及：  
  
 [!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]  
  
 默认本地化特性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供还可重写通过代码，因此你可以正确设置自定义控件的适当的默认值。 例如：  
  
 `[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]`  
  
 `public class CorporateLogo: TextBlock`  
  
 `{`  
  
 `…`  
  
 `..`  
  
 `.`  
  
 `}`  
  
 每个实例属性中设置[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]将优先于自定义控件的代码中设置的值。 有关特性和注释的详细信息，请参阅[本地化属性和注释](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md)。  
  
 **字体回退和复合字体**  
  
 如果指定不支持给定的码位范围的字体[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]将自动回退到一个通过使用位于 Windows\Fonts 目录全局用户 Interface.compositefont 来执行。 复合字体与任何其他字体的用法相同，通过设置元素的 FontFamily（例如 FontFamily= "Global User Interface"）可以显式使用复合字体。 通过创建你自己的复合字体并指定针对特定代码点范围和语言所使用的字体，可以指定你自己的字体回退首选项。  
  
 有关复合字体的详细信息请参阅<xref:System.Windows.Media.FontFamily>。  
  
 **本地化 Microsoft 主页**  
  
 可以按照“运行”对话框示例中的相同步骤对此应用程序进行本地化。 阿拉伯语的本地化的.csv 文件是否可供你在[全球化主页示例](http://go.microsoft.com/fwlink/?LinkID=159990)。
