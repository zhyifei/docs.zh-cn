---
title: 全球化和本地化概述
ms.date: 03/30/2017
helpviewer_keywords:
- globalization [WPF], about globalization
- localization [WPF], about localization
ms.assetid: 56e5a5c8-6c96-4d19-b8e1-a5be1dc564af
ms.openlocfilehash: 9be6245d7429466490d9dac93c5b94d70bde30bd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744485"
---
# <a name="wpf-globalization-and-localization-overview"></a>WPF 전역화 및 지역화 개요

제품을 한 언어로만 제공하면 잠재적 고객 기반이 전 세계 65억 인구의 극히 일부로만 제한됩니다. 전 세계를 대상으로 하는 애플리케이션을 만들려는 경우 가장 뛰어나고 경제적으로 고객에게 다가갈 수 있는 방법 중 하나는 바로 제품의 비용 효율적인 지역화입니다.

本概述介绍 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]中的全球化和本地化。 전역화는 여러 위치에서 수행되는 애플리케이션의 디자인 및 개발 작업입니다. 예를 들어 전역화는 여러 문화권의 사용자를 위해 지역화된 사용자 인터페이스와 국가별 데이터를 지원합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了全球化设计功能，包括自动布局、附属程序集以及本地化特性和注释。

지역화는 애플리케이션 리소스를 애플리케이션에서 지원할 각 문화권에 맞는 지역화된 버전으로 번역하는 작업입니다. 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中进行本地化时，使用 <xref:System.Windows.Markup.Localizer> 命名空间中的 Api。 这些 Api 支持[LocBaml 工具的示例](https://go.microsoft.com/fwlink/?LinkID=160016)命令行工具。 有关如何生成和使用 LocBaml 的信息，请参阅[本地化应用程序](how-to-localize-an-application.md)。

## <a name="best-practices-for-globalization-and-localization-in-wpf"></a>WPF를 위한 최선의 전역화 및 지역화 방법

通过遵循本部分提供的 UI 设计和本地化相关提示，你可以充分利用中 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内置的大多数全球化和本地化功能。

### <a name="best-practices-for-wpf-ui-design"></a>최선의 WPF UI 디자인 방법

设计基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]时，请考虑实施以下最佳做法：

- 将 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 写入 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中;避免在代码中创建 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]创建 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 时，可以通过内置的本地化 Api 公开此。

- 避免使用绝对位置和固定大小对内容进行布局;请改用相对或自动调整大小。

  - 使用 <xref:System.Windows.Window.SizeToContent%2A>，并将宽度和高度设置为 `Auto`。

  - 避免使用 <xref:System.Windows.Controls.Canvas> 对 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]进行布局。

  - 使用 <xref:System.Windows.Controls.Grid> 及其大小的共享功能。

- 지역화된 텍스트는 공간을 더 많이 필요로 하는 경우가 많으므로 여분의 공간을 여백으로 남겨 둡니다. 여분의 공간을 통해 여분의 문자를 표현할 수 있습니다.

- 启用 <xref:System.Windows.Controls.TextBlock> 上的 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> 以避免剪辑。

- `xml:lang` 특성을 설정합니다. 此属性描述特定元素及其子元素的区域性。 此属性的值更改 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中多个功能的行为。 예를 들어 하이픈 넣기, 맞춤법 검사, 숫자 대체, 복잡한 스크립트 셰이핑 및 글꼴 대체의 동작을 변경합니다. 有关[在 XAML 中设置 xml： Lang 处理](../../../desktop-wpf/xaml-services/xml-language-handling.md)的详细信息，请参阅适用于[WPF 的全球化](globalization-for-wpf.md)。

- 创建自定义的复合字体，以更好地控制用于不同语言的字体。 默认情况下，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 使用 Windows\Fonts 目录中的 GlobalUserInterface 字体。

- 当你创建的导航应用程序可能在以从右向左格式呈现文本的区域性中进行本地化时，请显式设置每个页面的 <xref:System.Windows.FlowDirection>，以确保页面不会从 <xref:System.Windows.Navigation.NavigationWindow>继承 <xref:System.Windows.FlowDirection>。

