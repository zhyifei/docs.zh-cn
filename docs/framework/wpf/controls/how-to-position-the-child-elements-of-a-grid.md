---
title: 如何：定位网格的子元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186722"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="51af0-102">如何：定位网格的子元素</span><span class="sxs-lookup"><span data-stu-id="51af0-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="51af0-103">此示例演示如何使用定义 get<xref:System.Windows.Controls.Grid>和设置方法来定位子元素。</span><span class="sxs-lookup"><span data-stu-id="51af0-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51af0-104">示例</span><span class="sxs-lookup"><span data-stu-id="51af0-104">Example</span></span>  
 <span data-ttu-id="51af0-105">下面的示例定义具有三列和<xref:System.Windows.Controls.Grid>三行`grid1`的父元素 （ ）。</span><span class="sxs-lookup"><span data-stu-id="51af0-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="51af0-106">子<xref:System.Windows.Shapes.Rectangle>元素 （`rect1`） 添加到列<xref:System.Windows.Controls.Grid>位置零，行位置零。</span><span class="sxs-lookup"><span data-stu-id="51af0-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="51af0-107"><xref:System.Windows.Controls.Button>元素表示可以调用以重新定位<xref:System.Windows.Shapes.Rectangle>元素的方法。 <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="51af0-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="51af0-108">当用户单击按钮时，将激活相关方法。</span><span class="sxs-lookup"><span data-stu-id="51af0-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="51af0-109">下面的代码后面示例处理按钮<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件引发的方法。</span><span class="sxs-lookup"><span data-stu-id="51af0-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="51af0-110">该示例将这些方法调用写入<xref:System.Windows.Controls.TextBlock>使用相关 get 方法将新属性值输出为字符串的元素。</span><span class="sxs-lookup"><span data-stu-id="51af0-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="51af0-111">这是完成的结果！</span><span class="sxs-lookup"><span data-stu-id="51af0-111">Here is the finished result!</span></span>

 ![屏幕截图描绘了包含两列的 WPF 用户界面，右侧有一个 3 x 3 网格，左侧有按钮在网格的列和行之间移动彩色矩形](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="51af0-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51af0-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="51af0-114">面板概述</span><span class="sxs-lookup"><span data-stu-id="51af0-114">Panels Overview</span></span>](panels-overview.md)
