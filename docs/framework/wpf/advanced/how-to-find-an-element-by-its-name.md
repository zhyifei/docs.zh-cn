---
title: 如何：按名称查找元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: e2d176c9334c0a1d4c10819e0dc9f2c408e41d5d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543571"
---
# <a name="how-to-find-an-element-by-its-name"></a><span data-ttu-id="519a0-102">如何：按名称查找元素</span><span class="sxs-lookup"><span data-stu-id="519a0-102">How to: Find an Element by Its Name</span></span>
<span data-ttu-id="519a0-103">本示例介绍了如何使用<xref:System.Windows.FrameworkElement.FindName%2A>方法以查找元素其<xref:System.Windows.FrameworkElement.Name%2A>值。</span><span class="sxs-lookup"><span data-stu-id="519a0-103">This example describes how to use the <xref:System.Windows.FrameworkElement.FindName%2A> method to find an element by its <xref:System.Windows.FrameworkElement.Name%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="519a0-104">示例</span><span class="sxs-lookup"><span data-stu-id="519a0-104">Example</span></span>  
 <span data-ttu-id="519a0-105">在此示例中，要按其名称查找特定元素的方法是编写为一个按钮的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="519a0-105">In this example, the method to find a particular element by its name is written as the event handler of a button.</span></span> <span data-ttu-id="519a0-106">`stackPanel` 是<xref:System.Windows.FrameworkElement.Name%2A>根的<xref:System.Windows.FrameworkElement>要搜索和示例方法然后直观指示所找到的元素通过强制转换为其作为<xref:System.Windows.Controls.TextBlock>和更改其中一个<xref:System.Windows.Controls.TextBlock>可见[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]属性。</span><span class="sxs-lookup"><span data-stu-id="519a0-106">`stackPanel` is the <xref:System.Windows.FrameworkElement.Name%2A> of the root <xref:System.Windows.FrameworkElement> being searched, and the example method then visually indicates the found element by casting it as <xref:System.Windows.Controls.TextBlock> and changing one of the <xref:System.Windows.Controls.TextBlock> visible [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] properties.</span></span>  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
