---
title: "数据和数据对象"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WPF], drag-and-drop
- DataFormats class [WPF]
- DataObject class [WPF]
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc5d5f8c2090f6abaa1157db2a92d2e689d7f216
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="data-and-data-objects"></a>数据和数据对象
作为拖放操作的一部分传输的数据存储在数据对象。  从概念上讲，数据对象由一个或多个以下对组成：  
  
-   <xref:System.Object>包含实际数据。  
  
-   相应的数据格式标识符。  
  
 数据本身可以包含的任何内容可以表示为基础<xref:System.Object>。  相应的数据格式是字符串或<xref:System.Type>，它提供有关设置数据的格式的提示是中。  数据对象支持承载多个数据/数据格式对;这使单个数据对象可以提供多个格式的数据。  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>数据对象  
 所有数据对象必须都实现<xref:System.Windows.IDataObject>接口，从而提供以下标准组方法，用于启用和帮助进行数据传输。  
  
|方法|摘要|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|检索指定的数据格式中的数据对象。|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|检查以确定是否可在中，或者可以转换为指定的格式数据。|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|返回此数据对象中的数据存储在中，或可以转换为的格式中的列表。|  
|<xref:System.Windows.IDataObject.SetData%2A>|将指定的数据存储在此数据对象。|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供的基本实现<xref:System.Windows.IDataObject>中<xref:System.Windows.DataObject>类。 常用<xref:System.Windows.DataObject>类是足够的许多常用的数据传输方案。  
  
 有几个预定义的格式，如位图、 CSV、 文件、 HTML、 RTF、 字符串、 文本和音频。 有关与提供的预定义的数据格式信息[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，请参阅<xref:System.Windows.DataFormats>类参考主题。  
  
 数据对象通常包括一个工具，以便自动将在提取数据; 时存储在为不同格式的一种格式的数据的转换此功能被称为自动转换。 当查询数据对象中可用的数据格式，可以通过调用筛选从本机数据格式自动转换的数据格式<xref:System.Windows.DataObject.GetFormats%28System.Boolean%29>或<xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29>方法并指定`autoConvert`参数作为`false`。  将数据添加到具有的数据对象时<xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29>方法，自动转换的数据，可以通过设置禁止`autoConvert`参数`false`。  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>使用数据对象  
 本部分介绍用于创建和使用数据对象的常见技术。  
  
### <a name="creating-new-data-objects"></a>创建新的数据对象  
 <xref:System.Windows.DataObject>类提供了多个重载的构造函数，以方便填充新<xref:System.Windows.DataObject>使用单一数据格式对的实例。  
  
 下面的代码示例创建一个新的数据对象，并利用重载的构造函数之一<xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) 来初始化具有一个字符串，指定的数据格式的数据对象。  字符串; 在这种情况下，指定数据格式<xref:System.Windows.DataFormats>类提供一组预定义的类型字符串。 默认情况下允许存储的数据的自动转换。  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 创建数据对象的代码的更多示例，请参阅[创建数据对象](../../../../docs/framework/wpf/advanced/how-to-create-a-data-object.md)。  
  
### <a name="storing-data-in-multiple-formats"></a>以多种格式存储数据  
 单个数据对象是能够以多种格式存储数据。   战略使用单个数据对象中的多个数据格式可能会使数据对象使用广泛的放置目标比如果只有无法表示一种数据格式。  请注意，一般情况下，拖动源必须是可由潜在的放置目标的数据格式不可知。  
  
 下面的示例演示如何使用<xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29>方法将数据添加到多个格式中的数据对象。  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>查询可用的格式数据对象  
 由于单个数据对象可以包含任意数目的数据格式，数据对象将包括用于检索可用的数据格式的列表的功能。  
  
 下面的代码示例使用<xref:System.Windows.DataObject.GetFormats%2A>重载获取表示所有可用数据对象 （本机和通过自动转换） 中的数据格式的字符串的数组。  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 查询可用的数据格式的数据对象的代码的更多示例，请参阅[列出数据对象中的数据格式](../../../../docs/framework/wpf/advanced/how-to-list-the-data-formats-in-a-data-object.md)。  查询数据对象是否存在特定的数据格式的示例，请参阅[确定数据格式是否存在数据对象中](../../../../docs/framework/wpf/advanced/how-to-determine-if-a-data-format-is-present-in-a-data-object.md)。  
  
### <a name="retrieving-data-from-a-data-object"></a>从数据对象中检索数据  
 从特定的格式中的数据对象中检索数据只需调用之一<xref:System.Windows.DataObject.GetData%2A>方法并指定所需的数据格式。  之一<xref:System.Windows.DataObject.GetDataPresent%2A>方法可以用于检查是否存在特定的数据格式。  <xref:System.Windows.DataObject.GetData%2A>返回中的数据<xref:System.Object>; 具体取决于数据格式，此对象可以强制转换为特定类型的容器。  
  
 下面的代码示例使用<xref:System.Windows.DataObject.GetDataPresent%28System.String%29>重载，以检查是否可指定的数据格式 （本机编译或通过自动转换）。 指定的格式是否可用，该示例通过使用检索的数据<xref:System.Windows.DataObject.GetData%28System.String%29>方法。  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 有关的数据对象中检索数据的代码的更多示例，请参阅[检索特定的数据格式的数据](../../../../docs/framework/wpf/advanced/how-to-retrieve-data-in-a-particular-data-format.md)。  
  
### <a name="removing-data-from-a-data-object"></a>从数据对象中删除数据  
 数据对象不能直接删除数据。  若要有效地从数据对象中删除数据，请按照下列步骤：  
  
1.  创建一个新的数据对象将包含你想要保留数据。  
  
2.  "复制"所需的数据，可从旧的数据对象到新的数据对象。  若要将数据复制，使用之一<xref:System.Windows.DataObject.GetData%2A>方法来检索<xref:System.Object>，其中包含原始数据，，然后执行下列任一<xref:System.Windows.DataObject.SetData%2A>方法将数据添加到新的数据对象。  
  
3.  将替换为新旧数据对象。  
  
> [!NOTE]
>  <xref:System.Windows.DataObject.SetData%2A>方法仅将数据添加到数据对象; 即使数据和数据格式时完全相同的先前调用作为不替换数据。 调用<xref:System.Windows.DataObject.SetData%2A>两次以相同的数据和数据格式将导致两次中的数据对象存在的数据/数据格式。
