---
title: "如何：定位网格的子元素"
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
helpviewer_keywords: Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2dbe0bcb5d3c46edcb97410e00832f1b9d6205b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="03a95-102">如何：定位网格的子元素</span><span class="sxs-lookup"><span data-stu-id="03a95-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="03a95-103">此示例演示如何使用 get 和 set 定义的方法<xref:System.Windows.Controls.Grid>来定位子元素。</span><span class="sxs-lookup"><span data-stu-id="03a95-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03a95-104">示例</span><span class="sxs-lookup"><span data-stu-id="03a95-104">Example</span></span>  
 <span data-ttu-id="03a95-105">下面的示例定义一个父<xref:System.Windows.Controls.Grid>元素 (`grid1`) 具有三列和三个行。</span><span class="sxs-lookup"><span data-stu-id="03a95-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="03a95-106">子<xref:System.Windows.Shapes.Rectangle>元素 (`rect1`) 添加到<xref:System.Windows.Controls.Grid>在列的位置零，行位置零。</span><span class="sxs-lookup"><span data-stu-id="03a95-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="03a95-107"><xref:System.Windows.Controls.Button>元素表示方法可以调用以进行重新定位<xref:System.Windows.Shapes.Rectangle>中的元素<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="03a95-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="03a95-108">当用户单击按钮时，将激活相关的方法。</span><span class="sxs-lookup"><span data-stu-id="03a95-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="03a95-109">下面的代码隐藏示例处理方法，该按钮<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件引发。</span><span class="sxs-lookup"><span data-stu-id="03a95-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="03a95-110">此示例将对这些方法调用<xref:System.Windows.Controls.TextBlock>元素使用与 get 方法以输出字符串的形式将新属性值。</span><span class="sxs-lookup"><span data-stu-id="03a95-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="03a95-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03a95-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="03a95-112">面板概述</span><span class="sxs-lookup"><span data-stu-id="03a95-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
