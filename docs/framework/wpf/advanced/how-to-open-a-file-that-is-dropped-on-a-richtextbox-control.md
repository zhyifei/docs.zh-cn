---
title: 如何：打开放入 RichTextBox 控件的文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: 408d48856362fa8a77a44e2cc97cb2d5ff608dcf
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046357"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a>如何：打开放入 RichTextBox 控件的文件

在中[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], 、<xref:System.Windows.Controls.RichTextBox>和<xref:System.Windows.Documents.FlowDocument>控件都具有内置的拖放功能。 <xref:System.Windows.Controls.TextBox> 内置功能可用于在控件内部和之间拖放文本。 但是, 它不会通过将文件放在控件上来打开文件。 这些控件还将拖放事件标记为已处理。 因此, 默认情况下, 不能添加自己的事件处理程序来提供打开已删除文件的功能。

若要为这些控件中的拖放事件添加其他处理, 请使用<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>方法添加拖放事件的事件处理程序。 将参数设置为`true` , 以便为已标记为由事件路由中的其他元素处理的路由事件调用指定的处理程序。 `handledEventsToo`

> [!TIP]
> 可以通过处理拖放事件的预览版本并将预览事件标记<xref:System.Windows.Controls.TextBox>为<xref:System.Windows.Controls.RichTextBox>"已<xref:System.Windows.Documents.FlowDocument>处理" 来替换、和的内置拖放功能。 但是, 这将禁用内置的拖放功能, 不建议这样做。

## <a name="example"></a>示例

下面的示例演示如何在<xref:System.Windows.DragDrop.DragOver> <xref:System.Windows.Controls.RichTextBox>中为和<xref:System.Windows.DragDrop.Drop>事件添加处理程序。 此示例使用<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>方法并`handledEventsToo`将参数设置为`true` , 以便即使将<xref:System.Windows.Controls.RichTextBox>这些事件标记为已处理, 也会调用事件处理程序。 事件处理程序中的代码将添加功能, 以打开在上<xref:System.Windows.Controls.RichTextBox>放置的文本文件。

若要测试此示例, 请从 Windows 资源管理器将文本文件或 rtf 格式 (RTF) 文件拖到<xref:System.Windows.Controls.RichTextBox>。 文件将在中<xref:System.Windows.Controls.RichTextBox>打开。 如果在删除文件之前按下 SHIFT 键, 则文件将以纯文本形式打开。

[!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]

[!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
[!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
