---
title: 文档序列化和存储
ms.date: 03/30/2017
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
ms.openlocfilehash: 8ee8acb95aa4a7c8dd80ea88594e582f05b71611
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="document-serialization-and-storage"></a>文档序列化和存储
Microsoft.NET Framework 提供了一个功能强大的环境，用于创建和显示高质量的文档。  支持固定文档和流文档以及高级的增强的功能查看控件，结合强大的二维和三维图形功能到新级别的质量和用户体验的.NET Framework 应用程序。  能够灵活地管理内存中文档的表示形式是.NET Framework 的一个主要功能和能够高效保存和加载数据存储区中的文档是几乎每个应用程序的需要。  将文档从内部的内存中表示形式转换为外部数据存储的过程称为序列化。  反之，读取数据存储并重新创建原始内存中实例的过程则称为反序列化。  
  
 
  
<a name="AboutSerialization"></a>   
## <a name="about-document-serialization"></a>关于文档序列化  
 理论上，对于应用程序来说，从内存中序列化文档和将文档反序列到原来的内存中都是透明的。  应用程序调用序列化程序“write”方法来保存文档，而反序列化程序“read”方法则访问数据存储并在内存中重新创建原始实例。  对于应用程序来说，只要序列化和反序列化进程将文档重新创建为其原始格式，数据存储的特定格式通常无关紧要。  
  
 应用程序通常提供多个序列化选项，用户可以使用这些选项将文档保存到不同的介质或保存为不同格式。  例如，应用程序可提供“另存为”选项将文档存储到磁盘文件、数据库或 Web 服务。  同样，不同的序列化程序可将文档存储为不同的格式，例如 HTML、RTF、XML、XPS 或第三方格式。  对于应用程序，序列化定义了一个接口，该接口可以隔离每个特定序列化程序的实现内部的存储介质的详细信息。  除了封装存储详细信息，.NET Framework 的好处<xref:System.Windows.Documents.Serialization>[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]提供几个其他重要功能。  
  
### <a name="features-of-net-framework-30-document-serializers"></a>.NET Framework 3.0 文档序列化程序的功能  
  
-   通过直接访问高级别文档对象（逻辑树和视觉对象），可以有效存储已分页的内容、二维/三维元素、图像、媒体、超链接、注释以及其他支持内容。  
  
-   同步和异步操作。  
  
-   支持具有以下增强功能的插件序列化程序：  
  
    -   所有.NET Framework 应用程序使用的系统级访问。  
  
    -   简单应用程序插件的发现功能。  
  
    -   第三方自定义插件的简单部署、安装和更新。  
  
    -   对自定义运行时设置和选项的用户界面支持。  
  
### <a name="xps-print-path"></a>XPS 打印路径  
 Microsoft.NET Framework[!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]打印路径还提供了一个可扩展机制，用于编写文档，一直到打印输出。  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 可以作为文档文件格式，也可以作为 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] 的本机后台打印格式。  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文档可直接发送到与 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 兼容的打印机，而无需转换为中间格式。  有关打印路径输出选项和功能的其他信息，请参阅[打印概述](../../../../docs/framework/wpf/advanced/printing-overview.md)。  
  
<a name="PluginSerializers"></a>   
## <a name="plug-in-serializers"></a>插件序列化程序  
 <xref:System.Windows.Documents.Serialization> Api 为插件序列化程序和链接的序列化程序从应用程序单独安装提供支持，在运行时，将绑定并通过使用访问<xref:System.Windows.Documents.Serialization.SerializerProvider>发现机制。  插件序列化程序提供增强功能，可以简化部署和系统范围的使用。  你还可以针对无法在其中访问插件序列化程序的部分可信环境（例如 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]）实现链接序列化程序。  链接序列化程序，它基于的派生实现<xref:System.Windows.Documents.Serialization.SerializerWriter>类，请将编译并链接到应用程序直接。  插件序列化程序和链接序列化程序都是通过相同的公共方法和事件来运行的，这样可以方便地在同一应用程序中使用其中一种或两种序列化程序。  
  
 插件序列化程序对应用程序开发人员很有帮助：它向新的存储设计和文件格式提供扩展性，而无需在生成时对每种潜在的格式进行直接编码。  插件序列化程序还通过为自定义或专有文件格式提供部署、安装和更新系统可访问插件的标准方法，使第三方开发人员受益匪浅。  
  
