---
title: 包 Uri
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: 0fec72bdedbcc2c84d8bc65e72391366e42d82be
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739158"
---
# <a name="pack-uris-in-wpf"></a>WPF의 Pack URI

在 Windows Presentation Foundation （WPF）中，统一资源标识符（Uri）用于通过多种方式标识和加载文件，其中包括：

- 指定在应用程序首次启动时要显示的 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。

- 이미지 로드

- 페이지 탐색

- 비실행 데이터 파일 로드

此外，可以使用 Uri 来标识和加载来自各种位置的文件，包括以下各项：

- 현재 어셈블리입니다.

- 참조된 어셈블리

- 어셈블리에 상대적인 위치

- 애플리케이션의 원본 사이트

为了提供用于从这些位置标识和加载这些类型的文件的一致机制，WPF 利用了*PACK URI 方案*的扩展性。 本主题概述了方案，并介绍了如何为各种方案构造包 Uri，以及如何在显示如何使用标记和代码中的 pack Uri 之前介绍绝对和相对 Uri 以及 URI 解析。

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a>Pack URI 체계

Pack URI 方案由[开放式打包约定](https://go.microsoft.com/fwlink/?LinkID=71255)（OPC）规范使用，此规范描述了用于组织和标识内容的模型。 此模型的关键元素是包和部件，其中，*包*是一个或多个逻辑*部分*的逻辑容器。 다음 그림에서는 이 개념을 보여 줍니다.

![패키지 및 파트 다이어그램](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

为了识别部件，OPC 规范利用了 RFC 2396 （统一资源标识符（URI）：通用语法）的扩展性来定义 pack URI 方案。

由 URI 指定的方案由其前缀定义;http、ftp 和 file 是众所周知的示例。 Pack URI 方案使用 "pack" 作为其方案，并且包含两个组件：颁发机构和路径。 下面是 pack URI 的格式。

pack://*机构*/*路径*

*颁发机构*指定包含部件的包类型，而*路径*指定部件在包中的位置。

다음 그림에서는 이 개념을 보여 줍니다.

![패키지, 권한 및 경로의 관계](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

패키지와 파트는 애플리케이션 및 파일과 유사합니다. 즉, 애플리케이션(패키지)은 다음을 비롯한 하나 이상의 파일(파트)을 포함할 수 있습니다.

- 로컬 어셈블리로 컴파일되는 리소스 파일

- 참조된 어셈블리로 컴파일되는 리소스 파일

- 참조하는 어셈블리로 컴파일되는 리소스 파일

- 콘텐츠 파일

- 원본 사이트 파일

为了访问这些类型的文件，WPF 支持两个权限： application:///和 siteoforigin:///。 application:/// 인증 기관은 리소스 및 콘텐츠 파일을 비롯하여 컴파일 시 알려진 애플리케이션 데이터 파일을 식별합니다. siteoforigin:/// 인증 기관은 원본 사이트 파일을 식별합니다. 다음 그림에서는 각 인증 기관의 범위를 보여 줍니다.

![Pack URI 다이어그램](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> 包 URI 的颁发机构组件是一个指向包并必须符合 RFC 2396 的嵌入 URI。 또한 “/” 문자를 “,” 문자로 바꾸고 “%” 및 “?” 같은 예약 문자는 이스케이프해야 합니다. 자세한 내용은 OPC를 참조하세요.

以下各节说明如何使用这两个颁发机构构造包 Uri 以及用于标识资源、内容和源站点文件的相应路径。

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a>리소스 파일 Pack URI

资源文件配置为 MSBuild `Resource` 项，并编译到程序集中。 WPF 支持构造包 Uri，这些 Uri 可用于标识编译到本地程序集中或编译到从本地程序集引用的程序集中的资源文件。

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a>로컬 어셈블리 리소스 파일

编译到本地程序集的资源文件的 pack URI 使用以下授权和路径：

- **인증 기관**: application:///

- **경로**: 로컬 어셈블리 프로젝트 폴더 루트에 상대적인 경로를 포함한 리소스 파일의 이름

下面的示例演示位于本地程序集的项目文件夹的根目录中的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 资源文件的 pack URI。

`pack://application:,,,/ResourceFile.xaml`

下面的示例演示位于本地程序集的项目文件夹的子文件夹中的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 资源文件的 pack URI。

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a>참조된 어셈블리 리소스 파일

编译到引用的程序集中的资源文件的 pack URI 使用以下授权和路径：

- **인증 기관**: application:///

- **경로**: 참조된 어셈블리로 컴파일되는 리소스 파일의 이름. 경로는 다음 형식을 따라야 합니다.

  *AssemblyShortName*{ *;版本*] { *;PublicKey*]; 组件/*路径*

  - **AssemblyShortName**: 참조된 어셈블리에 대한 약식 이름

  - **;Version**[옵션]: 리소스 파일을 포함하는 참조된 어셈블리의 버전. 동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.

  - **;PublicKey**[옵션]: 참조된 어셈블리를 서명하는 데 사용된 공개 키. 동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.

  - **;component**: 참조되는 어셈블리가 로컬 어셈블리에서 참조된다는 것을 지정

  - **/Path**: 참조된 어셈블리 프로젝트 폴더의 루트에 상대적인 경로를 포함한 리소스 파일의 이름

下面的示例显示了位于所引用程序集的项目文件夹的根目录中的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 资源文件的 pack URI。

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

下面的示例显示了位于所引用程序集的项目文件夹的子文件夹中的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 资源文件的 pack URI。

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

下面的示例演示一个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 资源文件的 pack URI，该文件位于所引用的特定于版本的程序集的项目文件夹的根文件夹中。

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

请注意，所引用的程序集资源文件的 pack URI 语法只能与 application:///机构一起使用。 例如，WPF 不支持以下。

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a>콘텐츠 파일 Pack URI

内容文件的 pack URI 使用以下授权和路径：

- **인증 기관**: application:///

- **경로**: 애플리케이션의 주 실행 가능 어셈블리의 파일 시스템 위치에 상대적인 경로를 포함한 콘텐츠 파일의 이름

下面的示例演示与可执行程序集位于同一文件夹中的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 内容文件的 pack URI。

`pack://application:,,,/ContentFile.xaml`

下面的示例演示一个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 内容文件的 pack URI，该 URI 位于相对于应用程序的可执行程序集的子文件夹中。

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> 不能导航到 HTML 内容文件。 URI 方案仅支持导航到位于源站点的 HTML 文件。

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a>원본 사이트 Pack URI

源站点文件的 pack URI 使用以下授权和路径：

- **인증 기관**: siteoforigin:///

- **경로**: 실행 가능 어셈블리가 시작된 위치에 상대적인 경로를 포함한 원본 사이트 파일의 이름

下面的示例显示了一个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 源站点文件的 pack URI，该 URI 存储在从中启动可执行程序集的位置。

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

下面的示例显示了一个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 源站点文件的 pack URI，该 URI 存储在相对于应用程序可执行程序集的启动位置的子文件夹中。

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a>페이지 파일

配置为 MSBuild `Page` 项的 XAML 文件将以与资源文件相同的方式编译到程序集中。 因此，可以使用资源文件的 pack Uri 来标识 MSBuild `Page` 项。

通常配置为 MSBuild`Page` 项的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件的类型具有以下项之一作为其根元素：

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a>绝对和相对 Pack Uri

完全限定的 pack URI 包含方案、颁发机构和路径，并被视为绝对包 URI。 作为开发人员的简化，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 元素通常允许使用相对 pack URI 设置相应的属性，其中只包含路径。

例如，请考虑本地程序集中某个资源文件的以下绝对包 URI。

`pack://application:,,,/ResourceFile.xaml`

引用此资源文件的相对 pack URI 如下所示。

`/ResourceFile.xaml`

> [!NOTE]
> 由于源站点文件不与程序集相关联，因此只能用绝对包 Uri 来引用它们。

默认情况下，相对 pack URI 被视为相对于包含引用的标记或代码的位置。 但是，如果使用前导反斜杠，则相对 pack URI 引用将被视为相对于应用程序的根。 예를 들어 다음과 같은 프로젝트 구조를 가정해 봅니다.

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

如果 Page1 包含引用*根*\SUBFOLDER\PAGE2.XAML 的 URI，则引用可以使用以下相对 pack URI。

`Page2.xaml`

如果 Page1 包含引用*根*\PAGE2.XAML 的 URI，则引用可以使用以下相对 pack URI。

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a>Pack URI 확인

Pack Uri 的格式使得不同类型的文件的包 Uri 能够看起来相同。 例如，请考虑下面的绝对包 URI。

`pack://application:,,,/ResourceOrContentFile.xaml`

此绝对包 URI 可以引用本地程序集或内容文件中的资源文件。 对于以下相对 URI 也是如此。

`/ResourceOrContentFile.xaml`

为了确定 pack URI 引用的文件类型，WPF 使用以下试探法解析本地程序集中的资源文件和内容文件的 Uri：

1. 探测与 pack URI 匹配的 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性的程序集元数据。

2. 如果找到 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性，包 URI 的路径将引用一个内容文件。

3. 如果找不到 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 特性，请探测编译到本地程序集的资源文件。

4. 如果找到与包 URI 的路径匹配的资源文件，则包 URI 的路径引用资源文件。

5. 如果找不到该资源，则内部创建的 <xref:System.Uri> 无效。

URI 解析不适用于引用以下各项的 Uri：

- 引用的程序集中的内容文件： WPF 不支持这些文件类型。

- 引用的程序集中的嵌入文件：标识这些文件的 Uri 是唯一的，因为它们包括引用的程序集的名称和 `;component` 后缀。

- 源站点文件：标识它们的 Uri 是唯一的，因为它们是可以由包含 siteoforigin:///机构的 pack Uri 标识的唯一文件。

Pack URI 解析可以通过一种简化来使代码在一定程度上独立于资源和内容文件的位置。 例如，如果本地程序集中有一个资源文件，该文件已重新配置为内容文件，则该资源的 pack URI 将保持不变，这与使用包 URI 的代码一样。

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a>Pack URI를 사용한 프로그래밍

许多 WPF 类实现可通过 pack Uri 进行设置的属性，包括：

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

이러한 속성을 태그와 코드 모두에서 설정할 수 있습니다. 이 섹션에서는 두 경우에 대한 기본 구조를 설명한 다음 일반적인 시나리오 예제를 보여 줍니다.

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a>태그에서 Pack URI 사용

通过使用 pack URI 设置特性的元素，在标记中指定包 URI。 예를 들면 다음과 같습니다.:

`<element attribute="pack://application:,,,/File.xaml" />`

表1说明了可在标记中指定的各种绝对包 Uri。

표 1: 태그의 절대 Pack URI

|File|绝对包 URI|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|리소스 파일 - 로컬 어셈블리|`"pack://application:,,,/ResourceFile.xaml"`|
|하위 폴더의 리소스 파일 - 로컬 어셈블리|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|리소스 파일 - 참조된 어셈블리|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|참조된 어셈블리의 하위 폴더에 있는 리소스 파일|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|버전이 있는 참조된 어셈블리의 리소스 파일|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|콘텐츠 파일|`"pack://application:,,,/ContentFile.xaml"`|
|하위 폴더의 콘텐츠 파일|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|원본 사이트 파일|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|하위 폴더의 원본 사이트 파일|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

表2说明了可以在标记中指定的各种相对包 Uri。

표 2: 태그의 상대 Pack URI

|File|相对 pack URI|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|로컬 어셈블리의 리소스 파일|`"/ResourceFile.xaml"`|
|로컬 어셈블리의 하위 폴더에 있는 리소스 파일|`"/Subfolder/ResourceFile.xaml"`|
|참조된 어셈블리의 리소스 파일|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|참조된 어셈블리의 하위 폴더에 있는 리소스 파일|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|콘텐츠 파일|`"/ContentFile.xaml"`|
|하위 폴더의 콘텐츠 파일|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a>코드에서 Pack URI 사용

通过实例化 <xref:System.Uri> 类并将包 URI 作为参数传递给构造函数，可以在代码中指定包 URI。 다음 예제를 통해 볼 수 있습니다.

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

默认情况下，<xref:System.Uri> 类将包 Uri 视为绝对 Uri。 因此，当使用相对 pack URI 创建 <xref:System.Uri> 类的实例时，将引发异常。

```csharp
Uri uri = new Uri("/File.xaml");
```

幸运的是，<xref:System.Uri> 类构造函数的 <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> 重载接受 <xref:System.UriKind> 类型的参数，以允许您指定包 URI 是绝对的还是相对的。

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

在确定所提供的 pack URI 为 one 时，应仅指定 <xref:System.UriKind.Absolute> 或 <xref:System.UriKind.Relative>。 如果你不知道所使用的 pack URI 的类型，例如当用户在运行时输入包 URI 时，请改用 <xref:System.UriKind.RelativeOrAbsolute>。

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

表3说明了可以使用 <xref:System.Uri?displayProperty=nameWithType>在代码中指定的各种相对包 Uri。

표 3: 코드의 절대 Pack URI

|File|绝对包 URI|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|리소스 파일 - 로컬 어셈블리|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|하위 폴더의 리소스 파일 - 로컬 어셈블리|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|리소스 파일 - 참조된 어셈블리|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|참조된 어셈블리의 하위 폴더에 있는 리소스 파일|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|버전이 있는 참조된 어셈블리의 리소스 파일|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|콘텐츠 파일|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|하위 폴더의 콘텐츠 파일|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|원본 사이트 파일|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|하위 폴더의 원본 사이트 파일|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

表4说明了可使用 <xref:System.Uri?displayProperty=nameWithType>在代码中指定的各种相对包 Uri。

표 4: 코드의 상대 Pack URI

|File|相对 pack URI|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|리소스 파일 - 로컬 어셈블리|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|하위 폴더의 리소스 파일 - 로컬 어셈블리|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|리소스 파일 - 참조된 어셈블리|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|하위 폴더의 리소스 파일 - 참조된 어셈블리|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|콘텐츠 파일|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|하위 폴더의 콘텐츠 파일|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a>일반적인 Pack URI 시나리오

前面几节讨论了如何构造包 Uri 来标识资源、内容和源站点文件。 在 WPF 中，可以通过多种方式使用这些构造，以下部分介绍了几种常见的用法。

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a>애플리케이션을 시작할 때 표시되는 UI 지정

<xref:System.Windows.Application.StartupUri%2A> 指定在启动 WPF 应用程序时要显示的第一个 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 对于独立应用程序，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 可以是窗口，如下面的示例中所示。

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

独立应用程序和 XAML 浏览器应用程序（Xbap）还可以将页指定为初始 UI，如下面的示例中所示。

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

如果应用程序是独立的应用程序，并且使用 <xref:System.Windows.Application.StartupUri%2A>指定了页面，则 WPF 将打开一个 <xref:System.Windows.Navigation.NavigationWindow> 来承载页面。 对于 Xbap，将在主机浏览器中显示页面。

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a>페이지 탐색

다음 예제에서는 페이지를 탐색하는 방법을 보여 줍니다.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

有关在 WPF 中导航的各种方式的详细信息，请参阅[导航概述](navigation-overview.md)。

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a>창 아이콘 지정

다음 예제에서는 URI를 사용하여 창 아이콘을 지정하는 방법을 보여 줍니다.

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

자세한 내용은 <xref:System.Windows.Window.Icon%2A>를 참조하세요.

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a>이미지, 오디오 및 비디오 파일 로드

WPF 允许应用程序使用各种媒体类型，所有这些类型都可以使用 pack Uri 进行标识和加载，如下面的示例中所示。

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

有关使用媒体内容的详细信息，请参阅[图形和多媒体](../graphics-multimedia/index.md)。

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a>원본 사이트에서 리소스 사전 로드

资源字典（<xref:System.Windows.ResourceDictionary>）可用于支持应用程序主题。 테마를 만들고 관리하는 한 가지 방법은 애플리케이션의 원본 사이트에 위치한 리소스 사전으로 여러 개의 테마를 만드는 것입니다. 이렇게 하면 애플리케이션을 다시 컴파일하여 배포할 필요 없이 테마를 추가하고 업데이트할 수 있습니다. 可以使用 pack Uri 来标识和加载这些资源字典，如以下示例中所示。

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

有关 WPF 中的主题的概述，请参阅[样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)。

## <a name="see-also"></a>另请参阅

- [WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일](wpf-application-resource-content-and-data-files.md)
