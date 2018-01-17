---
title: "如何：从剪贴板检索数据"
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
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c009efe743865896341da268bd14bf24158df46d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>如何：从剪贴板检索数据
<xref:System.Windows.Forms.Clipboard>类提供了可以使用与 Windows 操作系统的剪贴板功能进行交互的方法。 许多应用程序的数据作为临时存储库使用剪贴板。 例如，字处理器在剪切和粘贴操作期间使用剪贴板。 剪贴板还可用于将信息传输到另一个应用程序中。  
  
 某些应用程序将数据存储在剪贴板中多种格式，增加其他应用程序可能会使用数据的数量。 剪贴板格式是用于标识格式的字符串。 使用标识的格式的应用程序可以检索在剪贴板上关联的数据。 <xref:System.Windows.Forms.DataFormats>类提供了供你使用的预定义的格式名。 你可以使用你自己的格式名，或用作其格式的对象的类型。 有关将数据添加到剪贴板的信息，请参阅[如何： 将数据添加到剪贴板](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)。  
  
 若要确定剪贴板是否包含特定的格式的数据，使用之一`Contains`*格式*方法或<xref:System.Windows.Forms.Clipboard.GetData%2A>方法。 若要从剪贴板检索数据，使用之一`Get`*格式*方法或<xref:System.Windows.Forms.Clipboard.GetData%2A>方法。 这些方法是在新[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]。  
  
 从通过使用版本剪贴板访问数据早于[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]，使用<xref:System.Windows.Forms.Clipboard.GetDataObject%2A>方法调用的方法的返回和<xref:System.Windows.Forms.IDataObject>。 若要确定特定的格式是否位于返回的对象，例如，调用<xref:System.Windows.Forms.IDataObject.GetDataPresent%2A>方法。  
  
> [!NOTE]
>  所有基于 Windows 的应用程序共享系统剪贴板。 因此，内容可能会发生更改时切换到另一个应用程序。  
>   
>  <xref:System.Windows.Forms.Clipboard>类仅在设置为单线程单元 (STA) 模式的线程中使用。 若要使用此类，请确保你`Main`方法标记为<xref:System.STAThreadAttribute>属性。  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>若要从单一的常用格式在剪贴板中检索数据  
  
1.  使用<xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>， <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>， <xref:System.Windows.Forms.Clipboard.GetImage%2A>，或<xref:System.Windows.Forms.Clipboard.GetText%2A>方法。 （可选） 使用相应`Contains`*格式*方法，首先以确定数据是否可用的特定的格式。 这些方法是仅适用于[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]。  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>若要从自定义格式剪贴板中检索数据  
  
1.  使用<xref:System.Windows.Forms.Clipboard.GetData%2A>具有自定义格式名称方法。 此方法是仅适用于[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]。  
  
     你还可以使用与预定义的格式名<xref:System.Windows.Forms.Clipboard.SetData%2A>方法。 有关详细信息，请参阅<xref:System.Windows.Forms.DataFormats>。  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>若要从以多种格式剪贴板中检索数据  
  
1.  使用 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 方法。 必须使用此方法来检索数据从剪贴板上版本早于[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]。  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>请参阅  
 [拖放操作和剪贴板支持](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [如何：将数据添加到剪贴板](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
