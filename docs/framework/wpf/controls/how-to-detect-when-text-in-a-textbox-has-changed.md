---
title: 如何：检测 TextBox 中的文本何时更改
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1befd18220488334319a55bce2ce602aef20d3d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552947"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="650aa-102">如何：检测 TextBox 中的文本何时更改</span><span class="sxs-lookup"><span data-stu-id="650aa-102">How to: Detect When Text in a TextBox Has Changed</span></span>
<span data-ttu-id="650aa-103">此示例演示使用一种方法<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>事件来执行方法时中的文本<xref:System.Windows.Controls.TextBox>控制已更改。</span><span class="sxs-lookup"><span data-stu-id="650aa-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>  
  
 <span data-ttu-id="650aa-104">中的代码隐藏类[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]包含<xref:System.Windows.Controls.TextBox>控件，你想要监视的更改，插入要每当调用的方法<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>事件激发。</span><span class="sxs-lookup"><span data-stu-id="650aa-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="650aa-105">此方法必须具有的签名匹配的预期内容<xref:System.Windows.Controls.TextChangedEventHandler>委托。</span><span class="sxs-lookup"><span data-stu-id="650aa-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 <span data-ttu-id="650aa-106">会调用事件处理程序时的内容<xref:System.Windows.Controls.TextBox>由用户或以编程方式更改控制。</span><span class="sxs-lookup"><span data-stu-id="650aa-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="650aa-107">**注意：** 时将激发此事件<xref:System.Windows.Controls.TextBox>创建控件并将其最初会填充文本。</span><span class="sxs-lookup"><span data-stu-id="650aa-107">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="650aa-108">示例</span><span class="sxs-lookup"><span data-stu-id="650aa-108">Example</span></span>  
 <span data-ttu-id="650aa-109">在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，它定义你<xref:System.Windows.Controls.TextBox>控制，指定<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>带值相匹配的事件处理程序方法名称的属性。</span><span class="sxs-lookup"><span data-stu-id="650aa-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a><span data-ttu-id="650aa-110">示例</span><span class="sxs-lookup"><span data-stu-id="650aa-110">Example</span></span>  
 <span data-ttu-id="650aa-111">中的代码隐藏类[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]包含<xref:System.Windows.Controls.TextBox>控件，你想要监视的更改，插入要每当调用的方法<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>事件激发。</span><span class="sxs-lookup"><span data-stu-id="650aa-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="650aa-112">此方法必须具有的签名匹配的预期内容<xref:System.Windows.Controls.TextChangedEventHandler>委托。</span><span class="sxs-lookup"><span data-stu-id="650aa-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <span data-ttu-id="650aa-113">会调用事件处理程序时的内容<xref:System.Windows.Controls.TextBox>由用户或以编程方式更改控制。</span><span class="sxs-lookup"><span data-stu-id="650aa-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="650aa-114">**注意：** 时将激发此事件<xref:System.Windows.Controls.TextBox>创建控件并将其最初会填充文本。</span><span class="sxs-lookup"><span data-stu-id="650aa-114">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
 <span data-ttu-id="650aa-115">注释</span><span class="sxs-lookup"><span data-stu-id="650aa-115">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650aa-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="650aa-116">See Also</span></span>  
 <xref:System.Windows.Controls.TextChangedEventArgs>  
 [<span data-ttu-id="650aa-117">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="650aa-117">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="650aa-118">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="650aa-118">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
