---
title: 如何：绑定两个控件的属性
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 332e8e0dfa30ff7aff27c95652f07446baf6511a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754049"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="b72c2-102">如何：绑定两个控件的属性</span><span class="sxs-lookup"><span data-stu-id="b72c2-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="b72c2-103">此示例演示如何使用 <xref:System.Windows.Data.Binding.ElementName%2A> 属性将一个实例化控件的属性绑定到另一个。</span><span class="sxs-lookup"><span data-stu-id="b72c2-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b72c2-104">示例</span><span class="sxs-lookup"><span data-stu-id="b72c2-104">Example</span></span>  
 <span data-ttu-id="b72c2-105">下面的示例演示如何将 <xref:System.Windows.Controls.Canvas> 的 <xref:System.Windows.Controls.Panel.Background%2A> 属性绑定到<xref:System.Windows.Controls.ComboBox> 的 <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> 属性：</span><span class="sxs-lookup"><span data-stu-id="b72c2-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="b72c2-106">属性的<xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="b72c2-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="b72c2-107">当此示例呈现时，应如下所示：</span><span class="sxs-lookup"><span data-stu-id="b72c2-107">When this example is rendered it looks like the following:</span></span>  
  
![绿色的值的框处于选中状态和一个绿色方框显示组合框的屏幕截图。](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="b72c2-109">绑定目标属性 (在此示例中，<xref:System.Windows.Controls.Panel.Background%2A>属性) 必须是依赖属性。</span><span class="sxs-lookup"><span data-stu-id="b72c2-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="b72c2-110">有关详细信息，请参阅[数据绑定概述](data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b72c2-110">For more information, see [Data Binding Overview](data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b72c2-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b72c2-111">See also</span></span>

- [<span data-ttu-id="b72c2-112">指定绑定源</span><span class="sxs-lookup"><span data-stu-id="b72c2-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="b72c2-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="b72c2-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
