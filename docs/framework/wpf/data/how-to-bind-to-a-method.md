---
title: "如何：绑定到方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 45f2a141b09c52085c13803b8d338fdc9eebf135
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-method"></a><span data-ttu-id="5d686-102">如何：绑定到方法</span><span class="sxs-lookup"><span data-stu-id="5d686-102">How to: Bind to a Method</span></span>
<span data-ttu-id="5d686-103">下面的示例演示如何将绑定到方法使用<xref:System.Windows.Data.ObjectDataProvider>。</span><span class="sxs-lookup"><span data-stu-id="5d686-103">The following example shows how to bind to a method using <xref:System.Windows.Data.ObjectDataProvider>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d686-104">示例</span><span class="sxs-lookup"><span data-stu-id="5d686-104">Example</span></span>  
 <span data-ttu-id="5d686-105">在本示例中，`TemperatureScale` 是一个具有方法 `ConvertTemp` 的类，该方法接收两个参数（分别为 `double` 和 `enum` 类型的 `TempType)`），并将给定值从一个温标转换为另一个温标。</span><span class="sxs-lookup"><span data-stu-id="5d686-105">In this example, `TemperatureScale` is a class that has a method `ConvertTemp`, which takes two parameters (one of `double` and one of the `enum` type `TempType)` and converts the given value from one temperature scale to another.</span></span> <span data-ttu-id="5d686-106">在下面的示例中，<xref:System.Windows.Data.ObjectDataProvider>用来实例化`TemperatureScale`对象。</span><span class="sxs-lookup"><span data-stu-id="5d686-106">In the following example, an <xref:System.Windows.Data.ObjectDataProvider> is used to instantiate the `TemperatureScale` object.</span></span> <span data-ttu-id="5d686-107">将使用两个指定参数调用 `ConvertTemp` 方法。</span><span class="sxs-lookup"><span data-stu-id="5d686-107">The `ConvertTemp` method is called with two specified parameters.</span></span>  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 <span data-ttu-id="5d686-108">现在方法可以作为资源使用，因此可绑定到其结果。</span><span class="sxs-lookup"><span data-stu-id="5d686-108">Now that the method is available as a resource, you can bind to its results.</span></span> <span data-ttu-id="5d686-109">在下面的示例中，<xref:System.Windows.Controls.TextBox.Text%2A>属性<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>的<xref:System.Windows.Controls.ComboBox>绑定到方法的两个参数。</span><span class="sxs-lookup"><span data-stu-id="5d686-109">In the following example, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> of the <xref:System.Windows.Controls.ComboBox> are bound to the two parameters of the method.</span></span> <span data-ttu-id="5d686-110">这允许用户指定要转换的温度以及要转换自的温标。</span><span class="sxs-lookup"><span data-stu-id="5d686-110">This allows users to specify the temperature to convert and the temperature scale to convert from.</span></span> <span data-ttu-id="5d686-111">请注意，<xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>设置为`true`因为我们要绑定到<xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A>属性<xref:System.Windows.Data.ObjectDataProvider>实例和未包装的对象的属性<xref:System.Windows.Data.ObjectDataProvider>(`TemperatureScale`对象)。</span><span class="sxs-lookup"><span data-stu-id="5d686-111">Note that <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> is set to `true` because we are binding to the <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> property of the <xref:System.Windows.Data.ObjectDataProvider> instance and not properties of the object wrapped by the <xref:System.Windows.Data.ObjectDataProvider> (the `TemperatureScale` object).</span></span>  
  
 <span data-ttu-id="5d686-112"><xref:System.Windows.Controls.ContentControl.Content%2A>的最后一个<xref:System.Windows.Controls.Label>更新在用户修改的内容时<xref:System.Windows.Controls.TextBox>或选定的<xref:System.Windows.Controls.ComboBox>。</span><span class="sxs-lookup"><span data-stu-id="5d686-112">The <xref:System.Windows.Controls.ContentControl.Content%2A> of the last <xref:System.Windows.Controls.Label> updates when the user modifies the content of the <xref:System.Windows.Controls.TextBox> or the selection of the <xref:System.Windows.Controls.ComboBox>.</span></span>  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 <span data-ttu-id="5d686-113">转换器`DoubleToString`采用双精度值并将其转换中的字符串<xref:System.Windows.Data.IValueConverter.Convert%2A>方向 (从绑定源到绑定目标，即<xref:System.Windows.Controls.TextBox.Text%2A>属性)，并将转换`string`到`double`中<xref:System.Windows.Data.IValueConverter.ConvertBack%2A>方向。</span><span class="sxs-lookup"><span data-stu-id="5d686-113">The converter `DoubleToString` takes a double and turns it into a string in the <xref:System.Windows.Data.IValueConverter.Convert%2A> direction (from the binding source to binding target, which is the <xref:System.Windows.Controls.TextBox.Text%2A> property) and converts a `string` to a `double` in the <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> direction.</span></span>  
  
 <span data-ttu-id="5d686-114">`InvalidationCharacterRule`是<xref:System.Windows.Controls.ValidationRule>，用于检查无效字符。</span><span class="sxs-lookup"><span data-stu-id="5d686-114">The `InvalidationCharacterRule` is a <xref:System.Windows.Controls.ValidationRule> that checks for invalid characters.</span></span> <span data-ttu-id="5d686-115">默认的错误模板，这是一个红色边框周围<xref:System.Windows.Controls.TextBox>，显示输入的值不是一个双精度值时通知用户。</span><span class="sxs-lookup"><span data-stu-id="5d686-115">The default error template, which is a red border around the <xref:System.Windows.Controls.TextBox>, appears to notify users when the input value is not a double value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d686-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d686-116">See Also</span></span>  
 [<span data-ttu-id="5d686-117">帮助主题</span><span class="sxs-lookup"><span data-stu-id="5d686-117">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [<span data-ttu-id="5d686-118">绑定到枚举</span><span class="sxs-lookup"><span data-stu-id="5d686-118">Bind to an Enumeration</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)
