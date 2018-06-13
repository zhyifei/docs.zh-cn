---
title: 如何：使用焦点事件更改元素的颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: d8d8a3e8b24021cf8a5f916ce3f291a3b66d9411
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543109"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="7e755-102">如何：使用焦点事件更改元素的颜色</span><span class="sxs-lookup"><span data-stu-id="7e755-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="7e755-103">此示例演示如何获取和使用失去焦点时更改元素的颜色<xref:System.Windows.UIElement.GotFocus>和<xref:System.Windows.UIElement.LostFocus>事件。</span><span class="sxs-lookup"><span data-stu-id="7e755-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="7e755-104">此示例组成[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件和代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="7e755-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e755-105">示例</span><span class="sxs-lookup"><span data-stu-id="7e755-105">Example</span></span>  
 <span data-ttu-id="7e755-106">以下[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]创建用户界面，包含两个界面<xref:System.Windows.Controls.Button>对象，并将事件处理程序附加<xref:System.Windows.UIElement.GotFocus>和<xref:System.Windows.UIElement.LostFocus>事件<xref:System.Windows.Controls.Button>对象。</span><span class="sxs-lookup"><span data-stu-id="7e755-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="7e755-107">下面的代码隐藏创建<xref:System.Windows.UIElement.GotFocus>和<xref:System.Windows.UIElement.LostFocus>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7e755-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="7e755-108">当<xref:System.Windows.Controls.Button>提升键盘焦点，<xref:System.Windows.Controls.Control.Background%2A>的<xref:System.Windows.Controls.Button>将变为红色。</span><span class="sxs-lookup"><span data-stu-id="7e755-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="7e755-109">当<xref:System.Windows.Controls.Button>失去键盘焦点时，<xref:System.Windows.Controls.Control.Background%2A>的<xref:System.Windows.Controls.Button>将变回为空白。</span><span class="sxs-lookup"><span data-stu-id="7e755-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="7e755-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e755-110">See Also</span></span>  
 [<span data-ttu-id="7e755-111">输入概述</span><span class="sxs-lookup"><span data-stu-id="7e755-111">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
