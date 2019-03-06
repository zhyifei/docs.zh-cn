---
title: 如何：在 RichTextBox 中定位自定义上下文菜单
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: abb5bbb5d5a537b14f334782e87fa7caf0c7976f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367867"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="58068-102">如何：在 RichTextBox 中定位自定义上下文菜单</span><span class="sxs-lookup"><span data-stu-id="58068-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="58068-103">此示例演示如何定位自定义上下文菜单的<xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="58068-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="58068-104">当为 **RichTextBox** 定位自定义上下文菜单时，你负责处理上下文菜单的定位。</span><span class="sxs-lookup"><span data-stu-id="58068-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="58068-105">默认情况下，自定义上下文菜单在 **RichTextBox** 的中心打开。</span><span class="sxs-lookup"><span data-stu-id="58068-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58068-106">示例</span><span class="sxs-lookup"><span data-stu-id="58068-106">Example</span></span>  
 <span data-ttu-id="58068-107">若要重写默认定位行为，将添加的侦听程序<xref:System.Windows.FrameworkContentElement.ContextMenuOpening>事件。</span><span class="sxs-lookup"><span data-stu-id="58068-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="58068-108">下面的示例演示如何通过编程方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="58068-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="58068-109">示例</span><span class="sxs-lookup"><span data-stu-id="58068-109">Example</span></span>  
 <span data-ttu-id="58068-110">下面的示例显示了实现相应<xref:System.Windows.FrameworkContentElement.ContextMenuOpening>事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="58068-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="58068-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="58068-111">See also</span></span>
- [<span data-ttu-id="58068-112">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="58068-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="58068-113">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="58068-113">TextBox Overview</span></span>](textbox-overview.md)
