---
title: 如何：更改光标类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 2330cdd3be35dc4e4b555db6401dd55d9946ed1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745046"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="79fed-102">如何：更改光标类型</span><span class="sxs-lookup"><span data-stu-id="79fed-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="79fed-103">此示例演示如何更改<xref:System.Windows.Input.Cursor>的鼠标指针的特定元素和应用程序。</span><span class="sxs-lookup"><span data-stu-id="79fed-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="79fed-104">此示例中包含的[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件和代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="79fed-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79fed-105">示例</span><span class="sxs-lookup"><span data-stu-id="79fed-105">Example</span></span>  
 <span data-ttu-id="79fed-106">创建的用户界面，其中包含<xref:System.Windows.Controls.ComboBox>以选择所需<xref:System.Windows.Input.Cursor>，一对<xref:System.Windows.Controls.RadioButton>对象来确定游标更改是否适用于单个元素或适用于整个应用程序，和一个<xref:System.Windows.Controls.Border>这是新光标应用于的元素。</span><span class="sxs-lookup"><span data-stu-id="79fed-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="79fed-107">下面的代码隐藏创建<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>中更改的游标类型时调用的事件处理程序<xref:System.Windows.Controls.ComboBox>。</span><span class="sxs-lookup"><span data-stu-id="79fed-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="79fed-108">Switch 语句的游标名称和集上进行筛选<xref:System.Windows.FrameworkElement.Cursor%2A>上的属性<xref:System.Windows.Controls.Border>其名为*DisplayArea*。</span><span class="sxs-lookup"><span data-stu-id="79fed-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="79fed-109">如果光标更改设置为"整个应用程序"，<xref:System.Windows.Input.Mouse.OverrideCursor%2A>属性设置为<xref:System.Windows.FrameworkElement.Cursor%2A>属性的<xref:System.Windows.Controls.Border>控件。</span><span class="sxs-lookup"><span data-stu-id="79fed-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="79fed-110">这会强制更改对整个应用程序的光标。</span><span class="sxs-lookup"><span data-stu-id="79fed-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="79fed-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="79fed-111">See also</span></span>
- [<span data-ttu-id="79fed-112">输入概述</span><span class="sxs-lookup"><span data-stu-id="79fed-112">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
