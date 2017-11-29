---
title: "如何：控制文本框文本更新源的时间"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c923a24f5abfdb059a436206a15181a67d03068f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a><span data-ttu-id="62ec3-102">如何：控制文本框文本更新源的时间</span><span class="sxs-lookup"><span data-stu-id="62ec3-102">How to: Control When the TextBox Text Updates the Source</span></span>
<span data-ttu-id="62ec3-103">本主题介绍如何使用<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性控制绑定源更新的计时。</span><span class="sxs-lookup"><span data-stu-id="62ec3-103">This topic describes how to use the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property to control the timing of binding source updates.</span></span> <span data-ttu-id="62ec3-104">本主题使用<xref:System.Windows.Controls.TextBox>控件作为示例。</span><span class="sxs-lookup"><span data-stu-id="62ec3-104">The topic uses the <xref:System.Windows.Controls.TextBox> control as an example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62ec3-105">示例</span><span class="sxs-lookup"><span data-stu-id="62ec3-105">Example</span></span>  
 <span data-ttu-id="62ec3-106"><xref:System.Windows.Controls.TextBox>。<xref:System.Windows.Controls.TextBox.Text%2A>属性具有一个默认<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>值<xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>。</span><span class="sxs-lookup"><span data-stu-id="62ec3-106">The <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property has a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span> <span data-ttu-id="62ec3-107">这意味着应用程序是否已<xref:System.Windows.Controls.TextBox>与数据绑定<xref:System.Windows.Controls.TextBox>。<xref:System.Windows.Controls.TextBox.Text%2A>属性，你键入的文本<xref:System.Windows.Controls.TextBox>不会更新直到源<xref:System.Windows.Controls.TextBox>失去焦点 （例如，当你单击即可<xref:System.Windows.Controls.TextBox>).</span><span class="sxs-lookup"><span data-stu-id="62ec3-107">This means if an application has a <xref:System.Windows.Controls.TextBox> with a data-bound <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property, the text you type into the <xref:System.Windows.Controls.TextBox> does not update the source until the <xref:System.Windows.Controls.TextBox> loses focus (for instance, when you click away from the <xref:System.Windows.Controls.TextBox>).</span></span>  
  
 <span data-ttu-id="62ec3-108">如果你想要获取作为更新的源进行键入时，请将设置<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>绑定到的<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。</span><span class="sxs-lookup"><span data-stu-id="62ec3-108">If you want the source to get updated as you are typing, set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> of the binding to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="62ec3-109">在下面的示例中，`Text`属性<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.TextBlock>绑定到相同的源属性。</span><span class="sxs-lookup"><span data-stu-id="62ec3-109">In the following example, the `Text` properties of both the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.TextBlock> are bound to the same source property.</span></span> <span data-ttu-id="62ec3-110"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性<xref:System.Windows.Controls.TextBox>绑定设置为<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。</span><span class="sxs-lookup"><span data-stu-id="62ec3-110">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property of the <xref:System.Windows.Controls.TextBox> binding is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#usthowto)]  
  
 <span data-ttu-id="62ec3-111">因此，<xref:System.Windows.Controls.TextBlock>显示相同的文本 （因为源更改） 在用户输入到文本时<xref:System.Windows.Controls.TextBox>，如下面的屏幕截图中的示例所示：</span><span class="sxs-lookup"><span data-stu-id="62ec3-111">As a result, the <xref:System.Windows.Controls.TextBlock> shows the same text (because the source changes) as the user enters text into the <xref:System.Windows.Controls.TextBox>, as illustrated by the following screenshot of the sample:</span></span>  
  
 <span data-ttu-id="62ec3-112">![简单数据绑定示例屏幕快照](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span><span class="sxs-lookup"><span data-stu-id="62ec3-112">![Simple data binding sample screen shot](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span></span>  
  
 <span data-ttu-id="62ec3-113">如果你有一个对话框或用户可编辑窗体，并且您想要延迟源更新，直到用户完成字段的编辑，并单击"确定"，你可以设置<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>你绑定到值<xref:System.Windows.Data.UpdateSourceTrigger.Explicit>，下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="62ec3-113">If you have a dialog or a user-editable form and you want to defer source updates until the user is finished editing the fields and clicks "OK", you can set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of your bindings to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, as in the following example:</span></span>  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="62ec3-114">当你将设置<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>值赋给<xref:System.Windows.Data.UpdateSourceTrigger.Explicit>，源值只会更改时在应用程序调用<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="62ec3-114">When you set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, the source value only changes when the application calls the <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> method.</span></span> <span data-ttu-id="62ec3-115">下面的示例演示如何调用<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>为`itemNameTextBox`:</span><span class="sxs-lookup"><span data-stu-id="62ec3-115">The following example shows how to call <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> for `itemNameTextBox`:</span></span>  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="62ec3-116">你可以使用其他控件的属性相同的技术，但请记住其他大多数属性具有默认值<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>值<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>。</span><span class="sxs-lookup"><span data-stu-id="62ec3-116">You can use the same technique for properties of other controls, but keep in mind that most other properties have a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="62ec3-117">有关详细信息，请参阅<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性页。</span><span class="sxs-lookup"><span data-stu-id="62ec3-117">For more information, see the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62ec3-118"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>属性用于处理源更新并且因此仅适用于<xref:System.Windows.Data.BindingMode.TwoWay>或<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定。</span><span class="sxs-lookup"><span data-stu-id="62ec3-118">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property deals with source updates and therefore is only relevant for <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings.</span></span> <span data-ttu-id="62ec3-119">有关<xref:System.Windows.Data.BindingMode.TwoWay>和<xref:System.Windows.Data.BindingMode.OneWayToSource>绑定生效，需要提供属性更改通知将源对象。</span><span class="sxs-lookup"><span data-stu-id="62ec3-119">For <xref:System.Windows.Data.BindingMode.TwoWay> and <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings to work, the source object needs to provide property change notifications.</span></span> <span data-ttu-id="62ec3-120">有关详细信息，可以参见本主题中引用的示例。</span><span class="sxs-lookup"><span data-stu-id="62ec3-120">You can refer to the samples cited in this topic for more information.</span></span> <span data-ttu-id="62ec3-121">此外，也可以参见[实现属性更改通知](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)。</span><span class="sxs-lookup"><span data-stu-id="62ec3-121">In addition, you can look at [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ec3-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62ec3-122">See Also</span></span>  
 [<span data-ttu-id="62ec3-123">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="62ec3-123">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