### <a name="using-a-plug-in-serializer"></a>使用插件序列化程序  
 插件序列化程序易于使用。  <xref:System.Windows.Documents.Serialization.SerializerProvider>类枚举<xref:System.Windows.Documents.Serialization.SerializerDescriptor>对象对每个插件已安装的系统上。  <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A>属性筛选器已安装的即插即用的项基于当前配置并验证是否可以加载和应用程序使用序列化程序。  <xref:System.Windows.Documents.Serialization.SerializerDescriptor>还提供其他属性，如<xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A>和<xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>，应用程序可以用于提示中选择可用的输出格式的序列化程序的用户。  默认插件序列化程序[!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]提供.NET Framework，并会始终进行枚举。  在用户选择输出格式之后,<xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A>方法用于创建<xref:System.Windows.Documents.Serialization.SerializerWriter>对于特定的格式。  <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> 然后可以调用方法以输出到数据存储文档流。  
  
 下面的示例演示使用的应用程序<xref:System.Windows.Documents.Serialization.SerializerProvider>"PlugInFileFilter"属性中的方法。  PlugInFileFilter 枚举已安装的即插即用的项，并生成一个筛选器字符串，可用的文件选项<xref:Microsoft.Win32.SaveFileDialog>。  
  
 [!code-csharp[DocumentSerialize#DocSerializeFileFilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]  
  
 由用户选择了输出文件的名称之后，下面的示例演示使用<xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A>方法将给定的文档存储在指定的格式。  
  
 [!code-csharp[DocumentSerialize#DocSerializePlugIn](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]  
  
<a name="InstallingPluginSerializers"></a>   
### <a name="installing-plug-in-serializers"></a>安装插件序列化程序  
 <xref:System.Windows.Documents.Serialization.SerializerProvider>类提供了插件序列化程序发现和访问的较高级别应用程序接口。  <xref:System.Windows.Documents.Serialization.SerializerProvider> 查找并提供应用程序的序列化程序已安装并且可在系统上访问的列表。  已安装序列化程序的具体信息通过注册表设置来定义。  插件序列化程序可以通过使用添加到注册表<xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A>方法; 或如果.NET Framework 尚未安装，该插件安装脚本可以直接设置注册表值本身。  <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A>方法可以用于删除以前安装插件，或注册表设置都可以通过卸载脚本同样重置。  
  
### <a name="creating-a-plug-in-serializer"></a>创建插件序列化程序  
 插件序列化程序和链接序列化程序使用同一公开的公共方法和事件，并且可同样设计为以同步或异步方式运行。  创建插件序列化程序通常应执行下列三个基本步骤：  
  
1.  首先以链接序列化程序的形式实现和调试序列化程序。  开始时通过创建直接编译和链接到测试应用程序的序列化程序，可以提供对断点以及其他有助于测试的调试服务的完全访问权限。  
  
2.  序列化程序完全测试之后，<xref:System.Windows.Documents.Serialization.ISerializerFactory>接口添加以创建插件。  <xref:System.Windows.Documents.Serialization.ISerializerFactory>接口允许完全访问权限的所有.NET Framework 对象包括逻辑树中，<xref:System.Windows.UIElement>对象， <xref:System.Windows.Documents.IDocumentPaginatorSource>，和<xref:System.Windows.Media.Visual>元素。  此外<xref:System.Windows.Documents.Serialization.ISerializerFactory>提供相同的同步和异步方法和用于由链接的序列化事件。  由于输出大型文档需要一定时间，因此推荐使用异步操作以维持响应用户交互，并在数据存储出现问题时提供“取消”选项。  
  
3.  创建插件序列化程序之后，实现安装脚本以分发和安装（以及卸载）插件（请参阅上面的“[安装插件序列化程序](#InstallingPluginSerializers)”）。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Documents.Serialization>  
 <xref:System.Windows.Xps.XpsDocumentWriter>  
 <xref:System.Windows.Xps.Packaging.XpsDocument>  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [打印概述](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [XML 纸张规范：概述](http://go.microsoft.com/fwlink?LinkID=106246)
