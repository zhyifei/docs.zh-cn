---
title: 合并资源字典
ms.date: 03/30/2017
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
ms.openlocfilehash: 899955a9f3302e67de4efa0ce0cb6baf6bf0ec5d
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559776"
---
# <a name="merged-resource-dictionaries"></a>合并资源字典
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 资源支持合并资源字典功能。 此功能提供一种方法，可在编译的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 应用程序外部定义 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序的资源部分。 然后可以在应用程序之间共享资源，还可更方便地将资源隔离以进行本地化。  
  
## <a name="introducing-a-merged-resource-dictionary"></a>引入合并资源字典  
 在标记中，使用以下语法将合并资源字典引入页面：  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 请注意，<xref:System.Windows.ResourceDictionary> 元素没有 "X：Key"[指令](../../../desktop-wpf/xaml-services/xkey-directive.md)，资源集合中的所有项通常都需要此指令。 但 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 集合中的另一个 <xref:System.Windows.ResourceDictionary> 引用是一个特殊情况，为此合并资源字典方案保留。 引入合并资源字典的 <xref:System.Windows.ResourceDictionary> 不能包含[X：Key 指令](../../../desktop-wpf/xaml-services/xkey-directive.md)。 通常，<xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 集合中的每个 <xref:System.Windows.ResourceDictionary> 指定 <xref:System.Windows.ResourceDictionary.Source%2A> 属性。 <xref:System.Windows.ResourceDictionary.Source%2A> 的值应为一个统一资源标识符（URI），该资源标识符解析为要合并的资源文件的位置。 该 URI 的目标必须是另一个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件，其 <xref:System.Windows.ResourceDictionary> 为其根元素。  
  
> [!NOTE]
> 在指定为合并字典的 <xref:System.Windows.ResourceDictionary> 中定义资源是合法的，无论是指定 <xref:System.Windows.ResourceDictionary.Source%2A>的替代方法，还是除了指定的源中包含的所有资源。 但是，这不是一种常见方案；合并字典的主要方案是从外部文件位置合并资源。 如果要在页的标记中指定资源，通常应在主 <xref:System.Windows.ResourceDictionary> 中定义这些资源，而不应在合并字典中定义这些资源。  
  
## <a name="merged-dictionary-behavior"></a>合并字典的行为  
 合并字典中的资源占用资源查找范围中的一个位置，此范围恰好在它们合并到的主要资源字典中的范围之后。 尽管任何字典中的资源键必须唯一，但一个资源键可在一组合并字典中多次存在。 在这种情况下，返回的资源将来自 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 集合中按顺序找到的最后一个字典。 如果 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 集合是在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中定义的，则集合中合并字典的顺序就是标记中提供的元素的顺序。 如果在主要字典和合并的字典中均定义了同一个键，则返回的资源将来自主要字典。 这些范围规则同等地适用于静态资源引用和动态资源引用。  
  
### <a name="merged-dictionaries-and-code"></a>合并字典和代码  
 可通过代码将合并字典添加到 `Resources` 字典。 默认情况下，对于任何 `Resources` 属性，最初为空 <xref:System.Windows.ResourceDictionary> 都有默认值，初始为空 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 集合属性。 若要通过代码添加合并字典，可获取对所需主 <xref:System.Windows.ResourceDictionary>的引用、获取其 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> 属性值，并对 <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>中包含的泛型 `Collection` 调用 `Add`。 添加的对象必须是新的 <xref:System.Windows.ResourceDictionary>。 在代码中，你不设置 <xref:System.Windows.ResourceDictionary.Source%2A> 属性。 相反，您必须通过创建一个 <xref:System.Windows.ResourceDictionary> 对象或加载一个对象来获取该对象。 一种加载现有 <xref:System.Windows.ResourceDictionary> 以便在具有 <xref:System.Windows.ResourceDictionary> 根的现有 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件流上调用 <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> 的方法，然后将 <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> 返回值强制转换为 <xref:System.Windows.ResourceDictionary>。  
  
### <a name="merged-resource-dictionary-uris"></a>合并资源字典 URI  
 对于如何包含合并资源字典，有几种方法可供您使用的统一资源标识符（URI）格式来指示。 这些技术可概括地分为两类：作为项目的一部分编译的资源，和不作为项目的一部分编译的资源。  
  
 对于作为项目的一部分编译的资源，可使用引用资源位置的相对路径。 相对路径会在编辑期间计算。 必须将资源作为“资源”生成操作定义为项目的一部分。 如果将资源 .xaml 文件作为“资源”包括在项目中，则无需将资源文件复制到输出目录，因为资源已包括在编译的应用程序中。 也可以使用“内容”生成操作，但必须将文件复制到输出目录，还需将相同路径关系中的资源文件部署到可执行文件。  
  
> [!NOTE]
> 不要使用“嵌入资源”生成操作。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序支持生成操作本身，但 <xref:System.Windows.ResourceDictionary.Source%2A> 的解决不包含 <xref:System.Resources.ResourceManager>，因此无法将单个资源与流分离。 你仍可以将嵌入的资源用于其他目的，只要你还使用 <xref:System.Resources.ResourceManager> 来访问资源。  
  
 还有一种相关技术是使用指向 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件的 Pack URI，并将其作为“源”进行引用。 Pack URI 可启用对引用程序集的组件和其他技术的引用。 有关 Pack URI 的详细信息，请参阅 [WPF 应用程序资源、内容和数据文件](../app-development/wpf-application-resource-content-and-data-files.md)。  
  
 对于不作为项目的一部分编译的资源，URI 将在运行时计算。 可使用常见的 URI 传输（如 file: 或 http:）引用资源文件。 使用非编译资源方法的缺点是：file: 访问需要额外部署步骤，并且 http: 访问意味着需访问 Internet 安全区域。  
  
### <a name="reusing-merged-dictionaries"></a>重用合并字典  
 可以在应用程序之间重复使用或共享合并资源字典，因为要合并的资源字典可以通过任何有效的统一资源标识符（URI）进行引用。 执行此操作的确切方式取决于应用程序部署策略和所遵循的应用程序模型。 前面提及的 Pack URI 策略提供了一种方法，通常可通过共享程序集引用在开发期间跨多个项目将合并资源作为源使用。 在此方案中，资源仍由客户端分发，并且至少有一个应用程序必须部署引用的程序集。 还有可能通过使用 http 协议的分布式 URI 引用合并资源。  
  
 另一种合并字典/应用程序部署的可能方案是将合并字典编写为本地应用程序文件或编写到共享存储。  
  
### <a name="localization"></a>Localization  
 如果需要本地化的资源保留为松散的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，并且隔离于将合并为主要字典的字典，则可单独本地化这些文件。 这是本地化附属资源程序集的轻量级替代方法。 有关详细信息，请参阅 [WPF 全球化和本地化概述](wpf-globalization-and-localization-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.ResourceDictionary>
- [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [资源和代码](resources-and-code.md)
- [WPF 应用程序资源、内容和数据文件](../app-development/wpf-application-resource-content-and-data-files.md)
