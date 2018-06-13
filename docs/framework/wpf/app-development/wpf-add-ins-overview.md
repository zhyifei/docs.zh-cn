---
title: WPF 外接程序概述
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
ms.openlocfilehash: 942f5706a83a9f9e9cd969701ed5625c57b76f83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557857"
---
# <a name="wpf-add-ins-overview"></a>WPF 外接程序概述
<a name="Introduction"></a> [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 提供了一个外接程序模型，开发人员可以用它来创建支持外接程序扩展性的应用程序。 借助此外接程序模型，可以创建与应用程序功能集成并进行扩展的外接程序。 在某些情况下，应用程序还需要显示外接程序所提供的 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]。本主题演示 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 如何扩展 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型来实现这些方案，并演示它的体系结构、优点及局限性。  
  

  
<a name="Requirements"></a>   
## <a name="prerequisites"></a>系统必备  
 要求熟悉 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型。 有关详细信息，请参阅[外接程序和扩展性](../../../../docs/framework/add-ins/index.md)。  
  
<a name="AddInsOverview"></a>   
## <a name="add-ins-overview"></a>外接程序概述  
 为了需要对应用程序重新编译和重新部署才能引入新功能这一复杂过程，应用程序实现了扩展机制，使开发者（包括第一方和第三方）能够创建与应用程序集成的其他应用程序。 支持此扩展性类型的最常见方式是，使用外接程序（也称为“加载项”和“插件”）。 通过外接程序公开扩展性的实际应用程序示例包括：  
  
-   Internet Explorer 加载项。  
  
-   Windows Media Player 插件。  
  
-   Visual Studio 外接程序。  
  
 例如，通过 Windows Media Player 外接程序模型，第三方开发人员可以实现“插件”，从而以各种方式对 Windows Media Player 进行扩展，包括为 Windows Media Player 本身不支持的媒体格式（例如 DVD、MP3）创建解码器和编码器，创建音频效果和外观。 尽管有一些实体和行为是所有外接程序模型共有的，但会生成每个外接程序模型以公开某个应用程序的特有功能。  
  
 典型外接程序扩展性解决方案的三大实体是“协定”、“外接程序”和“主机应用程序”。 协定会定义外接程序与主机应用程序之间的两种集成方式：  
  
-   外接程序集成主机应用程序所实现的功能。  
  
-   主机应用程序公开供外接程序集成的功能。  
  
 为了使外接程序能发挥作用，主机应用程序需要在运行时找到它们并进行加载。 因此，支持外接程序的应用程序需要承担以下附加的职责：  
  
-   **发现**：查找遵循主机应用程序所支持的协定的外接程序。  
  
-   **激活**：加载和运行外接程序并与它们建立通信。  
  
-   **隔离**：使用应用程序域或进程建立隔离边界，以保护应用程序不受外接程序潜在安全问题和执行问题的影响。  
  
-   **通信**：通过调用方法和传递数据，允许外接程序和主机应用程序跨过隔离边界相互通信。  
  
-   **生存期管理**：通过可预测的干净方式来加载和卸载应用程序域和进程（请参阅[应用程序域](../../../../docs/framework/app-domains/application-domains.md)）。  
  
-   **版本管理**：确保在创建主机应用程序或外接程序的新版本后，它们仍可进行通信。  
  
 总之，开发一个可靠的外接程序模型不是一项简单的任务。 为此，[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 提供了一种用于生成外接程序模型的基础结构。  
  
> [!NOTE]
>  有关外接程序的更多详细信息，请参阅[外接程序和扩展性](../../../../docs/framework/add-ins/index.md)。  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## <a name="net-framework-add-in-model-overview"></a>.NET Framework 外接程序模型概述  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型，在中找到<xref:System.AddIn>命名空间，包含一组旨在简化的开发外接程序扩展的类型。 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型的基本单元是“协定”，用于定义主机应用程序与外接程序之间的通信方式。 会使用特定于主机应用程序的协定*视图*向主机应用程序公开协定。 同样，向外接程序公开特定于外接程序的协定*视图*。 使用*适配器*，主机应用程序和外接程序可以在它们各自的协定视图之间进行通信。 协定、视图和适配器称为管道段，一组相关的管道段组成一条*管道*。 将管道作为基础，以便 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型可以支持发现、激活、安全隔离、执行隔离（同时使用应用程序域和进程）、通信、生存期管理和版本管理。  
  
 所有这些支持使得开发人员能够生成与主机应用程序的功能相集成的外接程序。 但在某些情况下，主机应用程序需要显示外接程序所提供的 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]。由于 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 中的每种显示技术都有自己的 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 实现模型，因此 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型不支持任何特定的显示技术。 而由 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 对 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型进行扩展，来支持外接程序的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
