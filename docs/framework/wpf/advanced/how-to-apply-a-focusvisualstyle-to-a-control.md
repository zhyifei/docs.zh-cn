---
title: 如何：向控件应用 FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: 53d4984946143c15c4a2b71095529fb5ee7de4b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051320"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="1c7aa-102">如何：向控件应用 FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="1c7aa-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="1c7aa-103">此示例演示如何在资源中创建焦点视觉样式并将样式应用到控件时，使用<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="1c7aa-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c7aa-104">示例</span><span class="sxs-lookup"><span data-stu-id="1c7aa-104">Example</span></span>  
 <span data-ttu-id="1c7aa-105">下面的示例定义的样式，将创建仅在该控件是中的键盘焦点时应用的其他控件组合[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1c7aa-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="1c7aa-106">这通过定义样式与实现<xref:System.Windows.Controls.ControlTemplate>，然后在设置时，为资源引用该样式<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="1c7aa-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="1c7aa-107">类似于边框外部矩形放置之外的矩形区域。</span><span class="sxs-lookup"><span data-stu-id="1c7aa-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="1c7aa-108">除非修改，否则使用的样式的大小调整<xref:System.Windows.FrameworkElement.ActualHeight%2A>和<xref:System.Windows.FrameworkElement.ActualWidth%2A>焦点视觉样式应用的位置的矩形控件。</span><span class="sxs-lookup"><span data-stu-id="1c7aa-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="1c7aa-109">此示例设置值为负值<xref:System.Windows.FrameworkElement.Margin%2A>以使显示稍有外部具有焦点的控件的边框。</span><span class="sxs-lookup"><span data-stu-id="1c7aa-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="1c7aa-110">一个<xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>是附加到提供任何控件模板样式从显式样式或主题样式; 主样式的控件仍可创建使用<xref:System.Windows.Controls.ControlTemplate>并将该样式设置为<xref:System.Windows.FrameworkElement.Style%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="1c7aa-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="1c7aa-111">焦点视觉样式应始终在主题或 UI，而不是使用另一个用于每个可获得焦点的元素。</span><span class="sxs-lookup"><span data-stu-id="1c7aa-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="1c7aa-112">有关详细信息，请参阅[的控件和 FocusVisualStyle 焦点设置样式](styling-for-focus-in-controls-and-focusvisualstyle.md)。</span><span class="sxs-lookup"><span data-stu-id="1c7aa-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7aa-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c7aa-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="1c7aa-114">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="1c7aa-114">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="1c7aa-115">为控件中的焦点设置样式以及 FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="1c7aa-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
