---
title: 如何：控制文本框文本更新源的时间
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: b211eb67e3bac95f74255935a39cc0d6aec61531
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974786"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a><span data-ttu-id="fef1d-102">如何：控制文本框文本更新源的时间</span><span class="sxs-lookup"><span data-stu-id="fef1d-102">How to: Control When the TextBox Text Updates the Source</span></span>
<span data-ttu-id="fef1d-103">本主题介绍如何使用 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 属性控制绑定源更新的计时。</span><span class="sxs-lookup"><span data-stu-id="fef1d-103">This topic describes how to use the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property to control the timing of binding source updates.</span></span> <span data-ttu-id="fef1d-104">本主题使用 <xref:System.Windows.Controls.TextBox> 控件作为示例。</span><span class="sxs-lookup"><span data-stu-id="fef1d-104">The topic uses the <xref:System.Windows.Controls.TextBox> control as an example.</span></span>

## <a name="example"></a><span data-ttu-id="fef1d-105">示例</span><span class="sxs-lookup"><span data-stu-id="fef1d-105">Example</span></span>
 <span data-ttu-id="fef1d-106"><xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 属性的默认 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 值为 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>。</span><span class="sxs-lookup"><span data-stu-id="fef1d-106">The <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property has a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span> <span data-ttu-id="fef1d-107">这意味着，如果应用程序具有包含数据绑定 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 属性的 <xref:System.Windows.Controls.TextBox>，则键入 <xref:System.Windows.Controls.TextBox> 的文本将不会更新源，直到 <xref:System.Windows.Controls.TextBox> 失去焦点为止（例如，当您单击 <xref:System.Windows.Controls.TextBox>上的 "离开" 时）。</span><span class="sxs-lookup"><span data-stu-id="fef1d-107">This means if an application has a <xref:System.Windows.Controls.TextBox> with a data-bound <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property, the text you type into the <xref:System.Windows.Controls.TextBox> does not update the source until the <xref:System.Windows.Controls.TextBox> loses focus (for instance, when you click away from the <xref:System.Windows.Controls.TextBox>).</span></span>

 <span data-ttu-id="fef1d-108">如果希望在键入时更新源，请将绑定的 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 设置为 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。</span><span class="sxs-lookup"><span data-stu-id="fef1d-108">If you want the source to be updated as you type, set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> of the binding to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="fef1d-109">在下面的示例中，突出显示的代码行显示 <xref:System.Windows.Controls.TextBox> 和 <xref:System.Windows.Controls.TextBlock> 的 `Text` 属性都绑定到同一个源属性。</span><span class="sxs-lookup"><span data-stu-id="fef1d-109">In the following example, the highlighted lines of code show that the `Text` properties of both the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.TextBlock> are bound to the same source property.</span></span> <span data-ttu-id="fef1d-110"><xref:System.Windows.Controls.TextBox> 绑定的 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 属性设置为 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。</span><span class="sxs-lookup"><span data-stu-id="fef1d-110">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property of the <xref:System.Windows.Controls.TextBox> binding is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 <span data-ttu-id="fef1d-111">因此，当用户向 <xref:System.Windows.Controls.TextBox>中输入文本时，<xref:System.Windows.Controls.TextBlock> 会显示相同的文本（因为源发生更改），如以下示例屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="fef1d-111">As a result, the <xref:System.Windows.Controls.TextBlock> shows the same text (because the source changes) as the user enters text into the <xref:System.Windows.Controls.TextBox>, as illustrated by the following screenshot of the sample:</span></span>

 ![显示简单数据绑定的屏幕截图。](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 <span data-ttu-id="fef1d-113">如果您有一个对话框或用户可编辑的窗体，而您希望在用户完成编辑字段并单击 "确定" 之前延迟源更新，则可以将绑定的 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 值设置为 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="fef1d-113">If you have a dialog or a user-editable form and you want to defer source updates until the user is finished editing the fields and clicks "OK", you can set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of your bindings to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, as in the following example:</span></span>

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 <span data-ttu-id="fef1d-114">将 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 值设置为 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>时，源值仅在应用程序调用 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 方法时才会发生更改。</span><span class="sxs-lookup"><span data-stu-id="fef1d-114">When you set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, the source value only changes when the application calls the <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> method.</span></span> <span data-ttu-id="fef1d-115">下面的示例演示如何为 `itemNameTextBox`调用 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>：</span><span class="sxs-lookup"><span data-stu-id="fef1d-115">The following example shows how to call <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> for `itemNameTextBox`:</span></span>

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> <span data-ttu-id="fef1d-116">您可以为其他控件的属性使用相同的技术，但请记住，大多数其他属性的默认 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 值都为 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。</span><span class="sxs-lookup"><span data-stu-id="fef1d-116">You can use the same technique for properties of other controls, but keep in mind that most other properties have a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="fef1d-117">有关详细信息，请参阅 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 属性页。</span><span class="sxs-lookup"><span data-stu-id="fef1d-117">For more information, see the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property page.</span></span>

> [!NOTE]
> <span data-ttu-id="fef1d-118"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 属性处理源更新，因此仅适用于 <xref:System.Windows.Data.BindingMode.TwoWay> 或 <xref:System.Windows.Data.BindingMode.OneWayToSource> 绑定。</span><span class="sxs-lookup"><span data-stu-id="fef1d-118">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property deals with source updates and therefore is only relevant for <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings.</span></span> <span data-ttu-id="fef1d-119">要使 <xref:System.Windows.Data.BindingMode.TwoWay> 和 <xref:System.Windows.Data.BindingMode.OneWayToSource> 绑定正常工作，源对象需要提供属性更改通知。</span><span class="sxs-lookup"><span data-stu-id="fef1d-119">For <xref:System.Windows.Data.BindingMode.TwoWay> and <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings to work, the source object needs to provide property change notifications.</span></span> <span data-ttu-id="fef1d-120">有关详细信息，可以参见本主题中引用的示例。</span><span class="sxs-lookup"><span data-stu-id="fef1d-120">You can refer to the samples cited in this topic for more information.</span></span> <span data-ttu-id="fef1d-121">此外，也可以参见[实现属性更改通知](how-to-implement-property-change-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="fef1d-121">In addition, you can look at [Implement Property Change Notification](how-to-implement-property-change-notification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fef1d-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="fef1d-122">See also</span></span>

- [<span data-ttu-id="fef1d-123">帮助主题</span><span class="sxs-lookup"><span data-stu-id="fef1d-123">How-to Topics</span></span>](data-binding-how-to-topics.md)
