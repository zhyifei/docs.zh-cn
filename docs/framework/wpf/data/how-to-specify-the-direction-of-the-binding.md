---
title: "如何：指定绑定的方向"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9944ff214a9dfe12b21e005c4e1998c249bf72b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="6e25c-102">如何：指定绑定的方向</span><span class="sxs-lookup"><span data-stu-id="6e25c-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="6e25c-103">本示例演示如何指定绑定是仅更新绑定目标（目标）属性或绑定源（源）属性，还是同时更新目标属性和源属性。</span><span class="sxs-lookup"><span data-stu-id="6e25c-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e25c-104">示例</span><span class="sxs-lookup"><span data-stu-id="6e25c-104">Example</span></span>  
 <span data-ttu-id="6e25c-105">你使用<xref:System.Windows.Data.Binding.Mode%2A>属性指定绑定的方向。</span><span class="sxs-lookup"><span data-stu-id="6e25c-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="6e25c-106">以下枚举列表显示了可供绑定更新的选项：</span><span class="sxs-lookup"><span data-stu-id="6e25c-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <span data-ttu-id="6e25c-107"><xref:System.Windows.Data.BindingMode.TwoWay>当发生更改时的目标属性或源属性更新目标属性。</span><span class="sxs-lookup"><span data-stu-id="6e25c-107"><xref:System.Windows.Data.BindingMode.TwoWay> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <span data-ttu-id="6e25c-108"><xref:System.Windows.Data.BindingMode.OneWay>仅当源属性更改时，请更新目标属性。</span><span class="sxs-lookup"><span data-stu-id="6e25c-108"><xref:System.Windows.Data.BindingMode.OneWay> updates the target property only when the source property changes.</span></span>  
  
-   <span data-ttu-id="6e25c-109"><xref:System.Windows.Data.BindingMode.OneTime>仅当应用程序启动时或时，请更新目标属性<xref:System.Windows.FrameworkElement.DataContext%2A>发生了更改。</span><span class="sxs-lookup"><span data-stu-id="6e25c-109"><xref:System.Windows.Data.BindingMode.OneTime> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <span data-ttu-id="6e25c-110"><xref:System.Windows.Data.BindingMode.OneWayToSource>目标属性更改时，请更新源属性。</span><span class="sxs-lookup"><span data-stu-id="6e25c-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> updates the source property when the target property changes.</span></span>  
  
-   <span data-ttu-id="6e25c-111"><xref:System.Windows.Data.BindingMode.Default>默认值将导致<xref:System.Windows.Data.Binding.Mode%2A>要使用的目标属性的值。</span><span class="sxs-lookup"><span data-stu-id="6e25c-111"><xref:System.Windows.Data.BindingMode.Default> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="6e25c-112">有关详细信息，请参见 <xref:System.Windows.Data.BindingMode> 枚举。</span><span class="sxs-lookup"><span data-stu-id="6e25c-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="6e25c-113">下面的示例演示如何设置 <xref:System.Windows.Data.Binding.Mode%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="6e25c-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="6e25c-114">若要检测源更改 (适用于<xref:System.Windows.Data.BindingMode.OneWay>和<xref:System.Windows.Data.BindingMode.TwoWay>绑定)，源必须实现适当的属性更改通知机制如<xref:System.ComponentModel.INotifyPropertyChanged>。</span><span class="sxs-lookup"><span data-stu-id="6e25c-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="6e25c-115">请参阅[实现属性更改通知](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)有关的示例<xref:System.ComponentModel.INotifyPropertyChanged>实现。</span><span class="sxs-lookup"><span data-stu-id="6e25c-115">See [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="6e25c-116">有关<xref:System.Windows.Data.BindingMode.TwoWay>或<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定，你可以通过设置控制的源更新的计时<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6e25c-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="6e25c-117">有关更多信息，请参见<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。</span><span class="sxs-lookup"><span data-stu-id="6e25c-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e25c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e25c-118">See Also</span></span>  
 <xref:System.Windows.Data.Binding>  
 [<span data-ttu-id="6e25c-119">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="6e25c-119">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="6e25c-120">帮助主题</span><span class="sxs-lookup"><span data-stu-id="6e25c-120">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
