---
title: 如何：定位 Grid 的子元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: c508f45c1ea3d0925503d6fe5600498a0558d5ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770795"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="14dcf-102">如何：定位 Grid 的子元素</span><span class="sxs-lookup"><span data-stu-id="14dcf-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="14dcf-103">此示例演示如何使用 get 和 set 方法上定义的<xref:System.Windows.Controls.Grid>来定位子元素。</span><span class="sxs-lookup"><span data-stu-id="14dcf-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14dcf-104">示例</span><span class="sxs-lookup"><span data-stu-id="14dcf-104">Example</span></span>  
 <span data-ttu-id="14dcf-105">下面的示例定义一个父级<xref:System.Windows.Controls.Grid>元素 (`grid1`)，有三个列和三个行。</span><span class="sxs-lookup"><span data-stu-id="14dcf-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="14dcf-106">子<xref:System.Windows.Shapes.Rectangle>元素 (`rect1`) 添加到<xref:System.Windows.Controls.Grid>中的列位置零，行位置零。</span><span class="sxs-lookup"><span data-stu-id="14dcf-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="14dcf-107"><xref:System.Windows.Controls.Button> 元素表示方法可以调用以进行重新定位<xref:System.Windows.Shapes.Rectangle>元素内的<xref:System.Windows.Controls.Grid>。</span><span class="sxs-lookup"><span data-stu-id="14dcf-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="14dcf-108">当用户单击按钮时，激活相关的方法。</span><span class="sxs-lookup"><span data-stu-id="14dcf-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="14dcf-109">下面的代码隐藏示例处理方法，该按钮<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件引发。</span><span class="sxs-lookup"><span data-stu-id="14dcf-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="14dcf-110">该示例将写入到这些方法调用<xref:System.Windows.Controls.TextBlock>元素使用相关的 get 方法以输出新属性值作为字符串。</span><span class="sxs-lookup"><span data-stu-id="14dcf-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="14dcf-111">下面是最终的结果 ！</span><span class="sxs-lookup"><span data-stu-id="14dcf-111">Here is the finished result!</span></span>
 
 ![屏幕快照描述了具有两个列的 WPF 用户界面、 右侧有一个 3x3 网格和左侧具有按钮的网格行和列之间移动一个有色的矩形](././media/grid-methods-sample.png) 
  
## <a name="see-also"></a><span data-ttu-id="14dcf-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="14dcf-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="14dcf-114">面板概述</span><span class="sxs-lookup"><span data-stu-id="14dcf-114">Panels Overview</span></span>](panels-overview.md)
