---
title: 如何：绑定两个控件的属性
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 02e71bfcc41fc3d256ea95381ed27d36b289b8f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555576"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="a5c53-102">如何：绑定两个控件的属性</span><span class="sxs-lookup"><span data-stu-id="a5c53-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="a5c53-103">此示例演示如何使用 <xref:System.Windows.Data.Binding.ElementName%2A> 属性将一个实例化控件的属性绑定到另一个。</span><span class="sxs-lookup"><span data-stu-id="a5c53-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5c53-104">示例</span><span class="sxs-lookup"><span data-stu-id="a5c53-104">Example</span></span>  
 <span data-ttu-id="a5c53-105">下面的示例演示如何将绑定<xref:System.Windows.Controls.Panel.Background%2A>属性<xref:System.Windows.Controls.Canvas>到<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>。<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="a5c53-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="a5c53-106">属性<xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="a5c53-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="a5c53-107">当此示例呈现时，应如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5c53-107">When this example is rendered it looks like the following:</span></span>  
  
 <span data-ttu-id="a5c53-108">![具有绿色背景的画布](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span><span class="sxs-lookup"><span data-stu-id="a5c53-108">![A canvas with a green background](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span></span>  
  
 <span data-ttu-id="a5c53-109">**注意** 绑定目标属性（在此示例中为 <xref:System.Windows.Controls.Panel.Background%2A> 属性）必须是依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="a5c53-109">**Note** The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="a5c53-110">有关详细信息，请参阅[数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a5c53-110">For more information, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5c53-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5c53-111">See Also</span></span>  
 [<span data-ttu-id="a5c53-112">指定绑定源</span><span class="sxs-lookup"><span data-stu-id="a5c53-112">Specify the Binding Source</span></span>](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)  
 [<span data-ttu-id="a5c53-113">帮助主题</span><span class="sxs-lookup"><span data-stu-id="a5c53-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
