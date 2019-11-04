---
title: 如何：对控件应用 FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: b44330ee7554f953389556bd62ff49db120b5db9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459816"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="2cadc-102">如何：对控件应用 FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="2cadc-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="2cadc-103">此示例演示如何使用 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 属性在资源中创建焦点视觉样式，并将样式应用于控件。</span><span class="sxs-lookup"><span data-stu-id="2cadc-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cadc-104">示例</span><span class="sxs-lookup"><span data-stu-id="2cadc-104">Example</span></span>  
 <span data-ttu-id="2cadc-105">下面的示例定义了一个样式，该样式创建的附加控件组合仅适用于控件在 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]中的焦点。</span><span class="sxs-lookup"><span data-stu-id="2cadc-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="2cadc-106">这是通过以下方式实现的：使用 <xref:System.Windows.Controls.ControlTemplate>定义样式，然后在设置 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 属性时将该样式作为资源引用。</span><span class="sxs-lookup"><span data-stu-id="2cadc-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="2cadc-107">在矩形区域外放置一个类似于边框的外部矩形。</span><span class="sxs-lookup"><span data-stu-id="2cadc-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="2cadc-108">除非进行了其他修改，否则样式的大小将使用应用了焦点视觉样式的矩形控件的 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 和 <xref:System.Windows.FrameworkElement.ActualWidth%2A>。</span><span class="sxs-lookup"><span data-stu-id="2cadc-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="2cadc-109">此示例为 <xref:System.Windows.FrameworkElement.Margin%2A> 设置负值，使边框在聚焦控件之外稍微显示。</span><span class="sxs-lookup"><span data-stu-id="2cadc-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="2cadc-110"><xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 会附加到任何控件模板样式，无论是显式样式还是主题样式，都是如此。仍可使用 <xref:System.Windows.Controls.ControlTemplate> 创建控件的主样式，并将该样式设置为 <xref:System.Windows.FrameworkElement.Style%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="2cadc-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="2cadc-111">应在主题或 UI 中一致地使用焦点视觉样式，而不是为每个可获得焦点的元素使用不同的样式。</span><span class="sxs-lookup"><span data-stu-id="2cadc-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="2cadc-112">有关详细信息，请参阅为[控件中的焦点设置样式和 FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)。</span><span class="sxs-lookup"><span data-stu-id="2cadc-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cadc-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cadc-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="2cadc-114">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="2cadc-114">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="2cadc-115">为控件中的焦点设置样式以及 FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="2cadc-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
