---
title: 如何：设置 ToolBar 上的控件的样式
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 78b9fc505c3c9045a0ca16ddaa1361c90bcc896a
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459403"
---
# <a name="how-to-style-controls-on-a-toolbar"></a><span data-ttu-id="8315e-102">如何：设置 ToolBar 上的控件的样式</span><span class="sxs-lookup"><span data-stu-id="8315e-102">How to: Style Controls on a ToolBar</span></span>
<span data-ttu-id="8315e-103"><xref:System.Windows.Controls.ToolBar> 定义 <xref:System.Windows.ResourceKey> 对象来指定 <xref:System.Windows.Controls.ToolBar>中控件的样式。</span><span class="sxs-lookup"><span data-stu-id="8315e-103">The <xref:System.Windows.Controls.ToolBar> defines <xref:System.Windows.ResourceKey> objects to specify the style of controls within the <xref:System.Windows.Controls.ToolBar>.</span></span>  <span data-ttu-id="8315e-104">若要设置 <xref:System.Windows.Controls.ToolBar>中的控件的样式，请将样式的 `x:key` 属性设置为 <xref:System.Windows.Controls.ToolBar>中定义的 <xref:System.Windows.ResourceKey>。</span><span class="sxs-lookup"><span data-stu-id="8315e-104">To style a control in a <xref:System.Windows.Controls.ToolBar>, set the `x:key` attribute of the style to a <xref:System.Windows.ResourceKey> defined in <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 <span data-ttu-id="8315e-105"><xref:System.Windows.Controls.ToolBar> 定义以下 <xref:System.Windows.ResourceKey> 对象：</span><span class="sxs-lookup"><span data-stu-id="8315e-105">The <xref:System.Windows.Controls.ToolBar> defines the following <xref:System.Windows.ResourceKey> objects:</span></span>  
  
- <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a><span data-ttu-id="8315e-106">示例</span><span class="sxs-lookup"><span data-stu-id="8315e-106">Example</span></span>  
 <span data-ttu-id="8315e-107">下面的示例为 <xref:System.Windows.Controls.ToolBar>中的控件定义样式。</span><span class="sxs-lookup"><span data-stu-id="8315e-107">The following example defines styles for the controls within a <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a><span data-ttu-id="8315e-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="8315e-108">See also</span></span>

- [<span data-ttu-id="8315e-109">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="8315e-109">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
