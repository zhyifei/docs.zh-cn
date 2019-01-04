---
title: 如何：绑定到枚举
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 921f15a32eeb5ccb20e879466fcfee3233bbd29e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554942"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="a6ce1-102">如何：绑定到枚举</span><span class="sxs-lookup"><span data-stu-id="a6ce1-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="a6ce1-103">此示例演示如何将绑定到通过绑定到枚举的 GetValues 方法的枚举。</span><span class="sxs-lookup"><span data-stu-id="a6ce1-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6ce1-104">示例</span><span class="sxs-lookup"><span data-stu-id="a6ce1-104">Example</span></span>  
 <span data-ttu-id="a6ce1-105">在下面的示例中，<xref:System.Windows.Controls.ListBox> 通过数据绑定来显示 <xref:System.Windows.HorizontalAlignment> 的枚举值列表。</span><span class="sxs-lookup"><span data-stu-id="a6ce1-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="a6ce1-106"><xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.Button> 已进行绑定，目的是使你可以通过选择 <xref:System.Windows.Controls.ListBox> 中的值来更改 <xref:System.Windows.Controls.Button> 的 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性值。</span><span class="sxs-lookup"><span data-stu-id="a6ce1-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="a6ce1-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6ce1-107">See Also</span></span>  
 [<span data-ttu-id="a6ce1-108">绑定到方法</span><span class="sxs-lookup"><span data-stu-id="a6ce1-108">Bind to a Method</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [<span data-ttu-id="a6ce1-109">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="a6ce1-109">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="a6ce1-110">帮助主题</span><span class="sxs-lookup"><span data-stu-id="a6ce1-110">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