- 当你创建在浏览器外部托管的独立导航应用程序时，将初始应用程序的 <xref:System.Windows.Application.StartupUri%2A> 设置为 <xref:System.Windows.Navigation.NavigationWindow> 而不是页（例如 `<Application StartupUri="NavigationWindow.xaml">`）。 利用此设计，您可以更改窗口和导航栏的 <xref:System.Windows.FlowDirection>。 有关详细信息和示例，请参阅[全球化主页示例](https://go.microsoft.com/fwlink/?LinkID=159990)。

### <a name="best-practices-for-wpf-localization"></a>WPF 지역화 모범 사례

当你对基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序进行本地化时，请考虑实施下列最佳做法：

- 使用本地化注释为本地化人员提供额外的上下文。

- 使用本地化特性来控制本地化，而不是选择性地省略元素上的 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性。 有关详细信息，请参阅[本地化特性和注释](localization-attributes-and-comments.md)。

- 使用 `msbuild -t:updateuid` 和 `-t:checkuid` 添加和检查 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中的 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性。 使用 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性跟踪开发和本地化之间的更改。 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性可帮助你本地化新的开发更改。 如果手动将 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性添加到 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]中，则该任务通常单调乏味且不太准确。

  - 开始本地化后，请不要编辑或更改 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性。

  - 不要使用重复的 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性（在使用复制和粘贴命令时请记住此提示）。

  - 设置 AssemblyInfo 中的 `UltimateResourceFallback` 位置，以便为回退指定适当的语言（例如，`[assembly: NeutralResourcesLanguage("en-US",   UltimateResourceFallbackLocation.Satellite)]`）。

    如果通过省略项目文件中的 `<UICulture>` 标记来决定在主程序集中包含源语言，请将 `UltimateResourceFallback` 位置设置为主程序集而不是附属程序集（例如 `[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.MainAssembly)]`）。

## <a name="localize-a-wpf-application"></a>WPF 애플리케이션 지역화

对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序进行本地化时，有几个选项。 例如，可以将应用程序中的可本地化资源绑定到 XML 文件，将可本地化的文本存储在 resx 表中，或让本地化人员使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 文件。 本部分介绍使用 XAML 的 BAML 形式的本地化工作流，该工作流提供以下几个优点：

- 您可以在生成后进行本地化。

- 您可以使用 XAML 的 BAML 形式的更早版本中的本地化更新为 XAML 的 BAML 形式的更高版本，以便您可以在开发时进行本地化。

- 可以在编译时验证原始源元素和语义，因为 XAML 的 BAML 形式是 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的编译形式。

### <a name="localization-build-process"></a>지역화 빌드 프로세스

开发 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序时，本地化的生成过程如下所示：

- 开发人员创建并其全球化 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序。 在开发人员将 `<UICulture>en-US</UICulture>` 的项目文件中，这样，在编译应用程序时，将生成一个非特定语言的主程序集。 이 어셈블리에는 지역화 가능한 모든 리소스가 포함된 위성 .resources.dll 파일이 있습니다. 您可以根据需要将源语言保留在主程序集中，因为我们的本地化 Api 支持从主程序集进行提取。

- 将该文件编译为生成时，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 将转换为 XAML 的 BAML 形式。 非特定区域性 `MyDialog.exe` 和与区域性相关的（英语） `MyDialog.resources.dll` 文件将发布给英语客户。

### <a name="localization-workflow"></a>지역화 워크플로

本地化过程在生成未本地化 `MyDialog.resources.dll` 文件后开始。 原始 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 元素和属性通过使用 <xref:System.Windows.Markup.Localizer>下的 Api 从 XAML 的 BAML 形式提取到键值对。 지역화 담당자는 키/값 쌍을 사용하여 애플리케이션을 지역화합니다. 지역화가 완료된 후 새 값에서 새 .resource.dll을 생성할 수 있습니다.

键/值对的键是 `x:Uid` 开发人员置于原始 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中的值。 这些 `x:Uid` 值使 API 能够跟踪和合并本地化期间开发人员和本地化人员之间发生的更改。 例如，如果在本地化人员开始本地化后，开发人员更改了 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，则可以将开发更改与已完成的本地化工作合并，以便最小翻译工作丢失。

