---
title: "如何：更改光标类型"
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
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41cd8c9cd647c7efbc4e6cf13517ed638245e51c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="4904b-102">如何：更改光标类型</span><span class="sxs-lookup"><span data-stu-id="4904b-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="4904b-103">此示例演示如何更改<xref:System.Windows.Input.Cursor>鼠标指针的特定元素和应用程序。</span><span class="sxs-lookup"><span data-stu-id="4904b-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="4904b-104">此示例组成[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件和代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="4904b-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4904b-105">示例</span><span class="sxs-lookup"><span data-stu-id="4904b-105">Example</span></span>  
 <span data-ttu-id="4904b-106">创建用户界面，其中包括<xref:System.Windows.Controls.ComboBox>选择所需<xref:System.Windows.Input.Cursor>，一对<xref:System.Windows.Controls.RadioButton>对象以确定是否游标更改适用于仅包含单个元素或适用于整个应用程序，和一个<xref:System.Windows.Controls.Border>这是新光标将应用于的元素。</span><span class="sxs-lookup"><span data-stu-id="4904b-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="4904b-107">下面的代码隐藏创建<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>中更改的游标类型时调用事件处理程序<xref:System.Windows.Controls.ComboBox>。</span><span class="sxs-lookup"><span data-stu-id="4904b-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="4904b-108">Switch 语句的筛选器上的游标名称和集<xref:System.Windows.FrameworkElement.Cursor%2A>属性<xref:System.Windows.Controls.Border>名*DisplayArea*。</span><span class="sxs-lookup"><span data-stu-id="4904b-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="4904b-109">如果光标更改设置为"整个应用程序"，<xref:System.Windows.Input.Mouse.OverrideCursor%2A>属性设置为<xref:System.Windows.FrameworkElement.Cursor%2A>属性<xref:System.Windows.Controls.Border>控件。</span><span class="sxs-lookup"><span data-stu-id="4904b-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="4904b-110">这将强制更改对整个应用程序的光标。</span><span class="sxs-lookup"><span data-stu-id="4904b-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="4904b-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4904b-111">See Also</span></span>  
 [<span data-ttu-id="4904b-112">输入概述</span><span class="sxs-lookup"><span data-stu-id="4904b-112">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
