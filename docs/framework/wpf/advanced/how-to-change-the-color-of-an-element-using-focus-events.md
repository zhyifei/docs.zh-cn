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
ms.openlocfilehash: 5c59dc5f2f8f26fac69933f9ef641a3a51306619
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004833"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="53cd6-102">如何：使用焦点事件更改元素的颜色</span><span class="sxs-lookup"><span data-stu-id="53cd6-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="53cd6-103">此示例演示如何在使用 <xref:System.Windows.UIElement.GotFocus> 和 <xref:System.Windows.UIElement.LostFocus> 事件时更改元素的颜色，并使其失去焦点。</span><span class="sxs-lookup"><span data-stu-id="53cd6-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="53cd6-104">此示例由一个 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 文件和一个代码隐藏文件组成。</span><span class="sxs-lookup"><span data-stu-id="53cd6-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53cd6-105">示例</span><span class="sxs-lookup"><span data-stu-id="53cd6-105">Example</span></span>  
 <span data-ttu-id="53cd6-106">以下 XAML 创建用户界面，该用户界面由两个 <xref:System.Windows.Controls.Button> 对象组成，并将 <xref:System.Windows.UIElement.GotFocus> 的事件处理程序和 <xref:System.Windows.UIElement.LostFocus> 事件附加到 <xref:System.Windows.Controls.Button> 对象。</span><span class="sxs-lookup"><span data-stu-id="53cd6-106">The following XAML creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="53cd6-107">下面的代码将创建 <xref:System.Windows.UIElement.GotFocus> 和 <xref:System.Windows.UIElement.LostFocus> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="53cd6-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="53cd6-108">当 <xref:System.Windows.Controls.Button> 获得键盘焦点时，<xref:System.Windows.Controls.Button> 的 <xref:System.Windows.Controls.Control.Background%2A> 更改为红色。</span><span class="sxs-lookup"><span data-stu-id="53cd6-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="53cd6-109">当 <xref:System.Windows.Controls.Button> 失去键盘焦点时，<xref:System.Windows.Controls.Button> 的 <xref:System.Windows.Controls.Control.Background%2A> 会改回为白色。</span><span class="sxs-lookup"><span data-stu-id="53cd6-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="53cd6-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53cd6-110">See also</span></span>

- [<span data-ttu-id="53cd6-111">输入概述</span><span class="sxs-lookup"><span data-stu-id="53cd6-111">Input Overview</span></span>](input-overview.md)
