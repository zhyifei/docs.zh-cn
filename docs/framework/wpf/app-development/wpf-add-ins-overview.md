---
title: 外接程序概述
ms.date: 03/30/2017
helpviewer_keywords:
- add-ins and XAML browser applications [WPF]
- add-ins overview [WPF]
- add-ins [WPF], performance
- add-ins [WPF], benefits
- .NET Framework add-in model [WPF]
- add-ins [WPF], user interface
- add-ins and the user interface [WPF]
- add-ins [WPF], architecture
- add-ins [WPF], limitations
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
ms.openlocfilehash: 93904e308932ea41c736ca849ce0efb200502a7e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738938"
---
# <a name="wpf-add-ins-overview"></a>WPF 추가 기능 개요

<a name="Introduction"></a>.NET Framework 包含外接程序模型，开发人员可以使用该模型来创建支持外接程序扩展性的应用程序。 이 추가 기능 모델을 사용하면 애플리케이션 기능과 통합하고 이 기능을 확장하는 추가 기능을 만들 수 있습니다. 在某些情况下，应用程序还需要显示外接程序提供的用户界面。本主题演示 WPF 如何补充 .NET Framework 外接程序模型，以实现这些方案、其背后的体系结构、其优点和其局限性。

<a name="Requirements"></a>

## <a name="prerequisites"></a>先决条件

熟悉 .NET Framework 外接程序模型是必需的。 자세한 내용은 [추가 기능 및 확장성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))을 참조하세요.

<a name="AddInsOverview"></a>

## <a name="add-ins-overview"></a>추가 기능 개요

애플리케이션에서는 새 기능을 통합하기 위해 애플리케이션을 다시 컴파일하여 배포하는 복잡한 작업을 방지하도록 확장성 메커니즘을 구현하여 개발자(자사 및 타사)가 새 기능을 통합하는 다른 애플리케이션을 만들 수 있도록 합니다. 이러한 형식의 확장성을 지원하는 가장 일반적인 방법은 추가 기능(“추가 기능” 및 “플러그 인”이라고도 함)을 사용하는 것입니다. 추가 기능으로 확장성을 노출하는 실제 애플리케이션의 예에는 다음이 있습니다.

- Internet Explorer 추가 기능.

- Windows Media Player 플러그 인.

- Visual Studio 추가 기능.

예를 들어, Windows Media Player 추가 기능 모델을 사용하면 타사 개발자가 다양한 방식으로 Windows Media Player를 확장하는 “플러그 인”을 구현할 수 있습니다. 이러한 방식에는 Windows Media Player에서 기본적으로 지원하지 않는 미디어 형식(예: DVD, MP3)의 디코더와 인코더, 오디오 효과 및 스킨이 포함됩니다. 모든 추가 기능 모델에 공통인 동작과 엔터티가 여러 개 있지만, 각 추가 기능 모델은 애플리케이션에 고유한 기능을 노출하도록 빌드되어 있습니다.

일반적인 추가 기능 확장성 솔루션의 세 가지 기본 엔터티는 *계약*, *추가 기능* 및 *호스트 애플리케이션*입니다. 계약은 추가 기능이 다음 두 방법으로 호스트 애플리케이션과 통합하는 방법을 정의합니다.

- 추가 기능은 호스트 애플리케이션으로 구현된 기능과 통합됩니다.

- 호스트 애플리케이션에서 추가 기능과 통합될 기능을 노출합니다.

추가 기능을 사용하려면 호스트 애플리케이션에서 해당 기능을 찾아 런타임 시 로드해야 합니다. 따라서 추가 기능을 지원하는 애플리케이션에서는 다음과 같은 추가 작업을 담당합니다.

- **검색**: 호스트 애플리케이션에서 지원하는 계약을 준수하는 추가 기능 찾기.

- **활성화**: 추가 기능과의 통신을 로드, 실행 및 설정.

- **격리**: 애플리케이션 도메인 또는 프로세스를 사용하여 추가 기능의 잠재적인 보안 및 실행 문제로부터 애플리케이션을 보호하는 격리 경계 설정.

