---
title: 如何：绑定到方法
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 6cdad46fd6d9ef3bc4ce1a13fedb6ff1d639d93e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123235"
---
# <a name="how-to-bind-to-a-method"></a><span data-ttu-id="afb77-102">如何：绑定到方法</span><span class="sxs-lookup"><span data-stu-id="afb77-102">How to: Bind to a Method</span></span>
<span data-ttu-id="afb77-103">下面的示例演示如何将绑定到方法使用<xref:System.Windows.Data.ObjectDataProvider>。</span><span class="sxs-lookup"><span data-stu-id="afb77-103">The following example shows how to bind to a method using <xref:System.Windows.Data.ObjectDataProvider>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afb77-104">示例</span><span class="sxs-lookup"><span data-stu-id="afb77-104">Example</span></span>  
 <span data-ttu-id="afb77-105">在本示例中，`TemperatureScale` 是一个具有 `ConvertTemp` 方法的类，该方法接收两个参数（分别为 `double` 和 `enum` 类型的 `TempType)`），将给定值从一个温标转换为另一个温标。</span><span class="sxs-lookup"><span data-stu-id="afb77-105">In this example, `TemperatureScale` is a class that has a method `ConvertTemp`, which takes two parameters (one of `double` and one of the `enum` type `TempType)` and converts the given value from one temperature scale to another.</span></span> <span data-ttu-id="afb77-106">在以下示例中，<xref:System.Windows.Data.ObjectDataProvider> 用来实例化 `TemperatureScale` 对象。</span><span class="sxs-lookup"><span data-stu-id="afb77-106">In the following example, an <xref:System.Windows.Data.ObjectDataProvider> is used to instantiate the `TemperatureScale` object.</span></span> <span data-ttu-id="afb77-107">将使用两个指定参数调用 `ConvertTemp` 方法。</span><span class="sxs-lookup"><span data-stu-id="afb77-107">The `ConvertTemp` method is called with two specified parameters.</span></span>  
  
 [!code-xaml[BindToMethod#WindowResources](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 <span data-ttu-id="afb77-108">现在此方法可以作为资源使用，因此可绑定到其结果。</span><span class="sxs-lookup"><span data-stu-id="afb77-108">Now that the method is available as a resource, you can bind to its results.</span></span> <span data-ttu-id="afb77-109">在以下示例中，<xref:System.Windows.Controls.TextBox> 的 <xref:System.Windows.Controls.TextBox.Text%2A> 属性和 <xref:System.Windows.Controls.ComboBox> 的 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 绑定到该方法的两个参数。</span><span class="sxs-lookup"><span data-stu-id="afb77-109">In the following example, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> of the <xref:System.Windows.Controls.ComboBox> are bound to the two parameters of the method.</span></span> <span data-ttu-id="afb77-110">这样用户就可以指定要转换的温度以及要从哪个温标进行转换。</span><span class="sxs-lookup"><span data-stu-id="afb77-110">This allows users to specify the temperature to convert and the temperature scale to convert from.</span></span> <span data-ttu-id="afb77-111">注意，<xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> 设置为 `true` 是因为我们要绑定到 <xref:System.Windows.Data.ObjectDataProvider> 实例的 <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> 属性，而不是由 <xref:System.Windows.Data.ObjectDataProvider> 包装的对象（`TemperatureScale`对象）的属性。</span><span class="sxs-lookup"><span data-stu-id="afb77-111">Note that <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> is set to `true` because we are binding to the <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> property of the <xref:System.Windows.Data.ObjectDataProvider> instance and not properties of the object wrapped by the <xref:System.Windows.Data.ObjectDataProvider> (the `TemperatureScale` object).</span></span>  
  
 <span data-ttu-id="afb77-112">最后一个 <xref:System.Windows.Controls.Label> 的 <xref:System.Windows.Controls.ContentControl.Content%2A> 会在用户修改 <xref:System.Windows.Controls.TextBox> 的内容或 <xref:System.Windows.Controls.ComboBox> 的选项时更新。</span><span class="sxs-lookup"><span data-stu-id="afb77-112">The <xref:System.Windows.Controls.ContentControl.Content%2A> of the last <xref:System.Windows.Controls.Label> updates when the user modifies the content of the <xref:System.Windows.Controls.TextBox> or the selection of the <xref:System.Windows.Controls.ComboBox>.</span></span>  
  
 [!code-xaml[BindToMethod#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 <span data-ttu-id="afb77-113">`DoubleToString` 转换器在 <xref:System.Windows.Data.IValueConverter.Convert%2A> 方向接受一个双精度值并将其转换为字符串（从绑定源到绑定目标，后者为 <xref:System.Windows.Controls.TextBox.Text%2A> 属性），在<xref:System.Windows.Data.IValueConverter.ConvertBack%2A> 方向将 `string` 转换为 `double`。</span><span class="sxs-lookup"><span data-stu-id="afb77-113">The converter `DoubleToString` takes a double and turns it into a string in the <xref:System.Windows.Data.IValueConverter.Convert%2A> direction (from the binding source to binding target, which is the <xref:System.Windows.Controls.TextBox.Text%2A> property) and converts a `string` to a `double` in the <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> direction.</span></span>  
  
 <span data-ttu-id="afb77-114">`InvalidationCharacterRule` 是一个 <xref:System.Windows.Controls.ValidationRule>，用于检查无效字符。</span><span class="sxs-lookup"><span data-stu-id="afb77-114">The `InvalidationCharacterRule` is a <xref:System.Windows.Controls.ValidationRule> that checks for invalid characters.</span></span> <span data-ttu-id="afb77-115">当输入值不是一个 `double` 值时，默认错误模板（一个围绕 <xref:System.Windows.Controls.TextBox> 的红色边框）将出现，对用户进行通知。</span><span class="sxs-lookup"><span data-stu-id="afb77-115">The default error template, which is a red border around the <xref:System.Windows.Controls.TextBox>, appears to notify users when the input value is not a double value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb77-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="afb77-116">See also</span></span>

- [<span data-ttu-id="afb77-117">帮助主题</span><span class="sxs-lookup"><span data-stu-id="afb77-117">How-to Topics</span></span>](data-binding-how-to-topics.md)
- [<span data-ttu-id="afb77-118">绑定到枚举</span><span class="sxs-lookup"><span data-stu-id="afb77-118">Bind to an Enumeration</span></span>](how-to-bind-to-an-enumeration.md)