<a name="WPFAddInModel"></a>   
## <a name="wpf-add-ins"></a>WPF 外接程序  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 与 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型相结合，能够处理各种要求主机应用程序显示外接程序 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 的方案。特别是，这些方案由 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 使用以下两种编程模型进行处理：  
  
1.  **外接程序返回 UI**。 外接程序按照协定的定义，通过方法调用将 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 返回给主机应用程序。 此方案可用于以下情况：  
  
    -   外接程序返回的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的外观依赖于仅在运行时存在的数据或条件，例如动态生成的报告。  
  
    -   外接程序提供的服务 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 不同于可以使用该外接程序的主机应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
    -   外接程序主要执行主机应用程序的某项服务，并通过 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 向主机应用程序报告状态。  
  
2.  **外接程序为 UI**。 正如协定所定义的那样，外接程序为 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 此方案可用于以下情况：  
  
    -   外接程序提供的服务都需要显示，例如广告。  
  
    -   外接程序提供的服务 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 为可以使用该外接程序的所有主机应用程序（如计算器或颜色选取器）所共用。  
  
 这些方案要求 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 对象可以在主机应用程序和外接应用程序域之间传递。 由于 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型依赖于远程处理来在不同的应用程序域之间进行通信，因此在它们之间传递的对象必须可远程处理。  
  
 可远程处理的对象是某个类的实例，并执行以下一个或多个任务：  
  
-   派生自<xref:System.MarshalByRefObject>类。  
  
-   实现 <xref:System.Runtime.Serialization.ISerializable> 接口。  
  
-   具有<xref:System.SerializableAttribute>应用的属性。  
  
> [!NOTE]
>  有关创建可远程处理的 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 对象的详细信息，请参阅[使对象可远程处理](http://msdn.microsoft.com/library/01197253-3f13-43b7-894d-9683e431192a)。  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 类型不可远程处理。 为解决此问题，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 扩展了 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型，允许从主机应用程序显示外接程序所创建的 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 通过提供此支持[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]通过两种类型：<xref:System.AddIn.Contract.INativeHandleContract>接口和实现的两个静态方法<xref:System.AddIn.Pipeline.FrameworkElementAdapters>类：<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>和<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>。 从较高层面来看，这些类型和方法按以下方式使用：  
  
1.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 要求[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]由外接程序是从直接或间接派生的类<xref:System.Windows.FrameworkElement>，如形状、 控件、 用户控件、 布局面板和页。  
  
2.  只要协定声明，将外接程序与主机应用程序之间传递 UI，必须将它声明为<xref:System.AddIn.Contract.INativeHandleContract>(不<xref:System.Windows.FrameworkElement>);<xref:System.AddIn.Contract.INativeHandleContract>是外接程序的远程操作表示[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]可以跨隔离边界传递。  
  
3.  然后再从外接程序的应用程序域中，传递<xref:System.Windows.FrameworkElement>打包为<xref:System.AddIn.Contract.INativeHandleContract>通过调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>。  
  
4.  传递到主机应用程序的应用程序域后<xref:System.AddIn.Contract.INativeHandleContract>必须重新打包为<xref:System.Windows.FrameworkElement>通过调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>。  
  
 如何<xref:System.AddIn.Contract.INativeHandleContract>， <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>，和<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>使用取决于特定方案。 下面几节介绍每个编程模型的详细信息。  
  
<a name="ReturnUIFromAddInContract"></a>   
## <a name="add-in-returns-a-user-interface"></a>外接程序返回用户界面  
 若要使外接程序向主机应用程序返回 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，需要满足以下要求：  
  
1.  必须按照 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [外接程序和扩展性](../../../../docs/framework/add-ins/index.md)文档的描述，创建主机应用程序、外接程序和管道。  
  
2.  协定必须实现<xref:System.AddIn.Contract.IContract>和，以返回[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，协定必须声明具有类型的返回值的方法<xref:System.AddIn.Contract.INativeHandleContract>。  
  
3.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]传递外接程序和主机之间应用程序必须直接或间接派生自<xref:System.Windows.FrameworkElement>。  
  
4.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]返回的外接程序必须将从转换<xref:System.Windows.FrameworkElement>到<xref:System.AddIn.Contract.INativeHandleContract>在越过隔离边界之前。  
  
