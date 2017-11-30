---
title: "如何：在 RichTextBox 中定位自定义上下文菜单"
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
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1c0a4fd8d2df15dcca2d9d1751f3089922d9a5ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="ded23-102">如何：在 RichTextBox 中定位自定义上下文菜单</span><span class="sxs-lookup"><span data-stu-id="ded23-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="ded23-103">此示例演示如何将自定义上下文菜单<xref:System.Windows.Controls.RichTextBox>。</span><span class="sxs-lookup"><span data-stu-id="ded23-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="ded23-104">当为 **RichTextBox** 定位自定义上下文菜单时，你负责处理上下文菜单的定位。</span><span class="sxs-lookup"><span data-stu-id="ded23-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="ded23-105">默认情况下，自定义上下文菜单在 **RichTextBox** 的中心打开。</span><span class="sxs-lookup"><span data-stu-id="ded23-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ded23-106">示例</span><span class="sxs-lookup"><span data-stu-id="ded23-106">Example</span></span>  
 <span data-ttu-id="ded23-107">若要重写默认放置行为，将添加的侦听程序<xref:System.Windows.FrameworkContentElement.ContextMenuOpening>事件。</span><span class="sxs-lookup"><span data-stu-id="ded23-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="ded23-108">下面的示例演示如何通过编程方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ded23-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="ded23-109">示例</span><span class="sxs-lookup"><span data-stu-id="ded23-109">Example</span></span>  
 <span data-ttu-id="ded23-110">下面的示例演示实现相应<xref:System.Windows.FrameworkContentElement.ContextMenuOpening>事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="ded23-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="ded23-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ded23-111">See Also</span></span>  
 [<span data-ttu-id="ded23-112">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="ded23-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="ded23-113">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="ded23-113">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
