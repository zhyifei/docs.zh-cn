---
title: 문서
ms.date: 03/30/2017
helpviewer_keywords:
- documents [WPF], packaging
- documents [WPF], text layout
- documents [WPF], XPS
- 'XPS documents [WPF], , '
- documents [WPF], controls
- documents [WPF], types of
- documents [WPF], browser-viewable
ms.assetid: 6e8db7bc-050a-4070-aa72-bb8c46e87ff8
ms.openlocfilehash: eccb333b8e9a71ea30454f8bdf9fd2bf6dc90b9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737969"
---
# <a name="documents-in-wpf"></a>WPF의 문서
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供各种文档功能，使创建的高保真内容更易于访问和读取，而不是在以前的 Windows 版本中使用。 고급 기능 및 품질 외에도 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 문서 표시, 패키징 및 보안을 위한 통합 서비스도 제공합니다. 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 문서 형식 및 문서 패키징을 소개합니다.  

<a name="types_of_documents"></a>   
## <a name="types-of-documents"></a>문서 종류  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 용도에 따라 문서를 두 개의 광범위한 범주로 구분합니다. 이러한 문서 범주를 “고정 문서”와 “유동 문서”라고 합니다.  
  
 固定文档适用于需要精确的 "所见即所得" （WYSIWYG）表示形式的应用程序，而与所用的显示器或打印机硬件无关。 일반적으로 고정 문서는 데스크톱 출판, 워드 프로세싱 및 양식 레이아웃에 사용되며, 이 경우 원래 페이지 디자인을 고수하는 것이 중요합니다. 고정 문서에서는 사용 중인 디스플레이나 인쇄 디바이스와 무관하게 콘텐츠 요소의 정확한 위치를 레이아웃의 일부로 유지합니다. 예를 들어, 96dpi 디스플레이에 보이는 고정 문서 페이지는 600dpi 레이저 프린터로 출력할 때와 4800dpi 사진 식자기로 출력할 때 모두 똑같이 표시됩니다. 어느 경우에든 페이지 레이아웃은 동일하며, 문서 품질은 각 디바이스의 기능에 따라 최대화됩니다.  
  
 이에 비해 유동 문서는 보기와 가독성을 최적화하도록 설계되어 있으며, 문서 이용 시 용이한 가독성이 주된 요인인 시나리오에서 최적으로 활용할 수 있습니다. 유동 문서는 미리 정의된 하나의 레이아웃으로 설정되는 것이 아니라, 창 크기, 디바이스 해상도 및 선택적 사용자 기본 설정 등의 런타임 변수에 따라 동적으로 콘텐츠를 조정하고 리플로우합니다. 웹 페이지는 페이지 콘텐츠를 현재 창에 맞게 동적으로 형식화하는 유동 문서의 간단한 예입니다. 유동 문서는 런타임 환경을 기반으로 사용자의 보기 및 읽기 환경을 최적화합니다. 예를 들어, 동일한 유동 문서가 고해상도 19인치 디스플레이나 소형 2x3인치 PDA 화면에서 최적의 가독성을 제공하기 위해 동적으로 서식을 다시 지정합니다. 또한 유동 문서에는 검색, 가독성을 최적화하는 보기 모드 및 글꼴의 모양과 크기를 변경하는 기능 등의 여러 기본 제공 기능이 포함되어 있습니다.  플로우 문서에 대한 그림, 예제 및 자세한 정보는 [유동 문서 개요](flow-document-overview.md)를 참조하세요.  
  