- **통신**: 추가 기능과 호스트 애플리케이션을 통해 메서드를 호출하고 데이터를 전달하여 격리 경계를 넘어 서로 통신할 수 있도록 허용.

- **수명 관리**: 예측 가능하고 정리된 방식으로 애플리케이션 도메인과 프로세스를 로드 및 언로드( [애플리케이션 도메인](../../app-domains/application-domains.md) 참조).

- **버전 관리**: 호스트 애플리케이션과 추가 기능 중 하나의 새 버전이 만들어진 경우에도 계속 통신 가능한지 확인.

근본적으로, 강력한 추가 기능 모델을 개발하는 것은 쉬운 작업이 아닙니다. 出于此原因，.NET Framework 提供了一个用于生成外接程序模型的基础结构。

> [!NOTE]
> 추가 기능에 대한 자세한 내용은 [추가 기능 및 확장성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))을 참조하세요.

<a name="NETFrameworkAddInModelOverview"></a>

## <a name="net-framework-add-in-model-overview"></a>.NET Framework 추가 기능 모델 개요

<xref:System.AddIn> 命名空间中的 .NET Framework 外接程序模型包含一组类型，这些类型旨在简化外接程序扩展性的开发。 .NET Framework 外接程序模型的基本单位为协定，该*协定*定义主机应用程序和外接程序之间的通信方式。 계약은 계약의 호스트-애플리케이션별 *보기*를 사용하여 호스트 애플리케이션에 노출됩니다. 마찬가지로 계약의 추가 기능별 *보기*가 추가 기능에 노출됩니다. 호스트 애플리케이션과 추가 기능이 계약의 각 보기 간에 통신할 수 있도록 *어댑터*가 사용됩니다. 계약, 보기 및 어댑터를 세그먼트라고 하며, 관련 세그먼트 집합이 *파이프라인*을 구성합니다. 管道是 .NET Framework 外接程序模型支持发现、激活、安全隔离、执行隔离（使用应用程序域和进程）、通信、生存期管理和版本控制的基础。

개발자는 이러한 지원을 모두 활용하여 호스트 애플리케이션의 기능과 통합하는 추가 기능을 빌드할 수 있습니다. 不过，某些方案需要宿主应用程序显示外接程序提供的用户界面。由于 .NET Framework 中的每个表示技术都有自己的模型来实现用户界面，.NET Framework 外接程序模型不支持任何特定的表示技术。 而 WPF 却扩展了 .NET Framework 外接程序模型，其中包含外接程序的 UI 支持。

<a name="WPFAddInModel"></a>

## <a name="wpf-add-ins"></a>WPF 추가 기능

WPF 与 .NET Framework 外接程序模型一起使用，可以解决需要宿主应用程序从外接程序显示用户界面的各种方案。具体而言，WPF 使用以下两种编程模型解决了这些方案：

1. **추가 기능이 UI를 반환함**. 外接程序通过方法调用向宿主应用程序返回一个 UI，由协定定义。 이 시나리오는 다음과 같은 경우에 사용됩니다.

    - 外接程序返回的 UI 的外观依赖于只在运行时存在的数据或条件，如动态生成的报表。

    - 外接程序提供的服务的 UI 不同于可以使用外接程序的宿主应用程序的 UI。

    - 外接程序主要为主机应用程序执行服务，并使用 UI 向主机应用程序报告状态。

2. **추가 기능이 UI임**. 外接程序是由协定定义的 UI。 이 시나리오는 다음과 같은 경우에 사용됩니다.

    - 추가 기능에서 광고와 같이 표시되고 있지 않은 서비스를 제공하지 않는 경우.

    - 外接程序提供的服务的 UI 对于所有可使用该外接程序的宿主应用程序（如计算器或颜色选取器）都是通用的。

这些方案要求可以在主机应用程序和外接程序应用程序域之间传递 UI 对象。 由于 .NET Framework 外接程序模型依赖于远程处理来在应用程序域之间进行通信，因此在它们之间传递的对象必须是可远程处理的。