5.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]返回必须从转换<xref:System.AddIn.Contract.INativeHandleContract>到<xref:System.Windows.FrameworkElement>越过隔离边界之后。  
  
6.  主机应用程序将显示返回<xref:System.Windows.FrameworkElement>。  
  
 有关演示如何实现返回 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的外接程序的示例，请参阅[创建返回 UI 的外接程序](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)。  
  
<a name="AddInIsAUI"></a>   
## <a name="add-in-is-a-user-interface"></a>外接程序为用户界面  
 当外接程序为 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 时，必须满足以下要求：  
  
1.  必须按照 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [外接程序和扩展性](../../../../docs/framework/add-ins/index.md)文档的描述，创建主机应用程序、外接程序和管道。  
  
2.  外接程序的协定接口必须实现<xref:System.AddIn.Contract.INativeHandleContract>。  
  
3.  传递给主机应用程序的外接程序必须直接或间接派生自<xref:System.Windows.FrameworkElement>。  
  
4.  外接程序必须将从转换<xref:System.Windows.FrameworkElement>到<xref:System.AddIn.Contract.INativeHandleContract>在越过隔离边界之前。  
  
5.  外接程序必须将从转换<xref:System.AddIn.Contract.INativeHandleContract>到<xref:System.Windows.FrameworkElement>越过隔离边界之后。  
  
