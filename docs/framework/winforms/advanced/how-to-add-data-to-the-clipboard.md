---
title: "如何：将数据添加到剪贴板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 452dfc5a9645e8f43ab583099deec60faa2d1b4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-data-to-the-clipboard"></a>如何：将数据添加到剪贴板
<xref:System.Windows.Forms.Clipboard>类提供了可以使用与 Windows 操作系统的剪贴板功能进行交互的方法。 许多应用程序的数据作为临时存储库使用剪贴板。 例如，字处理器在剪切和粘贴操作期间使用剪贴板。 剪贴板还可用于将数据传输到另一个应用程序。  
  
 当将数据添加到剪贴板时，你可以指示的数据格式，以便其他应用程序能够识别数据，如果它们可以使用该格式。 到剪贴板中多个不同的格式，增加其他应用程序可能会使用数据的数量，你还可以添加数据。  
  
 剪贴板格式是一个字符串，标识格式，以便使用该格式的应用程序可以检索关联的数据。 <xref:System.Windows.Forms.DataFormats>类提供了供你使用的预定义的格式名。 你可以使用你自己的格式名，或用作其格式的对象的类型。  
  
 若要将数据添加到剪贴板中一个或多个格式，使用<xref:System.Windows.Forms.Clipboard.SetDataObject%2A>方法。 可以将任何对象传递给此方法，但若要添加多个格式数据，你必须首先将数据添加到一个单独的对象设计为可以使用多种格式。 通常情况下，你将添加到你的数据<xref:System.Windows.Forms.DataObject>，但你可以使用实现任何类型<xref:System.Windows.Forms.IDataObject>接口。  
  
 在[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]，你可以直接向剪贴板添加数据，通过使用为简化了基本剪贴板任务而设计的新方法。 当您使用单一的常用格式，例如文本中的数据时，请使用这些方法。  
  
> [!NOTE]
>  所有基于 Windows 的应用程序共享剪贴板。 因此，内容可能会发生更改时切换到另一个应用程序。  
>   
>  <xref:System.Windows.Forms.Clipboard>类仅在设置为单线程单元 (STA) 模式的线程中使用。 若要使用此类，请确保你`Main`方法标记为<xref:System.STAThreadAttribute>属性。  
>   
>  对象必须可序列化，才能将其放在剪贴板上。 若要使类型可序列化，将其与标记<xref:System.SerializableAttribute>属性。 如果将非可序列化对象传递给剪贴板方法时，该方法将失败而不引发异常。 有关序列化的详细信息，请参阅<xref:System.Runtime.Serialization>。  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>若要将数据添加到剪贴板中单一的常用格式  
  
1.  使用<xref:System.Windows.Forms.Clipboard.SetAudio%2A>， <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>， <xref:System.Windows.Forms.Clipboard.SetImage%2A>，或<xref:System.Windows.Forms.Clipboard.SetText%2A>方法。 这些方法是仅适用于[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]。  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>若要将数据添加到剪贴板中自定义格式  
  
1.  使用<xref:System.Windows.Forms.Clipboard.SetData%2A>具有自定义格式名称方法。 此方法是仅适用于[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]。  
  
     你还可以使用与预定义的格式名<xref:System.Windows.Forms.Clipboard.SetData%2A>方法。 有关详细信息，请参阅<xref:System.Windows.Forms.DataFormats>。  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>若要将数据添加到剪贴板中多种格式  
  
1.  使用<xref:System.Windows.Forms.Clipboard.SetDataObject%2A>方法并传入<xref:System.Windows.Forms.DataObject>，其中包含你的数据。 你必须使用此方法将数据添加到剪贴板上版本早于[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]。  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>请参阅  
 [拖放操作和剪贴板支持](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [如何：从剪贴板检索数据](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