원격으로 사용 가능한 개체는 다음 중 하나 이상을 수행하는 클래스의 인스턴스입니다.

- 派生自 <xref:System.MarshalByRefObject> 类。

- <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현합니다.

- 应用了 <xref:System.SerializableAttribute> 特性。

> [!NOTE]
> 有关创建可远程处理 .NET Framework 对象的详细信息，请参阅[使对象可远程](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))处理。

WPF UI 类型不能远程处理。 为了解决此问题，WPF 扩展了 .NET Framework 外接程序模型，以允许从主机应用程序显示外接程序创建的 WPF UI。 此支持由 WPF 通过两种类型提供： <xref:System.AddIn.Contract.INativeHandleContract> 接口和 <xref:System.AddIn.Pipeline.FrameworkElementAdapters> 类实现的两个静态方法： <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 和 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>。 상위 수준에서는 대략적으로 이러한 형식과 메서드가 다음과 같은 방식으로 사용됩니다.

1. WPF 要求外接程序提供的用户界面是直接或间接从 <xref:System.Windows.FrameworkElement>派生的类，如形状、控件、用户控件、布局面板和页面。

2. 无论协定声明在外接程序和宿主应用程序之间传递 UI，都必须将其声明为 <xref:System.AddIn.Contract.INativeHandleContract> （而非 <xref:System.Windows.FrameworkElement>）;<xref:System.AddIn.Contract.INativeHandleContract> 是可跨隔离边界传递的外接程序 UI 的可远程表示形式。

3. 在从外接程序的应用程序域传递之前，<xref:System.Windows.FrameworkElement> 通过调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>打包为 <xref:System.AddIn.Contract.INativeHandleContract>。

4. 将 <xref:System.AddIn.Contract.INativeHandleContract> 传递到主机应用程序的应用程序域之后，必须通过调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>将重新打包为 <xref:System.Windows.FrameworkElement>。

如何使用 <xref:System.AddIn.Contract.INativeHandleContract>、<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>和 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 取决于具体的方案。 다음 섹션에서는 각 프로그래밍 모델의 자세한 내용을 제공합니다.

<a name="ReturnUIFromAddInContract"></a>

## <a name="add-in-returns-a-user-interface"></a>추가 기능이 사용자 인터페이스를 반환함

若要使外接程序向宿主应用程序返回 UI，需要满足以下要求：

1. 必须创建宿主应用程序、外接程序和管道，如 .NET Framework[外接程序和扩展性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))文档中所述。

2. 协定必须实现 <xref:System.AddIn.Contract.IContract>，若要返回 UI，协定必须使用 <xref:System.AddIn.Contract.INativeHandleContract>类型的返回值声明方法。

3. 在外接程序和宿主应用程序之间传递的 UI 必须直接或间接从 <xref:System.Windows.FrameworkElement>派生。

4. 必须先将外接程序返回的 UI 从 <xref:System.Windows.FrameworkElement> 转换为 <xref:System.AddIn.Contract.INativeHandleContract>，然后才能跨越隔离边界。

5. 在跨越隔离边界之后，必须将返回的 UI 从 <xref:System.AddIn.Contract.INativeHandleContract> 转换为 <xref:System.Windows.FrameworkElement>。

6. 宿主应用程序显示返回的 <xref:System.Windows.FrameworkElement>。

有关演示如何实现返回 UI 的外接程序的示例，请参阅[创建返回 Ui 的外](how-to-create-an-add-in-that-returns-a-ui.md)接程序。

<a name="AddInIsAUI"></a>

## <a name="add-in-is-a-user-interface"></a>추가 기능이 사용자 인터페이스임

当外接程序为 UI 时，需要以下各项：

1. 必须创建宿主应用程序、外接程序和管道，如 .NET Framework[外接程序和扩展性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))文档中所述。

2. 外接程序的协定接口必须实现 <xref:System.AddIn.Contract.INativeHandleContract>。

3. 传递到主机应用程序的外接程序必须直接或间接从 <xref:System.Windows.FrameworkElement>派生。

