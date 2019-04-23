---
title: 如何：实现绑定验证
ms.date: 03/30/2017
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 3950df8b6f4b48a035c6ebf37d8d65c18cb82e1e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197212"
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="d561d-102">如何：实现绑定验证</span><span class="sxs-lookup"><span data-stu-id="d561d-102">How to: Implement Binding Validation</span></span>
<span data-ttu-id="d561d-103">此示例演示如何在用户输入无效值后，基于自定义验证规则使用 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 和样式触发器来提供视觉反馈，以便通知用户。</span><span class="sxs-lookup"><span data-stu-id="d561d-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d561d-104">示例</span><span class="sxs-lookup"><span data-stu-id="d561d-104">Example</span></span>  
 <span data-ttu-id="d561d-105">在下面的示例中，<xref:System.Windows.Controls.TextBox> 的文本内容绑定到一个名为 `ods` 的绑定源对象的 `Age` 属性（类型为 int) 。</span><span class="sxs-lookup"><span data-stu-id="d561d-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="d561d-106">该绑定已设置为使用名为 `AgeRangeRule` 的验证规则。因此，当用户输入了非数值字符或输入的值小于 21 或者大于 130 时，文本框旁边会显示一个红色感叹号，而当用户将鼠标移动到该文本框上时，会显示包含错误消息的工具提示。</span><span class="sxs-lookup"><span data-stu-id="d561d-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>  
  
 [!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="d561d-107">下面的示例演示如何实现 `AgeRangeRule`，它继承 <xref:System.Windows.Controls.ValidationRule> 并重写 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="d561d-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="d561d-108">对值调用 Int32.Parse() 方法是为了确保该值不包含任何无效字符。</span><span class="sxs-lookup"><span data-stu-id="d561d-108">The Int32.Parse() method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="d561d-109"><xref:System.Windows.Controls.ValidationRule.Validate%2A> 方法将返回 <xref:System.Windows.Controls.ValidationResult>，该返回结果指示值是否有效（根据是否在分析期间捕获了异常，以及年龄值是否超出了下限和上限）。</span><span class="sxs-lookup"><span data-stu-id="d561d-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>  
  
 [!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 <span data-ttu-id="d561d-110">下面的示例演示了自定义 <xref:System.Windows.Controls.ControlTemplate> `validationTemplate`，后者会创建一个红色感叹号来通知用户存在验证错误。</span><span class="sxs-lookup"><span data-stu-id="d561d-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="d561d-111">控件模板用于重新定义控件的外观。</span><span class="sxs-lookup"><span data-stu-id="d561d-111">Control templates are used to redefine the appearance of a control.</span></span>  
  
 [!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 <span data-ttu-id="d561d-112">如以下示例所示，显示错误消息的 <xref:System.Windows.Controls.ToolTip> 是通过名为 `textBoxInError` 的样式创建的。</span><span class="sxs-lookup"><span data-stu-id="d561d-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="d561d-113">如果 <xref:System.Windows.Controls.Validation.HasError%2A> 的值是 `true`，该触发器会将当前 <xref:System.Windows.Controls.TextBox> 的工具提示设置为其第一个验证错误。</span><span class="sxs-lookup"><span data-stu-id="d561d-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="d561d-114"><xref:System.Windows.Data.Binding.RelativeSource%2A> 设置为 <xref:System.Windows.Data.RelativeSourceMode.Self>，用于引用当前元素。</span><span class="sxs-lookup"><span data-stu-id="d561d-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>  
  
 [!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 <span data-ttu-id="d561d-115">有关完整示例，请参阅[绑定验证示例](https://go.microsoft.com/fwlink/?LinkID=159972)。</span><span class="sxs-lookup"><span data-stu-id="d561d-115">For the complete example, see [Binding Validation Sample](https://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
 <span data-ttu-id="d561d-116">请注意，如果未提供自定义 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>，则当验证出错时,系统会使用默认错误模板向用户提供可视反馈。</span><span class="sxs-lookup"><span data-stu-id="d561d-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="d561d-117">有关详细信息，请参阅[数据绑定概述](data-binding-overview.md)中的“数据验证”。</span><span class="sxs-lookup"><span data-stu-id="d561d-117">See "Data Validation" in [Data Binding Overview](data-binding-overview.md) for more information.</span></span> <span data-ttu-id="d561d-118">另外，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 还提供了内置验证规则，该规则捕获在更新绑定源属性期间引发的异常。</span><span class="sxs-lookup"><span data-stu-id="d561d-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="d561d-119">有关详细信息，请参阅 <xref:System.Windows.Controls.ExceptionValidationRule>。</span><span class="sxs-lookup"><span data-stu-id="d561d-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d561d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d561d-120">See also</span></span>

- [<span data-ttu-id="d561d-121">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="d561d-121">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="d561d-122">帮助主题</span><span class="sxs-lookup"><span data-stu-id="d561d-122">How-to Topics</span></span>](data-binding-how-to-topics.md)