6.  主机应用程序将显示返回<xref:System.Windows.FrameworkElement>。  
  
 有关演示如何实现作为 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的外接程序的示例，请参阅[创建作为 UI 的外接程序](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md)。  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## <a name="returning-multiple-uis-from-an-add-in"></a>从外接程序返回多个 UI  
 外接程序通常向主机应用程序提供多个需要其显示的 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]。 例如，假设一个作为 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的外接程序，它同时还向主机应用程序（也是 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]）提供状态信息。 此类外接程序可以通过结合使用[外接程序返回用户界面](#ReturnUIFromAddInContract)和[外接程序为用户界面](#AddInIsAUI)模型中的技术来实现。  
  
<a name="AddInsAndXBAPs"></a>   
## <a name="add-ins-and-xaml-browser-applications"></a>外接程序和 XAML 浏览器应用程序  
 到目前为止，示例中的主机应用程序都安装为独立应用程序。 但是，如果满足以下附加的生成和实现要求，[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 也可以承载外接程序：  
  
-   必须专门配置 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 应用程序清单，以便将管道（文件夹和程序集）和外接程序程序集下载到客户端计算机上的 [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] 应用程序缓存中 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 所在的文件夹中。  
  
-   用于发现和加载外接程序的 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 代码必须将 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 的 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 应用程序缓存用作管道和外接程序位置。  
  
-   如果外接程序引用位于源站点的松散文件，则 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 必须将外接程序加载到专门的安全上下文中；在由 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 承载时，外接程序只能引用位于主机应用程序源站点的松散文件。  
  
 下面几个小节将详细介绍这些任务。  
  
### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>配置用于 ClickOnce 部署的管道和外接程序  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 将下载到 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 部署缓存中的安全文件夹并从该文件夹运行。 为了使 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 能够承载外接程序，还必须将管道和外接程序程序集下载到该安全文件夹。 为此，需要将应用程序清单配置为包含要下载的管道和外接程序程序集。 这在 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 中最容易实现，但为使 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 检测到管道程序集，管道和外接程序程序集需要位于宿主 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 项目的根文件夹中。  
  
 因此，第一步是通过设置每个管道程序集和外接程序程序集项目的生成输出，向 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 项目的根文件夹生成管道和外接程序程序集。 下表显示管道程序集项目和外接程序程序集项目的生成输出路径，这些路径位于与宿主 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 项目相同的解决方案和根文件夹中。  
  
 表 1：XBAP 承载的管道程序集的生成输出路径  
  
|管道程序集项目|生成输出路径|  
|-------------------------------|-----------------------|  
|协定|`..\HostXBAP\Contracts\`|  
|加载项视图|`..\HostXBAP\AddInViews\`|  
|加载项方适配器|`..\HostXBAP\AddInSideAdapters\`|  
|宿主端适配器|`..\HostXBAP\HostSideAdapters\`|  
|外接程序|`..\HostXBAP\AddIns\WPFAddIn1`|  
  
 下一步是通过在 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 中执行以下操作，将管道程序集和外接程序程序集指定为 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 内容文件：  
  
1.  通过在“解决方案资源管理器”中右键单击每个管道文件夹，然后选择“包括在项目中”，将管道和外接程序程序集包括在项目中。  
  
2.  在“属性”窗口中，将每个管道程序集和外接程序程序集的“生成操作”都设置为“内容”。  
  
 最后一步是配置应用程序清单，以包含要下载的管道程序集文件和外接程序程序集文件。 这些文件应位于 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 应用程序所占用的 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 缓存的根文件夹下的文件夹中。 通过执行以下操作，可以在 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 中实现该配置：  
  
1.  右键单击 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 项目，依次单击“属性”、“发布”，然后单击“应用程序文件”按钮。  
  
2.  在“应用程序文件”对话框中，将每个管道和外接程序 DLL 的“发布状态”都设置为“包括(自动)”，并将每个管道和外接程序 DLL 的“下载组”都设置为“(必需)”。  
  
### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>从应用程序基使用管道和外接程序  
 为 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 部署配置管道和外接程序时，它们将下载到 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 所在的 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] 缓存文件夹中。 若要从 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 中使用管道和外接程序，[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 代码必须从应用程序基获取它们。 用于处理管道和外接程序的 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型的各种类型和成员为这种情况提供特殊支持。 首先，通过标识路径<xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase>枚举值。 将此值用于使用管道的相关外接程序成员的重载，这些成员包括：  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
### <a name="accessing-the-hosts-site-of-origin"></a>访问宿主的源站点  
 为确保外接程序可以引用源站点的文件，必须使用等效于主机应用程序的安全隔离来加载外接程序。 此安全级别由<xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType>枚举值，并传递到<xref:System.AddIn.Hosting.AddInToken.Activate%2A>激活外接程序时的方法。  
  
<a name="WPFAddInModelArchitecture"></a>   
## <a name="wpf-add-in-architecture"></a>WPF 外接程序体系结构  
 在最高级别，如我们所见，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]使[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序来实现[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)](直接或间接派生自<xref:System.Windows.FrameworkElement>) 使用<xref:System.AddIn.Contract.INativeHandleContract>，<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>和<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>。 结果是主机应用程序将返回<xref:System.Windows.FrameworkElement>显示从[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]宿主应用程序中。  
  
 对于简单的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 外接程序方案，这些内容已足够详细，可以满足开发者的需要。 对于更复杂的方案，特别是那些尝试使用附加 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 服务（如布局、资源和数据绑定）的方案，需要更为深入地掌握 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 如何扩展支持 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型的知识，才能了解它的优点和限制。  
  
 基本上，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 不会将 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 从外接程序传递到主机应用程序；[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 通过使用 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 互操作性传递 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的 Win32 窗口句柄。 因此，当 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 从外接程序传递到主机应用程序时，会发生以下情况：  
  
-   在外接程序端，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 获得一个将由主机应用程序显示的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的窗口句柄。 窗口句柄封装通过内部[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]派生自的类<xref:System.Windows.Interop.HwndSource>并实现<xref:System.AddIn.Contract.INativeHandleContract>。 此类的实例由<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>和封送从外接程序的应用程序域到主机应用程序的应用程序域。  
  
-   在主机应用程序端，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]会重新打包<xref:System.Windows.Interop.HwndSource>作为内部[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]派生自的类<xref:System.Windows.Interop.HwndHost>和使用<xref:System.AddIn.Contract.INativeHandleContract>。 此类的实例由<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>主机应用程序。  
  
 <xref:System.Windows.Interop.HwndHost> 存在要显示[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]，标识由窗口句柄，从[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]。 有关详细信息，请参阅 [WPF 和 Win32 互操作](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)。  
  
 总之， <xref:System.AddIn.Contract.INativeHandleContract>， <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>，和<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>的存在使得的窗口句柄[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]若要从外接程序中传递到主机应用程序，它通过封装<xref:System.Windows.Interop.HwndHost>和显示主机应用程序的[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
> [!NOTE]
>  因为主机应用程序获取<xref:System.Windows.Interop.HwndHost>，主机应用程序无法将返回的对象转换<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>到类型它由实现，如外接程序 (例如， <xref:System.Windows.Controls.UserControl>)。  
  
 按其性质，<xref:System.Windows.Interop.HwndHost>具有一定的局限性，影响主机应用程序可以使用它们。 但是，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]扩展<xref:System.Windows.Interop.HwndHost>具有多种功能，为外接程序方案。 下面介绍这些优点和限制。  
  
<a name="WPFAddInModelBenefits"></a>   
## <a name="wpf-add-in-benefits"></a>WPF 外接程序的优点  
 因为[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]外接程序[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]显示从主机应用程序使用派生自的内部类<xref:System.Windows.Interop.HwndHost>、 这些[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]约束由功能<xref:System.Windows.Interop.HwndHost>相对于[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]服务，如布局、 呈现、 数据绑定、 样式、 模板和资源。 但是，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]扩展了其内部<xref:System.Windows.Interop.HwndHost>子类的附加功能，包括以下：  
  
-   在主机应用程序的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 和外接程序的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 之间的 Tab 键切换功能。 请注意，"外接程序是[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]"编程模型要求重写的外接程序端适配器<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>以使用 tab 键切换，无论外接程序是完全信任还是部分受信任的。  
  
-   满足从主机应用程序 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 显示的外接程序 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 的可访问性要求。  
  
-   使 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 应用程序可在多个应用程序域方案中安全运行。  
  
-   在外接程序使用安全隔离（即部分信任安全沙盒）运行时，防止非法访问外接程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 窗口句柄。 调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>可确保此安全：  
  
    -   有关"外接程序返回[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]"编程模型，唯一的方法传递的外接程序的窗口句柄[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]越过隔离边界是调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>。  
  
    -   有关"外接程序是[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]"编程模型，重写<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>上的外接程序端适配器和调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>（如在上面的示例所示） 是必需的如正在调用外接程序端适配器`QueryContract`实现从主机端适配器中。  
  
-   提供多个应用程序域执行保护。 由于应用程序域的限制，因此即使存在隔离边界，外接程序应用程序域中引发的未经处理的异常也会导致整个应用程序出现故障。 但是，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 和 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 外接程序模型提供了一种简单方式来解决此问题并提高应用程序稳定性。 A[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]外接程序显示[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]创建<xref:System.Windows.Threading.Dispatcher>的线程的应用程序域的运行，如果主机应用程序是[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用程序。 你可以检测通过处理应用程序域中发生的所有未经处理的异常<xref:System.Windows.Threading.Dispatcher.UnhandledException>事件[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]外接程序的<xref:System.Windows.Threading.Dispatcher>。 你可以获取<xref:System.Windows.Threading.Dispatcher>从<xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>属性。  
  
<a name="WPFAddInModelLimitations"></a>   
## <a name="wpf-add-in-limitations"></a>WPF 外接程序限制  
 优点之外，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]将添加到由提供的默认行为<xref:System.Windows.Interop.HwndSource>， <xref:System.Windows.Interop.HwndHost>，和窗口句柄，也有限制的外接程序[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]，显示从主机应用程序：  
  
-   从主机应用程序显示的外接程序 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 不遵从主机应用程序的剪辑行为。  
  
-   互操作性方案中的“空域”概念也适用于外接程序（请参阅[技术区概述](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)）。  
  
-   主机应用程序的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 服务（如资源继承、数据绑定和命令）不会自动提供给外接程序 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]。 若要向外接程序提供这些服务，需要更新管道。  
  
-   外接程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 不能旋转、缩放、倾斜，也不受转换的影响（请参阅[转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)）。  
  
-   外接程序中的内容[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]，呈现的绘制操作从<xref:System.Drawing>命名空间可以包括 alpha 混合。 但是，包含它的外接程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 和主机应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 都必须是 100% 不透明；换言之，二者的 `Opacity` 属性必须设置为 1。  
  
-   如果<xref:System.Windows.Window.AllowsTransparency%2A>属性中的主机应用程序外接程序包含一个窗口[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]设置为`true`外, 接程序不可见。 即使外接程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 是 100% 不透明（即 `Opacity` 属性的值为 1）也是如此。  
  
-   外接程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 必须出现在同一顶级窗口中其他 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 元素之上。  
  
-   外接程序的任何部分[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]可以使用呈现<xref:System.Windows.Media.VisualBrush>。 外接程序可以获取生成的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的快照，从而创建一个位图，通过协定所定义的方法可将该位图传递到主机应用程序。  
  
-   无法从播放媒体文件<xref:System.Windows.Controls.MediaElement>在外接程序[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
-   主机应用程序既不会接收，也不会引发为外接程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 生成的鼠标事件，主机应用程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的 `IsMouseOver` 属性值为 `false`。  
  
-   当焦点在外接程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的控件之间移动时，主机应用程序既不会接收，也不会引发 `GotFocus` 和 `LostFocus` 事件。  
  
-   在打印时，包含外接程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 的主机应用程序部分将显示为空白。  
  
-   所有调度程序 (请参阅<xref:System.Windows.Threading.Dispatcher>) 创建的外接程序[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]必须关闭手动所有者外接程序被卸载前如果主机应用程序才能继续执行。 协定可以实现一些方法，主机应用程序使用这些方法，可以在外接程序卸载之前通知外接程序，从而允许外接程序 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 关闭自己的调度程序。  
  
-   如果外接程序[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]是<xref:System.Windows.Controls.InkCanvas>或包含<xref:System.Windows.Controls.InkCanvas>，不能卸载外接程序。  
  
<a name="PerformanceOptimization"></a>   
## <a name="performance-optimization"></a>性能优化  
 默认情况下，如果使用多个应用程序域，则每个应用程序所需的各种 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 程序集都会加载到该应用程序的域中。 因此，创建新应用程序域和在应用程序域中启动应用程序所需的时间可能会影响性能。 但 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 提供了一种减少启动时间的方法，即指示应用程序共享各应用程序域的程序集（如果已经加载）。 执行此操作通过使用<xref:System.LoaderOptimizationAttribute>属性，必须应用于入口点方法 (`Main`)。 这种情况下，只能使用代码来实现应用程序定义（请参阅[应用程序管理概述](../../../../docs/framework/wpf/app-development/application-management-overview.md)）。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.LoaderOptimizationAttribute>  
 [外接程序和扩展性](../../../../docs/framework/add-ins/index.md)  
 [应用程序域](../../../../docs/framework/app-domains/application-domains.md)  
 [.NET framework 远程处理概述](http://msdn.microsoft.com/library/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)  
 [使对象可远程处理](http://msdn.microsoft.com/library/01197253-3f13-43b7-894d-9683e431192a)  
 [帮助主题](../../../../docs/framework/wpf/app-development/how-to-topics.md)
