---
title: 전역화
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: 95c0368889dfa4e69b5e40b32ea19ba845aa5c30
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747050"
---
# <a name="globalization-for-wpf"></a>WPF의 전역화
本主题介绍编写全局市场 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 应用程序时应注意的问题。 全球化编程元素在 <xref:System.Globalization> 命名空间的 .NET 中定义。

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a>XAML 전역화
 Extensible Application Markup Language （XAML）基于 XML，并利用 XML 规范中定义的全球化支持。 以下部分介绍了一些您应该注意的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 功能。

<a name="char_reference"></a>
### <a name="character-references"></a>문자 참조
字符引用以十进制或十六进制形式为其表示的特定 Unicode 字符提供 UTF16 代码单元。 下面的示例显示了一个用于哥普特大写字母 HORI 或 "Ϩ" 的十进制字符引用：

```
&#1000;
```

下面的示例演示十六进制字符引用。 请注意，它在十六进制数字前面有一个**x** 。

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a>Encoding
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 支持的编码为 ASCII、Unicode UTF-16 和 UTF-8。 编码语句位于 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文档的开头。 인코딩 특성이 없으며 바이트 순서가 없으면 기본적으로 구문 분석기가 UTF-8로 설정됩니다. UTF-8과 UTF-16이 기본 인코딩입니다. UTF-7은 지원되지 않습니다. 下面的示例演示如何在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件中指定 UTF-8 编码。

```xaml
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a>언어 특성
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 使用[xml： lang](../../../desktop-wpf/xaml-services/xml-language-handling.md)表示元素的 language 特性。  若要利用 <xref:System.Globalization.CultureInfo> 类，language 特性值需要是由 <xref:System.Globalization.CultureInfo>预定义的区域性名称之一。 [xml:lang](../../../desktop-wpf/xaml-services/xml-language-handling.md)은 요소 트리에서 상속 가능하며(반드시 종속성 속성 상속성때문이 아니라 XML 규칙에 따름), 명시적으로 할당되지 않은 경우 기본값은 비어 있습니다.

 언어를 지정할 때 언어 특성이 매우 유용합니다. 예를 들어, 프랑스, 퀘벡, 벨기에 및 스위스의 프랑스어에는 다른 철자, 어휘 및 발음이 있습니다. 同时，中文、日语和朝鲜语使用 Unicode 共享码位，但表意形状不同，它们使用完全不同的字体。

 以下 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 示例使用 `fr-CA` language 特性指定加拿大法语。

```xaml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a>유니코드(Unicode)
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 支持所有 Unicode 功能，包括代理项。 只要字符集可以映射到 Unicode，就支持该字符集。 예를 들어, GB18030에서는 중국어, 일본어 및 한국어(CFK) 확장 A와 B에 매핑되는 일부 문자와 서로게이트 쌍을 소개하므로 완전히 지원됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序可以使用 <xref:System.Globalization.StringInfo> 操作字符串，而无需了解它们是否具有代理项对或组合字符。

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a>XAML로 국가별 사용자 인터페이스 설계
 本部分介绍编写应用程序时应考虑的 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 功能。

<a name="intl_text"></a>
### <a name="international-text"></a>국가별 텍스트
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 包括针对所有 Microsoft .NET Framework 支持的书写系统的内置处理。

 현재 지원되는 스크립트는 다음과 같습니다.

- 아랍어

- 벵골어

- 데바나가리어

- 키릴 자모

- 그리스어

- 구자라트어

- 굴묵키어

- 히브리어

- 표의 문자 스크립트

- 칸나다어

- 라오어

- 라틴어

- 말라얄람어

- 몽골어

- 오리야어

- 시리아어

- 타밀어

- 텔루구어

- 타나 문자

- 태국어*

- 티베트어

 \* 이 릴리스에서는 태국어 텍스트의 표시 및 편집이 지원되며, 단어 구분은 지원되지 않습니다.

 현재 지원되지 않는 스크립트는 다음과 같습니다.

- 크메르어

- 한국어 옛 한글

- 미얀마어

- 스리랑카어

 所有书写系统引擎都支持 OpenType 字体。 OpenType 字体可以包含 OpenType 布局表，它们使字体创建者能够设计更好的国际化和高端版式字体。 OpenType 字体布局表包含有关符号替换、标志符号定位、对齐和基线定位的信息，使文本处理应用程序能够改进文本布局。

 OpenType 字体允许使用 Unicode 编码处理大字形集。 이러한 인코딩을 사용하면 글꼴 문자 모양 변형 외에도 광범위한 국가별 지원이 가능합니다.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 文本呈现由支持分辨率独立性的 Microsoft ClearType 子像素技术提供支持。 이 기능을 통해 가독성이 크게 향상되며, 모든 스크립트에 대해 고품질 잡지 스타일 문서를 지원하는 기능을 제공합니다.

