---
title: 如何：设置 ToolBar 上的控件的样式
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 097bb23a41ba68bf9c121a53920f19694508348b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544856"
---
# <a name="how-to-style-controls-on-a-toolbar"></a><span data-ttu-id="8ab86-102">如何：设置 ToolBar 上的控件的样式</span><span class="sxs-lookup"><span data-stu-id="8ab86-102">How to: Style Controls on a ToolBar</span></span>
<span data-ttu-id="8ab86-103"><xref:System.Windows.Controls.ToolBar>定义<xref:System.Windows.ResourceKey>对象来指定中的控件的样式<xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="8ab86-103">The <xref:System.Windows.Controls.ToolBar> defines <xref:System.Windows.ResourceKey> objects to specify the style of controls within the <xref:System.Windows.Controls.ToolBar>.</span></span>  <span data-ttu-id="8ab86-104">若要设置样式中的控件<xref:System.Windows.Controls.ToolBar>，将`x:key`到样式属性<xref:System.Windows.ResourceKey>中定义<xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="8ab86-104">To style a control in a <xref:System.Windows.Controls.ToolBar>, set the `x:key` attribute of the style to a <xref:System.Windows.ResourceKey> defined in <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 <span data-ttu-id="8ab86-105"><xref:System.Windows.Controls.ToolBar>定义了以下<xref:System.Windows.ResourceKey>对象：</span><span class="sxs-lookup"><span data-stu-id="8ab86-105">The <xref:System.Windows.Controls.ToolBar> defines the following <xref:System.Windows.ResourceKey> objects:</span></span>  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a><span data-ttu-id="8ab86-106">示例</span><span class="sxs-lookup"><span data-stu-id="8ab86-106">Example</span></span>  
 <span data-ttu-id="8ab86-107">下面的示例定义内的控件的样式<xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="8ab86-107">The following example defines styles for the controls within a <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a><span data-ttu-id="8ab86-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ab86-108">See also</span></span>
- [<span data-ttu-id="8ab86-109">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="8ab86-109">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
