---
title: 如何：指定绑定方向
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 4334ed178e7f2ed90928db6b434eb8c9fee77bf7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931475"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="826bc-102">如何：指定绑定方向</span><span class="sxs-lookup"><span data-stu-id="826bc-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="826bc-103">本示例演示如何指定绑定是仅更新绑定目标（目标）属性或绑定源（源）属性，还是同时更新目标属性和源属性。</span><span class="sxs-lookup"><span data-stu-id="826bc-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="826bc-104">示例</span><span class="sxs-lookup"><span data-stu-id="826bc-104">Example</span></span>  
 <span data-ttu-id="826bc-105">使用<xref:System.Windows.Data.Binding.Mode%2A>属性指定绑定的方向。</span><span class="sxs-lookup"><span data-stu-id="826bc-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="826bc-106">以下枚举列表显示了可供绑定更新的选项：</span><span class="sxs-lookup"><span data-stu-id="826bc-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
- <span data-ttu-id="826bc-107"><xref:System.Windows.Data.BindingMode.TwoWay> 会在目标属性或源属性更改时进行目标属性或源属性的更新。</span><span class="sxs-lookup"><span data-stu-id="826bc-107"><xref:System.Windows.Data.BindingMode.TwoWay> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="826bc-108"><xref:System.Windows.Data.BindingMode.OneWay> 仅当源属性更改时更新目标属性。</span><span class="sxs-lookup"><span data-stu-id="826bc-108"><xref:System.Windows.Data.BindingMode.OneWay> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="826bc-109"><xref:System.Windows.Data.BindingMode.OneTime> 仅当应用程序启动时或<xref:System.Windows.FrameworkElement.DataContext%2A>发生更改时更新目标属性。</span><span class="sxs-lookup"><span data-stu-id="826bc-109"><xref:System.Windows.Data.BindingMode.OneTime> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="826bc-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> 在目标属性更改时更新源属性。</span><span class="sxs-lookup"><span data-stu-id="826bc-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="826bc-111"><xref:System.Windows.Data.BindingMode.Default> 迫使系统将使用目标属性的默认 <xref:System.Windows.Data.Binding.Mode%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="826bc-111"><xref:System.Windows.Data.BindingMode.Default> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="826bc-112">有关详细信息，请参见 <xref:System.Windows.Data.BindingMode> 枚举。</span><span class="sxs-lookup"><span data-stu-id="826bc-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="826bc-113">下面的示例演示如何设置 <xref:System.Windows.Data.Binding.Mode%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="826bc-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="826bc-114">若要检测源更改 (适用于<xref:System.Windows.Data.BindingMode.OneWay>并<xref:System.Windows.Data.BindingMode.TwoWay>绑定)，源必须实现一种合适的属性更改通知机制如<xref:System.ComponentModel.INotifyPropertyChanged>。</span><span class="sxs-lookup"><span data-stu-id="826bc-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="826bc-115">请参阅[实现属性更改通知](how-to-implement-property-change-notification.md)有关的示例<xref:System.ComponentModel.INotifyPropertyChanged>实现。</span><span class="sxs-lookup"><span data-stu-id="826bc-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="826bc-116">有关<xref:System.Windows.Data.BindingMode.TwoWay>或<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定的更多信息，您可以通过设置控制源更新的计时<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="826bc-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="826bc-117">有关更多信息，请参见<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>。</span><span class="sxs-lookup"><span data-stu-id="826bc-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="826bc-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="826bc-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="826bc-119">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="826bc-119">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="826bc-120">帮助主题</span><span class="sxs-lookup"><span data-stu-id="826bc-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
