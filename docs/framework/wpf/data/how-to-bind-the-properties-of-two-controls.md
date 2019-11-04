---
title: 如何：绑定两个控件的属性
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 66c759c28747de5b0288c906f5d51e4253fb7d52
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459177"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="ab501-102">如何：绑定两个控件的属性</span><span class="sxs-lookup"><span data-stu-id="ab501-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="ab501-103">此示例演示如何使用 <xref:System.Windows.Data.Binding.ElementName%2A> 属性将一个实例化控件的属性绑定到另一个控件的属性。</span><span class="sxs-lookup"><span data-stu-id="ab501-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab501-104">示例</span><span class="sxs-lookup"><span data-stu-id="ab501-104">Example</span></span>  
 <span data-ttu-id="ab501-105">下面的示例演示如何将 <xref:System.Windows.Controls.Canvas> 的 <xref:System.Windows.Controls.Panel.Background%2A> 属性绑定到 <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>。<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="ab501-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="ab501-106"><xref:System.Windows.Controls.ComboBox>的属性：</span><span class="sxs-lookup"><span data-stu-id="ab501-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="ab501-107">当此示例呈现时，应如下所示：</span><span class="sxs-lookup"><span data-stu-id="ab501-107">When this example is rendered it looks like the following:</span></span>  
  
![屏幕截图，其中显示了值为绿色的组合框和绿色正方形。](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="ab501-109">绑定目标属性（在本示例中为 <xref:System.Windows.Controls.Panel.Background%2A> 属性）必须是依赖属性。</span><span class="sxs-lookup"><span data-stu-id="ab501-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="ab501-110">有关详细信息，请参阅 [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ab501-110">For more information, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab501-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab501-111">See also</span></span>

- [<span data-ttu-id="ab501-112">指定绑定源</span><span class="sxs-lookup"><span data-stu-id="ab501-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="ab501-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="ab501-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