<a name="intl_layout"></a>
### <a name="international-layout"></a>국가별 레이아웃
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 가로, 양방향 및 세로 레이아웃을 지원하는 매우 편리한 방법을 제공합니다. 在演示框架中，<xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性可用于定义布局。 흐름 방향 패턴은 다음과 같습니다.

- *LeftToRight* - 라틴어, 동아시아어 등을 위한 가로 레이아웃.

- *RightToLeft* - 아랍어, 히브리어 등을 위한 양방향.

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a>지역화 가능 애플리케이션 개발
 글로벌 사용을 위해 애플리케이션을 작성할 때 애플리케이션을 지역화해야 한다는 점에 유의해야 합니다. 다음 항목에서는 고려할 사항을 제공합니다.

<a name="mui"></a>
### <a name="multilingual-user-interface"></a>다국어 사용자 인터페이스
 多语言用户界面（MUI）是用于将用户界面从一种语言切换到另一种语言的 Microsoft 支持。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序使用程序集模型来支持 MUI。 한 애플리케이션에는 언어 중립 어셈블리 외에도 언어별 위성 리소스 어셈블리도 포함됩니다. 진입점은 기본 어셈블리에서 관리되는 .EXE입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 资源加载器利用框架的资源管理器来支持资源查找和回退。 여러 언어 위성 어셈블리는 동일한 기본 어셈블리와 작동합니다. 加载的资源程序集取决于当前线程的 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A>。

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a>지역화할 수 있는 사용자 인터페이스
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 来定义其 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용하면 개발자가 속성 및 논리 집합이 포함된 개체의 계층 구조를 지정할 수 있습니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 的主要用途是开发 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序，但它可用于指定任何公共语言运行时（CLR）对象的层次结构。 大多数开发人员都使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 来指定应用程序的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，并使用编程语言C# （例如）来响应用户交互。

 从资源的角度来看，旨在描述依赖于语言的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件是一个资源元素，因此，其最终分发格式必须可本地化以支持国际语言。 由于 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 无法处理事件，许多 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 应用程序包含执行此操作的代码块。 자세한 내용은 [XAML 개요 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)합니다. 将 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件标记为 XAML 的 BAML 形式后，代码会被去除并编译到不同的二进制文件中。 XAML 파일의 BAML 양식, 이미지 및 기타 형식의 관리 리소스 개체는 위성 리소스 어셈블리에 포함되어 다른 언어로 지역화되거나, 지역화가 필요하지 않은 경우 기본 어셈블리에 포함됩니다.

> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序支持所有 FrameworkCLR 资源，包括字符串表、图像等。

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a>지역화 가능 애플리케이션 빌드
 本地化意味着将 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 改编为不同的文化。 若要使 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的应用程序可本地化，开发人员需要将所有可本地化的资源生成到一个资源程序集中。 资源程序集本地化为不同的语言，代码隐藏使用资源管理 API 进行加载。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序所需的文件之一是项目文件（proj）。 애플리케이션에서 사용하는 모든 리소스는 프로젝트 파일에 포함되어야 합니다. .csprop 파일의 다음 예에서는 이 작업을 수행하는 방법을 보여줍니다.

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 若要在应用程序中使用资源，请实例化 <xref:System.Resources.ResourceManager> 并加载要使用的资源。 다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a>지역화된 애플리케이션에서 ClickOnce 사용
 ClickOnce 是 Visual Studio 2005 附带的一种新的 Windows 窗体部署技术。 애플리케이션 설치 및 웹 애플리케이션의 업그레이드를 수행할 수 있습니다. ClickOnce로 배포된 애플리케이션이 지역화되면 지역화된 문화권에서만 볼 수 있습니다. 例如，如果已部署的应用程序本地化为日语，则只能在日语版 Microsoft Windows 上查看该应用程序。 这会带来一个问题，因为它是日语用户运行英语版本的 Windows 的常见方案。

 이 문제는 중립 언어 대체 특성을 설정하여 해결합니다. 애플리케이션 개발자가 선택적으로 기본 어셈블리에서 리소스를 제거하고 특정 문화권에 해당하는 위성 어셈블리에서 해당 리소스를 찾을 수 있게 지정할 수 있습니다. 若要控制此过程，请使用 <xref:System.Resources.NeutralResourcesLanguageAttribute>。 <xref:System.Resources.NeutralResourcesLanguageAttribute> 类的构造函数具有两个签名，一个签名采用 <xref:System.Resources.UltimateResourceFallbackLocation> 参数来指定 <xref:System.Resources.ResourceManager> 应提取回退资源的位置：主程序集或附属程序集。 다음 예제에서는 이 특성을 사용하는 방법을 보여 줍니다. 对于最终回退位置，代码会使 <xref:System.Resources.ResourceManager> 在当前正在执行的程序集的目录的 "de" 子目录中查找资源。

```csharp
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a>另请参阅

- [WPF 전역화 및 지역화 개요](wpf-globalization-and-localization-overview.md)
