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
ms.openlocfilehash: 8ffa4c9919788060dc4524e127c181ee8282e6f9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378906"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a><span data-ttu-id="419c7-102">如何：打开放置在 RichTextBox 控件上的文件</span><span class="sxs-lookup"><span data-stu-id="419c7-102">How to: Open a File That is Dropped on a RichTextBox Control</span></span>
<span data-ttu-id="419c7-103">在中[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]，则<xref:System.Windows.Controls.TextBox>， <xref:System.Windows.Controls.RichTextBox>，和<xref:System.Windows.Documents.FlowDocument>控件都具有内置的拖放功能。</span><span class="sxs-lookup"><span data-stu-id="419c7-103">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], the <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> controls all have built-in drag-and-drop functionality.</span></span> <span data-ttu-id="419c7-104">内置功能，可拖放文本内和控件之间。</span><span class="sxs-lookup"><span data-stu-id="419c7-104">The built-in functionality enables drag-and-drop of text within and between the controls.</span></span> <span data-ttu-id="419c7-105">但是，它不会启用通过拖放控件上的文件来打开文件。</span><span class="sxs-lookup"><span data-stu-id="419c7-105">However, it does not enable opening a file by dropping the file on the control.</span></span> <span data-ttu-id="419c7-106">这些控件还会将拖放事件标记为已处理。</span><span class="sxs-lookup"><span data-stu-id="419c7-106">These controls also mark the drag-and-drop events as handled.</span></span> <span data-ttu-id="419c7-107">因此，默认情况下，无法添加你自己的事件处理程序，以提供功能以打开拖放的文件。</span><span class="sxs-lookup"><span data-stu-id="419c7-107">As a result, by default, you cannot add your own event handlers to provide functionality to open dropped files.</span></span>  
  
 <span data-ttu-id="419c7-108">若要在这些控件中添加额外处理拖放事件，请使用<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>方法添加拖放事件在事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="419c7-108">To add additional handling for drag-and-drop events in these controls, use the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method to add your event handlers for the drag-and-drop events.</span></span> <span data-ttu-id="419c7-109">设置`handledEventsToo`参数`true`具有已标记为由事件路由的另一个元素处理的路由事件调用指定的处理程序。</span><span class="sxs-lookup"><span data-stu-id="419c7-109">Set the `handledEventsToo` parameter to `true` to have the specified handler be invoked for a routed event that has already been marked as handled by another element along the event route.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="419c7-110">您可以替换的内置拖放功能<xref:System.Windows.Controls.TextBox>， <xref:System.Windows.Controls.RichTextBox>，和<xref:System.Windows.Documents.FlowDocument>通过处理拖放事件的预览版本并将预览事件标记为已处理。</span><span class="sxs-lookup"><span data-stu-id="419c7-110">You can replace the built-in drag-and-drop functionality of <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> by handling the preview versions of the drag-and-drop events and marking the preview events as handled.</span></span> <span data-ttu-id="419c7-111">但是，这将禁用内置的拖放功能，并且不建议。</span><span class="sxs-lookup"><span data-stu-id="419c7-111">However, this will disable the built-in drag-and-drop functionality, and is not recommended.</span></span>  
  
## <a name="example"></a><span data-ttu-id="419c7-112">示例</span><span class="sxs-lookup"><span data-stu-id="419c7-112">Example</span></span>  
 <span data-ttu-id="419c7-113">下面的示例演示如何将处理程序添加<xref:System.Windows.DragDrop.DragOver>并<xref:System.Windows.DragDrop.Drop>上的事件<xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="419c7-113">The following example demonstrates how to add handlers for the <xref:System.Windows.DragDrop.DragOver> and <xref:System.Windows.DragDrop.Drop> events on a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="419c7-114">此示例使用<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>方法并设置`handledEventsToo`参数`true`，以便将即使调用事件处理程序<xref:System.Windows.Controls.RichTextBox>标记为已处理这些事件。</span><span class="sxs-lookup"><span data-stu-id="419c7-114">This example uses the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method and sets the `handledEventsToo` parameter to `true` so that the events handlers will be invoked even though the <xref:System.Windows.Controls.RichTextBox> marks these events as handled.</span></span> <span data-ttu-id="419c7-115">事件处理程序中的代码的新增功能可打开放置在一个文本文件<xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="419c7-115">The code in the event handlers adds functionality to open a text file that is dropped on the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="419c7-116">若要测试此示例中，将文本文件或丰富文本格式 (RTF) 文件从 Windows 资源管理器到<xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="419c7-116">To test this example, drag a text file or a rich text format (RTF) file from Windows Explorer to the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="419c7-117">该文件将在中打开<xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="419c7-117">The file will be opened in the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="419c7-118">如果按下 SHIFT 键之前删除该文件，将以明文形式打开文件。</span><span class="sxs-lookup"><span data-stu-id="419c7-118">If you press the SHIFT key before the dropping the file, the file will be opened as plain text.</span></span>  
  
 [!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