다음 그래픽은 BAML 양식의 XAML을 기반으로 하는 일반적인 지역화 워크플로를 보여 줍니다. 此关系图假设开发人员用英语编写应用程序。 개발자가 WPF 애플리케이션을 만들고 전역화합니다. 开发人员将 `<UICulture>en-US</UICulture>` 的项目文件设置为在生成时，使用包含所有可本地化资源的附属. .resources 生成语言中性主程序集。 또는 WPF 지역화 API가 주 어셈블리에서의 추출을 지원하므로 주 어셈블리에서 소스 언어를 유지할 수 있습니다. 빌드 프로세스 후 XAML이 BAML로 컴파일됩니다. 문화권에 중립적인 MyDialog.exe.resources.dll이 영어권 고객에게 제공됩니다.

![显示本地化工作流的关系图。](./media/wpf-globalization-and-localization-overview/localization-workflow.png)

![显示未本地化工作流的关系图。](./media/wpf-globalization-and-localization-overview/unlocalized-workflow.png)

## <a name="examples-of-wpf-localization"></a>WPF 지역화 예제

本部分包含可帮助你了解如何生成和本地化 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序的本地化应用程序的示例。

#### <a name="run-dialog-box-example"></a>실행 대화 상자 예제

下图显示 "**运行**" 对话框示例的输出。

**영어:**

![显示 "英语运行" 对话框的屏幕截图。](./media/wpf-globalization-and-localization-overview/run-dialog-box-english.png)

**독일어:**

![显示德语 "运行" 对话框的屏幕截图。](./media/wpf-globalization-and-localization-overview/run-dialog-box-german.png)

**전역 실행 대화 상자 디자인**

此示例通过使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]生成一个 "**运行**" 对话框。 此对话框等效于 Microsoft Windows "开始" 菜单中提供的 "**运行**" 对话框。

전역 대화 상자를 만들 때 주의해야 할 점은 다음과 같습니다.

**자동 레이아웃**

*Window1.xaml:*

`<Window SizeToContent="WidthAndHeight">`

이전 Window 속성이 창의 크기를 콘텐츠 크기에 맞게 자동으로 조정합니다. 이 속성은 지역화한 후 크기가 증가한 콘텐츠가 창에서 잘리는 것을 방지하며, 지역화한 후 콘텐츠 크기가 줄어들 때 생기는 불필요한 공간도 제거합니다.

`<Grid x:Uid="Grid_1">`

要使 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的本地化 Api 正常工作，<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性是必需的。

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 本地化 Api 使用这些方法跟踪 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]的开发和本地化之间的更改。 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性使你能够将较新版本的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 与 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]的较旧本地化合并在一起。 可以通过在命令行界面中运行 `msbuild -t:updateuid RunDialog.csproj` 来添加 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性。 这是添加 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性的建议方法，因为手动添加它们通常是耗时且不太准确的。 可以通过运行 `msbuild -t:checkuid RunDialog.csproj`来检查 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A> 属性是否正确设置。

通过使用 <xref:System.Windows.Controls.Grid> 控件来构造 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，这是在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中利用自动布局的有用控件。 대화 상자는 세 개의 행과 다섯 개의 열로 나뉩니다. 不是行和列定义中的一个具有固定的大小;因此，位于每个单元格中的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 元素可以在本地化过程中适应大小的增加和减小。