<a name="document_viewer"></a>   
## <a name="document-controls-and-text-layout"></a>문서 컨트롤 및 텍스트 레이아웃  
 .NET Framework 提供了一组预建的控件，这些控件可简化在应用程序中使用固定文档、流文档和常规文本。  使用 <xref:System.Windows.Controls.DocumentViewer> 控件支持显示固定文档内容。  流文档内容的显示由三个不同的控件支持： <xref:System.Windows.Controls.FlowDocumentReader>、<xref:System.Windows.Controls.FlowDocumentPageViewer>和映射到不同用户方案的 <xref:System.Windows.Controls.FlowDocumentScrollViewer> （请参阅以下部分）。  기타 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서는 일반 텍스트 사용을 지원하는 간소화된 레이아웃을 제공합니다(아래 [사용자 인터페이스의 텍스트](#text_in_the_user_interface) 참조).  
  
### <a name="fixed-document-control---documentviewer"></a>고정 문서 컨트롤 - DocumentViewer  
 <xref:System.Windows.Controls.DocumentViewer> 控件旨在显示 <xref:System.Windows.Documents.FixedDocument> 内容。 <xref:System.Windows.Controls.DocumentViewer> 控件提供了一个直观的用户界面，该界面为常见操作（包括打印输出、复制到剪贴板、缩放和文本搜索功能）提供内置支持。 컨트롤에서는 친숙한 스크롤링 메커니즘을 통해 콘텐츠 페이지에 액세스하는 권한을 제공합니다. 与所有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 控件一样，<xref:System.Windows.Controls.DocumentViewer> 支持完整或部分 restyling，这使得控件能够直观地集成到几乎任何应用程序或环境中。  
  
 <xref:System.Windows.Controls.DocumentViewer> 旨在以只读方式显示内容;编辑或修改内容不可用，因此不受支持。  
  
<a name="flow_document"></a>   
### <a name="flow-document-controls"></a>유동 문서 컨트롤  

> [!NOTE]
> 有关流文档功能以及如何创建它们的详细信息，请参阅[流文档概述](flow-document-overview.md)。  
  
 以下三个控件支持流文档内容的显示： <xref:System.Windows.Controls.FlowDocumentReader>、<xref:System.Windows.Controls.FlowDocumentPageViewer>和 <xref:System.Windows.Controls.FlowDocumentScrollViewer>。  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> 包括允许用户在各种查看模式之间进行动态选择的功能，包括单页（一次一页）查看模式、一次一页（书籍阅读格式）查看模式和连续滚动（无限）查看模式。  有关这些查看模式的详细信息，请参阅 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>。  如果不需要在不同查看模式之间动态切换的功能，请 <xref:System.Windows.Controls.FlowDocumentPageViewer> 和 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 提供在特定查看模式下固定的轻型流内容查看器。  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer 및 FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> 以一次一页的查看模式显示内容，而 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 以连续滚动模式显示内容。  <xref:System.Windows.Controls.FlowDocumentPageViewer> 和 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 都固定到特定的查看模式。 与 <xref:System.Windows.Controls.FlowDocumentReader>比较，其中包括允许用户在各种查看模式（由 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> 枚举提供）之间进行动态选择的功能，成本比 <xref:System.Windows.Controls.FlowDocumentPageViewer> 或 <xref:System.Windows.Controls.FlowDocumentScrollViewer>更多的资源。  
  
 기본적으로 세로 스크롤 막대는 항상 표시되며 가로 스크롤 막대는 필요한 경우 표시됩니다. <xref:System.Windows.Controls.FlowDocumentScrollViewer> 的默认 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 不包括工具栏;但 <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> 属性可用于启用内置工具栏。  
  
<a name="text_in_the_user_interface"></a>   
### <a name="text-in-the-user-interface"></a>사용자 인터페이스의 텍스트  
 문서에 텍스트를 추가하는 외에도 양식과 같은 애플리케이션 UI에서 명확하게 텍스트를 사용할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 화면에 텍스트를 그리는 데 사용하는 여러 컨트롤이 포함되어 있습니다. 각 컨트롤은 다른 시나리오를 대상으로 하며 고유 기능 및 제한 사항 목록을 가지고 있습니다. 通常情况下，当需要有限的文本支持时，应使用 <xref:System.Windows.Controls.TextBlock> 元素，例如 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]中的 brief 句子。 需要最少文本支持时，可以使用 <xref:System.Windows.Controls.Label>。 자세한 내용은 [TextBlock 개요](../controls/textblock-overview.md)를 참조하세요.  
  
<a name="packaging"></a>   
## <a name="document-packaging"></a>문서 패키징  
 <xref:System.IO.Packaging> Api 提供了一种高效的方法，可用于将应用程序数据、文档内容和相关资源组织到一个易于访问、可移植且易于分发的容器中。 ZIP 文件是支持将多个对象作为单个单元进行保存的 <xref:System.IO.Packaging.Package> 类型的示例。 打包 Api 提供了一个默认的 <xref:System.IO.Packaging.ZipPackage> 实现，它使用 XML 和 ZIP 文件体系结构的开放打包约定标准。 使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 打包 Api，可以轻松地创建包，并存储和访问这些包中的对象。 存储在 <xref:System.IO.Packaging.Package> 中的对象称为 <xref:System.IO.Packaging.PackagePart> （"part"）。 패키지에는 파트의 작성기를 식별하고 패키지의 콘텐츠가 수정되지 않았는지 유효성을 검사하는 데 사용할 수 있는 서명된 디지털 인증서도 포함될 수 있습니다.  包还包括一项 <xref:System.IO.Packaging.PackageRelationship> 功能，该功能允许将附加信息添加到包或与特定部分关联，而无需实际修改现有部件的内容。  包服务还支持 Microsoft Windows Rights Management （RM）。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패키지 아키텍처는 다음과 같은 여러 주요 기술의 기반 역할을 합니다.  
  
- 符合 XML 纸张规范（XPS）的 XPS 文档。  
  
- Microsoft Office “12” Open XML 형식 문서(.docx).  
  
- 고유 애플리케이션 디자인에 맞는 사용자 지정 스토리지 형식.  
  
 根据打包 Api，<xref:System.Windows.Xps.Packaging.XpsDocument> 专门为存储 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 固定内容文档而设计。 <xref:System.Windows.Xps.Packaging.XpsDocument> 是一种自包含文档，可在查看器中打开、显示在 <xref:System.Windows.Controls.DocumentViewer> 控件中、路由到打印假脱机或直接输出到 XPS 兼容的打印机。  
  
 以下各节提供了有关 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供的 <xref:System.IO.Packaging.Package> 和 <xref:System.Windows.Xps.Packaging.XpsDocument> Api 的其他信息。  
  
<a name="packages"></a>   
### <a name="package-components"></a>패키지 구성 요소  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패키징 API를 사용하면 애플리케이션 데이터와 문서를 이식 가능한 단일 단위로 구성할 수 있습니다. ZIP 파일은 가장 일반적인 패키지 유형 중 하나이고, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 제공하는 기본 패키지 유형입니다.  <xref:System.IO.Packaging.Package> 本身是一个抽象类，其中使用开放式标准 XML 和 ZIP 文件体系结构来实现 <xref:System.IO.Packaging.ZipPackage>。  默认情况下，<xref:System.IO.Packaging.Package.Open%2A> 方法使用 <xref:System.IO.Packaging.ZipPackage> 创建和使用 ZIP 文件。 패키지에는 다음과 같은 세 가지 기본 유형의 항목이 포함될 수 있습니다.  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|애플리케이션 콘텐츠, 데이터, 문서 및 리소스 파일.|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|ID, 인증 및 유효성 검사용 [X.509 인증서].|  
|<xref:System.IO.Packaging.PackageRelationship>|패키지 또는 특정 파트와 관련된 추가 정보.|  
  
<a name="PackageParts"></a>   
#### <a name="packageparts"></a>PackageParts  
 <xref:System.IO.Packaging.PackagePart> （"part"）是一个抽象类，它引用存储在 <xref:System.IO.Packaging.Package>中的对象。 ZIP 파일에서 패키지 파트는 ZIP 파일에 저장된 개별 파일에 해당합니다.  <xref:System.IO.Packaging.ZipPackagePart> 提供 <xref:System.IO.Packaging.ZipPackage>中存储的可序列化对象的默认实现。  파일 시스템과 마찬가지로 패키지에 포함된 파트는 계층 구조 디렉터리 또는 “폴더 스타일” 조직에 저장됩니다.  使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 打包 Api，应用程序可以使用单个 ZIP 文件容器来编写、存储和读取多个 <xref:System.IO.Packaging.PackagePart> 对象。  
  
<a name="PackageDigitalSignatures"></a>   
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignatures  
 为安全，<xref:System.IO.Packaging.PackageDigitalSignature> （"数字签名"）可与包中的部件相关联。 <xref:System.IO.Packaging.PackageDigitalSignature> 包含了一个提供以下两个功能的 [509]：  
  
1. 파트의 작성기를 식별하고 인증합니다.  
  
2. 파트가 수정되지 않았는지 유효성을 검사합니다.  
  
 디지털 시그니처는 파트를 수정하지 못하게 하지는 않지만, 파트를 임의 방식으로 변경하면 디지털 시그니처의 유효성 검사 확인이 실패합니다. 그러면 애플리케이션에서 파트 열기를 차단하거나 사용자에게 파트가 수정되어 안전하지 않음을 알리는 등의 적절한 조치를 수행할 수 있습니다.  
  
<a name="PackageRelationships"></a>   
#### <a name="packagerelationships"></a>PackageRelationships  
 <xref:System.IO.Packaging.PackageRelationship> （"关系"）提供了一种机制，用于将附加信息与包或包中的部件相关联。 관계는 실제 파트 콘텐츠를 수정하지 않고 파트와 추가 정보를 연결할 수 있는 패키지 수준 기능입니다. 대부분의 경우 새 데이터를 파트 콘텐츠에 직접 삽입하는 것은 실용적이지 않습니다.  
  
- 파트의 실제 형식 및 해당 콘텐츠 스키마는 알 수 없습니다.  
  
- 알려진 경우에도 콘텐츠 스키마에서는 새 정보를 추가하는 방법을 제공하지 않습니다.  
  
- 파트는 디지털 방식으로 서명되거나 암호화될 수 있으며, 수정은 불가능합니다.  
  
 패키지 관계에서는 자세한 정보를 추가하여 개별 파트 또는 전체 패키지와 연결하는 검색 가능한 방법을 제공합니다. 패키지 관계는 다음 두 개의 주요 기능에 사용합니다.  
  
1. 파트 간 종속성 관계 정의.  
  
2. 메모 또는 파트와 관련된 다른 데이터를 추가하는 정보 관계 정의.  
  
 <xref:System.IO.Packaging.PackageRelationship> 提供了一种快速、可发现的方式来定义依赖项，并添加与包或包的一部分相关的其他信息。  
  
<a name="Dependency_Relationships"></a>   
##### <a name="dependency-relationships"></a>종속성 관계  
 종속성 관계는 한 파트가 다른 파트에 지정하는 종속성을 설명하는 데 사용됩니다. 예를 들어, 패키지에는 하나 이상의 \<img> 이미지 태그를 포함하는 HTML 파트가 포함될 수 있습니다. 이미지 태그는 패키지 내부의 다른 파트 또는 패키지 외부의 다른 파트(예: 인터넷을 통해 액세스 가능)로 있는 이미지를 참조합니다. 创建与 HTML 文件相关联的 <xref:System.IO.Packaging.PackageRelationship>，可以快速轻松地发现和访问从属资源。 브라우저 또는 뷰어 애플리케이션에서 파트 관계에 직접 액세스하고 스키마를 모르거나 문서를 구문 분석하지 않아도 종속 리소스의 어셈블링을 즉시 시작할 수 있습니다.  
  
<a name="Information_Relationships"></a>   
##### <a name="information-relationships"></a>정보 관계  
 与注释或批注类似，<xref:System.IO.Packaging.PackageRelationship> 还可用于存储其他类型的信息，以与部件关联，而无需实际修改部件内容本身。  
  
<a name="XPS_Documents"></a>   
## <a name="xps-documents"></a>XPS 문서  
 XML 纸张规范（XPS）文档是一个包，其中包含一个或多个固定文档以及呈现所需的所有资源和信息。  XPS 也是本机 Windows Vista 打印假脱机文件格式。  <xref:System.Windows.Xps.Packaging.XpsDocument> 存储在标准 ZIP 数据集中，可以包含 XML 和二进制组件（如图像和字体文件）的组合。 [PackageRelationships](#PackageRelationships)는 문서를 완전하게 렌더링하는 데 필요한 리소스와 콘텐츠 사이의 종속성을 정의하는 데 사용합니다.  <xref:System.Windows.Xps.Packaging.XpsDocument> 的设计提供了支持多种用途的单个高保真文档解决方案：  
  
- 고정 문서 콘텐츠와 리소스를 읽고 쓰며, 이식 가능하고 배포하기 쉬운 단일 파일로 저장.  
  
- 显示包含 XPS 查看器应用程序的文档。  
  
- 以 Windows Vista 的本机打印后台输出格式输出文档。  
  
- 将文档直接路由到与 XPS 兼容的打印机。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Documents.FixedDocument>
- <xref:System.Windows.Documents.FlowDocument>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.IO.Packaging.ZipPackage>
- <xref:System.IO.Packaging.ZipPackagePart>
- <xref:System.IO.Packaging.PackageRelationship>
- <xref:System.Windows.Controls.DocumentViewer>
- [Text](optimizing-performance-text.md)
- [유동 문서 개요](flow-document-overview.md)
- [인쇄 개요](printing-overview.md)
- [문서 serialization 및 스토리지](document-serialization-and-storage.md)