4. 必须先将外接程序从 <xref:System.Windows.FrameworkElement> 转换为 <xref:System.AddIn.Contract.INativeHandleContract>，才能跨越隔离边界。

5. 跨隔离边界后，外接程序必须从 <xref:System.AddIn.Contract.INativeHandleContract> 转换为 <xref:System.Windows.FrameworkElement>。

6. 宿主应用程序显示返回的 <xref:System.Windows.FrameworkElement>。

有关演示如何实现作为 UI 的外接程序的示例，请参阅[创建作为 ui 的外](how-to-create-an-add-in-that-is-a-ui.md)接程序。

<a name="ReturningMultipleUIsFromAnAddIn"></a>

## <a name="returning-multiple-uis-from-an-add-in"></a>추가 기능에서 여러 UI 반환

外接程序通常为宿主应用程序提供多个用户界面以显示。 例如，请考虑作为 UI 的外接程序，该外接程序还向宿主应用程序提供状态信息。 이와 같은 추가 기능은 [추가 기능이 사용자 인터페이스를 반환함](#ReturnUIFromAddInContract) 및 [추가 기능이 사용자 인터페이스임](#AddInIsAUI) 모델의 기술을 조합하여 구현할 수 있습니다.

<a name="AddInsAndXBAPs"></a>

## <a name="add-ins-and-xaml-browser-applications"></a>추가 기능 및 XAML 브라우저 애플리케이션

지금까지의 예에서는 호스트 애플리케이션이 독립형 애플리케이션으로 설치되었습니다. 但 XAML 浏览器应用程序（Xbap）也可以承载外接程序，但有以下其他生成和实现要求：

- XBAP 应用程序清单必须经过专门配置，以将管道（文件夹和程序集）和外接程序程序集下载到客户端计算机上的 ClickOnce 应用程序缓存中，该文件位于 XBAP 所在的文件夹中。

- 用于发现和加载外接程序的 XBAP 代码必须使用 XBAP 的 ClickOnce 应用程序缓存作为管道和外接程序位置。

- 如果外接程序引用位于源站点的松散文件，XBAP 必须将外接程序加载到特殊安全上下文中;当由 Xbap 承载时，外接程序只能引用位于主机应用程序源站点的松散文件。

이러한 작업은 다음 하위 섹션에 자세히 설명되어 있습니다.

### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>ClickOnce 배포를 위한 파이프라인 및 추가 기능 구성

Xbap 将下载到并从 ClickOnce 部署缓存中的一个安全文件夹运行。 为了使 XBAP 承载外接程序，还必须将管道和外接程序程序集下载到 safe 文件夹中。 이 작업을 수행하려면 다운로드할 파이프라인과 추가 기능 어셈블리를 모두 포함하도록 애플리케이션 매니페스트를 구성해야 합니다. 尽管管道和外接程序程序集需要位于主机 XBAP 项目的根文件夹中，但对于 Visual Studio 检测管道程序集，但这在 Visual Studio 中最容易实现。

因此，第一步是通过设置每个管道程序集和外接程序程序集项目的生成输出，将管道和外接程序程序集生成到 XBAP 项目的根。 下表显示了管道程序集项目和外接程序程序集项目的生成输出路径，该程序集项目位于与宿主 XBAP 项目相同的解决方案和根文件夹中。

표 1: XBAP로 호스팅되는 파이프라인 어셈블리의 출력 경로 빌드

|파이프라인 어셈블리 프로젝트|빌드 출력 경로|
|-------------------------------|-----------------------|
|계약|`..\HostXBAP\Contracts\`|
|추가 기능 뷰|`..\HostXBAP\AddInViews\`|
|추가 기능측 어댑터|`..\HostXBAP\AddInSideAdapters\`|
|호스트측 어댑터|`..\HostXBAP\HostSideAdapters\`|
|추가 기능|`..\HostXBAP\AddIns\WPFAddIn1`|

下一步是通过执行以下操作，将管道程序集和外接程序程序集指定为 Visual Studio 中的 Xbap 内容文件：

1. 솔루션 탐색기에서 각 파이프라인 폴더를 마우스 오른쪽 단추로 클릭하고 **프로젝트에 포함**을 선택하여 프로젝트에 파이프라인 및 추가 기능 어셈블리 포함.

2. **속성** 창에서 각 파이프라인 어셈블리 및 추가 기능 어셈블리의 **빌드 작업**을 **콘텐츠**로 설정.

마지막 단계에서는 다운로드할 파이프라인 어셈블리 파일과 추가 기능 어셈블리 파일을 포함하도록 애플리케이션 매니페스트를 구성합니다. 文件应位于 XBAP 应用程序所占用的 ClickOnce 缓存中文件夹根目录的文件夹中。 通过执行以下操作，可以在 Visual Studio 中实现该配置：

1. 右键单击 XBAP 项目，单击 "**属性**"，单击 "**发布**"，然后单击 "**应用程序文件**" 按钮。

2. **애플리케이션 파일** 대화 상자에서 각 파이프라인과 추가 기능 DLL의 **게시 상태**를 **포함(자동)** 으로 설정하고 각 파이프라인과 추가 기능 DLL에 대해 **그룹 다운로드**을 **(필수)** 로 설정합니다.

### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>애플리케이션 기준 위치에서 파이프라인과 추가 기능 사용

为 ClickOnce 部署配置管道和外接程序时，会将它们下载到与 XBAP 相同的 ClickOnce 缓存文件夹中。 若要从 XBAP 使用管道和外接程序，XBAP 代码必须从应用程序基获取它们。 使用管道和外接程序的 .NET Framework 外接程序模型的各种类型和成员为此方案提供特殊支持。 首先，路径由 <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> 枚举值标识。 다음을 포함하는 파이프라인을 사용하기 위해 관련 추가 기능 멤버의 오버로드와 함께 이 값을 사용합니다.

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

### <a name="accessing-the-hosts-site-of-origin"></a>호스트의 원본 사이트에 액세스

추가 기능이 원본 사이트의 파일을 참조할 수 있도록 호스트 애플리케이션과 동일한 수준의 보안 격리로 추가 기능을 로드해야 합니다. 此安全级别由 <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> 枚举值标识，并在激活外接程序时传递到 <xref:System.AddIn.Hosting.AddInToken.Activate%2A> 方法。

<a name="WPFAddInModelArchitecture"></a>

## <a name="wpf-add-in-architecture"></a>WPF 추가 기능 아키텍처

正如我们所看到的，在最高级别，WPF 允许 .NET Framework 外接程序使用 <xref:System.AddIn.Contract.INativeHandleContract>、<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 和 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>实现直接或间接从 <xref:System.Windows.FrameworkElement>派生的用户界面。 结果是，主机应用程序返回了从主机应用程序中的 UI 显示的 <xref:System.Windows.FrameworkElement>。

对于简单的 UI 外接程序方案，这是开发人员所需的详细信息。 对于更复杂的方案（尤其是那些尝试使用其他 WPF 服务（如布局、资源和数据绑定）的方案，需要 WPF 如何扩展带有 UI 支持的 .NET Framework 外接程序模型，以了解其优势和限制。

从根本上讲，WPF 不会将 UI 从外接程序传递到主机应用程序;而是使用 WPF 互操作性为 UI 传递 Win32 窗口句柄。 因此，当外接程序中的 UI 被传递到主机应用程序时，将发生以下情况：

- 在外接程序端，WPF 会为将由主机应用程序显示的 UI 获取一个窗口句柄。 窗口句柄由从 <xref:System.Windows.Interop.HwndSource> 派生并实现 <xref:System.AddIn.Contract.INativeHandleContract>的内部 WPF 类封装。 此类的实例由 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 返回，并从外接程序的应用程序域封送到主机应用程序的应用程序域。

- 在宿主应用程序端，WPF 将 <xref:System.Windows.Interop.HwndSource> 作为从 <xref:System.Windows.Interop.HwndHost> 派生并使用 <xref:System.AddIn.Contract.INativeHandleContract>的内部 WPF 类重新打包。 此类的实例由 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 向宿主应用程序返回。

<xref:System.Windows.Interop.HwndHost> 存在，用于显示 WPF 用户界面中由窗口句柄标识的用户界面。 자세한 내용은 [WPF 및 Win32 상호 운용성](../advanced/wpf-and-win32-interoperation.md)을 참조하세요.

在 "摘要" 中，<xref:System.AddIn.Contract.INativeHandleContract>、<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>和 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 存在，以允许将 WPF UI 的窗口句柄从外接程序传递到主机应用程序，在该应用程序中，将由 <xref:System.Windows.Interop.HwndHost> 并显示宿主应用程序的 UI。

> [!NOTE]
> 由于宿主应用程序获取 <xref:System.Windows.Interop.HwndHost>，因此主机应用程序无法将 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 返回的对象转换为该外接程序（例如，<xref:System.Windows.Controls.UserControl>）所实现的类型。

<xref:System.Windows.Interop.HwndHost> 在本质上存在一些限制，这些限制会影响主机应用程序的使用方式。 不过，WPF 扩展了 <xref:System.Windows.Interop.HwndHost> 具有一些外接程序方案的功能。 이러한 이점과 한계는 아래에 설명되어 있습니다.

<a name="WPFAddInModelBenefits"></a>

## <a name="wpf-add-in-benefits"></a>WPF 추가 기능의 이점

因为 WPF 外接程序用户界面是使用派生自 <xref:System.Windows.Interop.HwndHost>的内部类从主机应用程序显示的，所以这些用户界面受与 WPF UI 服务有关的 <xref:System.Windows.Interop.HwndHost> 的功能的约束，如布局、呈现、数据绑定、样式、模板和资源。 不过，WPF 通过其他功能增强了其内部 <xref:System.Windows.Interop.HwndHost> 子类，其中包括：

- 在宿主应用程序的 UI 和外接程序的 UI 之间进行 tab 键切换。 请注意，"外接程序是 UI" 编程模型要求外接程序端适配器覆盖 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 来启用 tab 键切换，无论外接程序是完全信任的还是部分信任的。

- 满足从主机应用程序用户界面中显示的外接程序用户界面的辅助功能要求。

- 允许 WPF 应用程序在多个应用程序域方案中安全运行。

- 当外接程序以安全隔离（即部分信任的安全沙盒）运行时，防止非法访问外接程序 UI 窗口句柄。 调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 可确保安全：

  - 对于 "外接程序返回 UI" 编程模型，跨隔离边界传递外接程序 UI 的窗口句柄的唯一方法是调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>。

  - 对于 "外接程序是 UI" 编程模型，需要重写外接程序端适配器上的 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>，并调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> （如前面的示例中所示），就像从宿主端适配器调用外接程序端适配器的 `QueryContract` 实现一样。

- 여러 애플리케이션 도메인 실행 보호 제공. 애플리케이션 도메인의 한계로 인해 추가 기능 애플리케이션 도메인에서 throw된 처리되지 않은 예외가 발생하면 격리 경계가 있는 경우에도 전체 애플리케이션이 중단됩니다. 不过，WPF 和 .NET Framework 外接程序模型提供一种简单的方法来解决此问题并提高应用程序的稳定性。 如果主机应用程序是 WPF 应用程序，则显示 UI 的 WPF 外接程序会为运行应用程序域的线程创建 <xref:System.Windows.Threading.Dispatcher>。 您可以通过处理 WPF 外接程序的 <xref:System.Windows.Threading.Dispatcher>的 <xref:System.Windows.Threading.Dispatcher.UnhandledException> 事件来检测应用程序域中发生的所有未处理的异常。 可以从 <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> 属性获取 <xref:System.Windows.Threading.Dispatcher>。

<a name="WPFAddInModelLimitations"></a>

## <a name="wpf-add-in-limitations"></a>WPF 추가 기능 한계

除了 WPF 添加到 <xref:System.Windows.Interop.HwndSource>、<xref:System.Windows.Interop.HwndHost>和窗口句柄提供的默认行为以外，还存在从主机应用程序显示的外接程序用户界面的限制：

- 宿主应用程序显示的外接程序用户界面不遵守主机应用程序的剪辑行为。

- 상호 운용성 시나리오의 *에어스페이스* 개념도 추가 기능에 적용됩니다([기술 영역 개요](../advanced/technology-regions-overview.md) 참조).

- 宿主应用程序的 UI 服务（如资源继承、数据绑定和命令）不会自动提供给外接程序用户界面。 추가 기능에 이러한 서비스를 제공하려면 파이프라인을 업데이트해야 합니다.

- 外接程序 UI 不能旋转、缩放、倾斜或以其他方式受转换的影响（请参阅[转换概述](../graphics-multimedia/transforms-overview.md)）。

- 由 <xref:System.Drawing> 命名空间的绘图操作呈现的外接程序用户界面内的内容可以包含 alpha 混合。 但是，加载项 UI 和包含它的主机应用程序 UI 必须是100% 不透明;换言之，两者的 `Opacity` 属性必须设置为1。

- 如果宿主应用程序中包含外接程序 UI 的窗口的 <xref:System.Windows.Window.AllowsTransparency%2A> 属性设置为 `true`，则外接程序将不可见。 即使外接程序 UI 为100% 不透明（即，`Opacity` 属性的值为1），也是如此。

- 外接程序 UI 必须出现在同一顶级窗口中的其他 WPF 元素之上。

- 外接程序 UI 的任何部分都无法使用 <xref:System.Windows.Media.VisualBrush>进行呈现。 相反，外接程序可能会拍摄生成的 UI 的快照，以创建一个可以使用协定所定义的方法传递到主机应用程序的位图。

- 无法从外接程序 UI 中的 <xref:System.Windows.Controls.MediaElement> 播放媒体文件。

- 宿主应用程序既不会接收也不会引发为外接程序 UI 生成的鼠标事件，主机应用程序 UI 的 `IsMouseOver` 属性的值为 `false`。

- 当焦点在外接程序 UI 中的控件之间移动时，主机应用程序既不会接收 `GotFocus` 事件，也不会引发 `LostFocus` 事件。

- 在打印时，包含外接程序 UI 的主机应用程序部分显示为白色。

- 如果主机应用程序继续执行，则在卸载 owner 外接程序之前，必须手动关闭外接程序 UI 创建的所有调度程序（请参阅 <xref:System.Windows.Threading.Dispatcher>）。 协定可以实现一些方法，这些方法允许主机应用程序在外接程序卸载之前通知外接程序，从而允许外接程序 UI 关闭其调度程序。

- 如果外接程序 UI 是 <xref:System.Windows.Controls.InkCanvas> 或包含 <xref:System.Windows.Controls.InkCanvas>，则无法卸载外接程序。

<a name="PerformanceOptimization"></a>

## <a name="performance-optimization"></a>성능 최적화

默认情况下，当使用多个应用程序域时，每个应用程序所需的各种 .NET Framework 程序集都将加载到该应用程序的域中。 결과적으로 새 애플리케이션 도메인을 만들고 이 도메인의 애플리케이션을 시작하는 데 필요한 시간이 성능에 영향을 미칠 수 있습니다. 不过，通过指示应用程序在已加载的应用程序域之间共享程序集，.NET Framework 提供了一种减少开始时间的方法。 为此，请使用 <xref:System.LoaderOptimizationAttribute> 特性，该特性必须应用于入口点方法（`Main`）。 이 경우, 애플리케이션 정의를 구현하는 코드만 사용해야 합니다([애플리케이션 관리 개요](application-management-overview.md) 참조).

## <a name="see-also"></a>另请参阅

- <xref:System.LoaderOptimizationAttribute>
- [추가 기능 및 확장성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [애플리케이션 도메인](../../app-domains/application-domains.md)
- [.NET Framework 远程处理概述](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kwdt6w2k(v=vs.100))
- [使对象可远程处理](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))
- [방법 항목](how-to-topics.md)
