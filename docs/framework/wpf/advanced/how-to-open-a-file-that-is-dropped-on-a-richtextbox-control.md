---
title: 如何：打开放置在 RichTextBox 控件上的文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: f3c10ae76a9afcc04578c590cc57cd43c3ab7a1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547757"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>如何：打开放置在 RichTextBox 控件上的文件
在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]、 <xref:System.Windows.Controls.TextBox>， <xref:System.Windows.Controls.RichTextBox>，和<xref:System.Windows.Documents.FlowDocument>控件所有具有内置拖放功能。 内置功能，可拖放文本内部或之间控件。 但是，它不支持通过删除该控件上的文件打开的文件。 这些控件还会将拖放事件标记为已处理。 因此，默认情况下，无法添加你自己的事件处理程序来提供功能以打开拖放的文件。  
  
 若要添加这些控件中的拖放事件的其他处理，使用<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>方法以添加事件处理程序的拖放事件。 设置`handledEventsToo`参数`true`为具有已标记为由事件路由的其他元素处理的路由事件调用所指定的处理程序。  
  
> [!TIP]
>  你可以替换内置的拖放功能的<xref:System.Windows.Controls.TextBox>， <xref:System.Windows.Controls.RichTextBox>，和<xref:System.Windows.Documents.FlowDocument>通过处理拖放事件的预览版本并将预览事件标记为已处理。 但是，这将禁用与内置的拖放功能，并且不建议。  
  
## <a name="example"></a>示例  
 下面的示例演示如何添加处理程序<xref:System.Windows.DragDrop.DragOver>和<xref:System.Windows.DragDrop.Drop>上的事件<xref:System.Windows.Controls.RichTextBox>。 此示例使用<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>方法和集`handledEventsToo`参数`true`，以便将即使调用事件处理程序<xref:System.Windows.Controls.RichTextBox>标记为已处理这些事件。 中的事件处理程序的代码的新增功能可打开放置一个文本文件<xref:System.Windows.Controls.RichTextBox>。  
  
 若要测试此示例，请将拖动的文本文件或丰富文本格式 (RTF) 文件从 Windows 资源管理器到<xref:System.Windows.Controls.RichTextBox>。 将在中打开文件<xref:System.Windows.Controls.RichTextBox>。 如果你在按住 SHIFT 键之前删除该文件，将以纯文本格式打开文件。  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