[!code-xaml[GlobalizationRunDialog#GridColumnDef](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef)]

放置**打开的：** 标签和 <xref:System.Windows.Controls.ComboBox> 的前两列使用 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 总宽度的10%。

[!code-xaml[GlobalizationRunDialog#GridColumnDef2](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationRunDialog/CS/Window1.xaml#gridcolumndef2)]

请注意，此示例使用 <xref:System.Windows.Controls.Grid>的共享大小调整功能。 最后三列通过将其放在同一 <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>中来利用这一点。 속성의 이름에서 알 수 있듯이 이 속성을 통해 열은 같은 크기를 공유할 수 있습니다. 因此，当 "浏览 ..."已本地化为较长的字符串 "Durchsuchen ... ..."，所有按钮的宽度都将增加，而不是使用较小的 "确定" 按钮和不成比例的 "Durchsuchen ... ..."鼠标.

**xml:lang**

`xml:lang="en-US"`

请注意， [XAML 中的 xml： Lang 处理](../../../desktop-wpf/xaml-services/xml-language-handling.md)置于 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]的根元素中。 이 속성은 해당 요소 및 자식의 문화권을 설명합니다. 此值由 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的多个功能使用，并且应在本地化过程中相应地进行更改。 이 값은 단어 하이픈 넣기와 맞춤법 검사에 사용할 언어 사전을 변경합니다. 또한 숫자의 표시 및 글꼴 대체 시스템에서 사용할 글꼴을 선택하는 방법에도 영향을 줍니다. 마지막으로, 속성은 숫자 표시 방식과 복잡한 스크립트에 포함된 텍스트의 모양이 지정되는 방식에 영향을 줍니다. 기본값은 "en-US"입니다.

**위성 리소스 어셈블리 빌드**

*.csproj:*

编辑 `.csproj` 文件，并将以下标记添加到无条件 `<PropertyGroup>`：

`<UICulture>en-US</UICulture>`

请注意，添加了 `UICulture` 值。 如果将此项设置为有效 <xref:System.Globalization.CultureInfo> 值（例如 en-us），则生成项目时将生成包含其中所有可本地化资源的附属程序集。

`<Resource Include="RunIcon.JPG">`

`<Localizable>False</Localizable>`

`</Resource>`

不需要对 `RunIcon.JPG` 进行本地化，因为它对于所有区域性都应该是相同的。 `Localizable` 设置为 `false`，以使其保留在语言中性主程序集中，而不是附属程序集。 所有 noncompilable 资源的默认值均 `Localizable` 设置为 `true`。

**실행 대화 상자 지역화**

**구문 분석**

애플리케이션을 빌드한 후 지역화의 첫 번째 단계는 위성 어셈블리에서 지역화할 수 있는 리소스를 구문 분석하는 것입니다. 出于本主题的目的，请使用示例 LocBaml 工具，该工具可在[LocBaml 工具示例](https://go.microsoft.com/fwlink/?LinkID=160016)中找到。 LocBaml은 지역화 프로세스에 적합한 지역화 도구의 빌드에 도움을 주기 위한 샘플 도구입니다. 使用 LocBaml，运行以下内容来分析： **LocBaml/Parse rundialog.csproj/out：** 生成 "rundialog.csproj" 文件的文件。

**지역화**

유니코드를 지원하는 CSV 편집기 중 적절한 것을 사용하여 이 파일을 편집합니다. 지역화 범주가 “None”인 모든 항목을 필터링합니다. 다음과 같은 항목이 표시되어야 합니다.

|리소스 키|지역화 범주|값|
|-|-|-|
|Button_1:System.Windows.Controls.Button.$Content|단추|확인|
|Button_2:System.Windows.Controls.Button.$Content|단추|Cancel|
|Button_3:System.Windows.Controls.Button.$Content|단추|찾아보기...|
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|텍스트|프로그램, 폴더, 문서 또는 인터넷 리소스의 이름을 입력하면 Windows에서 열립니다.|
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|텍스트|열기:|
|Window_1:System.Windows.Window.Title|제목|를 실행합니다.|

애플리케이션을 독일어로 지역화하려면 다음과 같이 번역해야 합니다.

|리소스 키|지역화 범주|값|
|-|-|-|
|Button_1:System.Windows.Controls.Button.$Content|단추|확인|
|Button_2:System.Windows.Controls.Button.$Content|단추|Abbrechen|
|Button_3:System.Windows.Controls.Button.$Content|단추|Durchsuchen…|
|ComboBox_1:System.Windows.Controls.ComboBox.$Content|ComboBox||
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|텍스트|Geben Sie den Namen eines Programms, Ordners, Dokuments oder einer Internetresource an.|
|TextBlock_2:System.Windows.Controls.TextBlock.$Content|텍스트|열기:|
|Window_1:System.Windows.Window.Title|제목|를 실행합니다.|

**생성**

지역화의 마지막 단계에서는 새로 지역화된 위성 어셈블리를 만듭니다. 이렇게 하려면 다음 LocBaml 명령을 사용합니다.

**LocBaml.exe /generate RunDialog.resources.dll /trans:RunDialog.resources.dll.CSV /out: . /cul:de-DE**

在德语窗口上，如果将此资源 .dll 放置在主程序集旁边的取消拖放文件夹中，则此资源将自动加载，而不是 en-us 文件夹中的一个。 如果你没有德语版本的 Windows 来测试这种情况，请将区域性设置为要使用的 Windows 的任何区域性（例如 `en-US`），并替换原始的资源 DLL。

**위성 리소스 로드**

|MyDialog.exe|en-US\MyDialog.resources.dll|de-DE\MyDialog.resources.dll|
|------------------|------------------------------------|------------------------------------|
|代码|원본 영어 BAML|지역화된 BAML|
|문화권에 중립적인 리소스|영어로 된 기타 리소스|독일어로 지역화된 기타 리소스|

.NET framework 会根据应用程序的 `Thread.CurrentThread.CurrentUICulture`自动选择要加载的附属资源程序集。 此值默认为 Windows OS 的区域性。 因此，如果您使用的是德语 Windows，则会加载 de-DE\MyDialog.resources.dll，如果您使用的是英语 Windows，则 en-US\MyDialog.resources.dll 会加载。 프로젝트의 AssemblyInfo.*에 NeutralResourcesLanguage를 지정하여 애플리케이션에 대한 최종 대체 리소스를 설정할 수 있습니다. 예를 들면 다음과 같이 지정할 수 있습니다.

`[assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]`

그러면 de-DE\MyDialog.resources.dll 또는 de\MyDialog.resources.dll을 모두 사용할 수 없는 경우 en-US\MyDialog.resources.dll이 독일어 Windows에 사용됩니다.

### <a name="microsoft-saudi-arabia-homepage"></a>Microsoft 사우디아라비아 홈페이지

다음 그래픽에서는 영어 및 아랍어 홈페이지를 보여 줍니다. 有关生成这些图形的完整示例，请参阅[全球化主页示例](https://go.microsoft.com/fwlink/?LinkID=159990)。

**영어:**

![显示英语主页的屏幕截图。](./media/wpf-globalization-and-localization-overview/english-home-page-sample.jpg)

**아랍어:**

![显示阿拉伯语主页的屏幕截图。](./media/wpf-globalization-and-localization-overview/arabic-home-page-sample.jpg)

### <a name="designing-a-global-microsoft-home-page"></a>设计全球 Microsoft 主页

이 Microsoft 사우디아라비아 웹 사이트 샘플에서는 RightToLeft 언어를 위해 제공되는 전역화 기능을 보여 줍니다. 希伯来语和阿拉伯语等语言具有从右到左的阅读顺序，因此，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 布局的布局通常与从左到右的语言（如英语）的布局不同。 왼쪽에서 오른쪽으로 읽는 언어를 오른쪽에서 왼쪽으로 읽는 언어로 또는 그 반대로 지역화하는 작업은 꽤 까다로울 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 이러한 지역화를 훨씬 쉽게 수행할 수 있도록 디자인되었습니다.

**FlowDirection**

*Homepage.xaml:*

[!code-xaml[GlobalizationHomepage#Homepage](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#homepage)]

请注意 <xref:System.Windows.Controls.Page>上的 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性。 将此属性更改为 "<xref:System.Windows.FlowDirection.RightToLeft> 将更改 <xref:System.Windows.Controls.Page> 及其子元素的 <xref:System.Windows.FrameworkElement.FlowDirection%2A>，以便将此 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的布局反向转换为与阿拉伯语用户所期望的从右到左。 通过在任何元素上指定显式 <xref:System.Windows.FrameworkElement.FlowDirection%2A>，可以重写继承行为。 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性可用于任何 <xref:System.Windows.FrameworkElement> 或文档相关元素，并且具有隐式值 <xref:System.Windows.FlowDirection.LeftToRight>。

请注意，当根 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 更改时，即使背景渐变画笔也能正确翻转：

**FlowDirection="LeftToRight"**

![显示从左到右的渐变流的屏幕截图。](./media/wpf-globalization-and-localization-overview/gradient-flow-left-right.png)

**FlowDirection="RightToLeft"**

![显示从右到左渐变流的屏幕截图。](./media/wpf-globalization-and-localization-overview/gradient-flow-right-left.png)

**패널 및 컨트롤에 고정 크기 사용 피하기**

浏览主页 .xaml，注意除了为顶部 <xref:System.Windows.Controls.DockPanel>上的整个 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 指定的固定宽度和高度以外，没有其他固定尺寸。 지역화된 텍스트가 소스 텍스트보다 길어서 잘리는 것을 방지하기 위해 고정된 크기를 사용하지 않도록 하세요. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패널 및 컨트롤은 포함된 콘텐츠에 따라 자동으로 크기가 조정됩니다. 大多数控件也具有可以设置以进行更多控制的最小和最大尺寸（例如，MinWidth = "20"）。 使用 <xref:System.Windows.Controls.Grid>，还可以通过使用 "\*" （例如 `Width="0.25*"`）或使用其单元大小共享功能设置相对宽度和高度。

**지역화 주석**

콘텐츠가 모호하여 번역하기 어려운 경우도 많이 있습니다. 개발자나 디자이너는 지역화 주석을 통해 지역화 담당자에게 추가적인 컨텍스트 및 주석을 제공할 수 있습니다. 예를 들어 아래의 Localization.Comments에서는 문자 ‘&#124;’의 사용을 명확하게 설명합니다.

[!code-xaml[GlobalizationHomepage#LocalizationComment](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcomment)]

此注释将与 TextBlock_1 的内容相关联，并在 LocBaml 工具（请参阅[本地化应用程序](how-to-localize-an-application.md)）的情况下，可在输出 .csv 文件中 TextBlock_1 行的第6列中查看：

|리소스 키|범주|가독성|수정 가능성|설명|값|
|-|-|-|-|-|-|
|TextBlock_1:System.Windows.Controls.TextBlock.$Content|텍스트|true|true|이 문자는 장식 규칙으로 사용됩니다.|&#124;|

다음 구문을 사용하여 주석을 요소의 속성 또는 콘텐츠에 배치할 수 있습니다.

[!code-xaml[GlobalizationHomepage#LocalizationCommentsProp](~/samples/snippets/csharp/VS_Snippets_Wpf/GlobalizationHomepage/CS/Homepage.xaml#localizationcommentsprop)]

**지역화 특성**

개발자 또는 지역화 관리자는 지역화 담당자가 읽고 수정할 수 있는 컨트롤을 필요로 할 수 있습니다. 예를 들어 회사 이름이나 법적 고지문은 번역하지 않아야 할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 지역화 도구가 요소를 잠그거나, 숨기거나, 정렬할 때 사용할 수 있는 요소의 콘텐츠나 속성의 가독성, 수정 가능 여부 및 범주를 설정할 수 있는 특성을 제공합니다. 자세한 내용은 <xref:System.Windows.Localization.Attributes%2A>를 참조하세요. 이 샘플의 목적상 LocBaml 도구는 이러한 특성의 값만 출력합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤은 모두 이러한 특성에 대해 기본값을 사용하지만 이를 재정의할 수 있습니다. 例如，下面的示例将重写 `TextBlock_1` 的默认本地化属性，并将内容设置为可读但对于本地化人员是不可修改的。

[!code-xaml[LocalizationComAtt#LocalizationAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributes)]

除了可读性和可修改性特性之外，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还提供了一个可用于向本地化人员提供更多上下文的常见 UI 类别（<xref:System.Windows.LocalizationCategory>）的枚举。 还可以在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中覆盖平台控件 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 默认类别：

[!code-xaml[LocalizationComAtt#LocalizationAttributesOverridden](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationComAtt/CSharp/Attributes.xaml#localizationattributesoverridden)]

还可以通过代码覆盖 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供的默认本地化特性，以便为自定义控件正确设置正确的默认值。 예를 들면 다음과 같습니다.:

```csharp
[Localizability(Readability = Readability.Readable, Modifiability=Modifiability.Unmodifiable, LocalizationCategory.None)]
public class CorporateLogo : TextBlock
{
    // ...
}
```

在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中设置的每个实例属性将优先于在自定义控件的代码中设置的值。 有关属性和注释的详细信息，请参阅[本地化特性和注释](localization-attributes-and-comments.md)。

**글꼴 대체 및 복합 글꼴**

如果指定的字体不支持给定的点区范围，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 将自动回退到使用 Windows\Fonts 目录中的全局用户界面的 compositefont。 复合字体的工作方式与任何其他字体一样，可通过设置元素的 `FontFamily` （例如，`FontFamily="Global User Interface"`）来显式使用。 복합 글꼴을 직접 만들고 특정 코드 포인트 범위와 언어에 사용할 글꼴을 지정하여 글꼴 대체 기본 설정을 직접 지정할 수 있습니다.

有关复合字体的详细信息，请参阅 <xref:System.Windows.Media.FontFamily>。

**Microsoft 홈페이지 지역화**

실행 대화 상자와 동일한 단계를 사용하여 이 애플리케이션을 지역화할 수 있습니다. 在[全球化主页示例](https://go.microsoft.com/fwlink/?LinkID=159990)中提供了适用于阿拉伯语的本地化 .csv 文件。
