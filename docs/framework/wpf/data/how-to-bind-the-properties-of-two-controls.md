---
title: "如何：绑定两个控件的属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff3da19d33e747ec514de9cd24fa08ccd6ab13bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="9ba98-102">如何：绑定两个控件的属性</span><span class="sxs-lookup"><span data-stu-id="9ba98-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="9ba98-103">此示例演示如何将一个实例化控件的属性绑定到的另一个使用<xref:System.Windows.Data.Binding.ElementName%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="9ba98-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ba98-104">示例</span><span class="sxs-lookup"><span data-stu-id="9ba98-104">Example</span></span>  
 <span data-ttu-id="9ba98-105">下面的示例演示如何将绑定<xref:System.Windows.Controls.Panel.Background%2A>属性<xref:System.Windows.Controls.Canvas>到<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>。<xref:System.Windows.Controls.ContentControl.Content%2A>属性<xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="9ba98-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="9ba98-106">当此示例呈现时，应如下所示：</span><span class="sxs-lookup"><span data-stu-id="9ba98-106">When this example is rendered it looks like the following:</span></span>  
  
 <span data-ttu-id="9ba98-107">![具有绿色背景的画布](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span><span class="sxs-lookup"><span data-stu-id="9ba98-107">![A canvas with a green background](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span></span>  
  
 <span data-ttu-id="9ba98-108">**请注意**绑定目标属性 (在此示例中，<xref:System.Windows.Controls.Panel.Background%2A>属性) 必须是依赖项属性。</span><span class="sxs-lookup"><span data-stu-id="9ba98-108">**Note** The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="9ba98-109">有关详细信息，请参阅 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9ba98-109">For more information, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba98-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ba98-110">See Also</span></span>  
 [<span data-ttu-id="9ba98-111">指定绑定源</span><span class="sxs-lookup"><span data-stu-id="9ba98-111">Specify the Binding Source</span></span>](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)  
 [<span data-ttu-id="9ba98-112">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="9ba98-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
