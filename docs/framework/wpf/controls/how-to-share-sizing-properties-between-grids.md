---
title: 如何：在 Grid 之间共享重设大小属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190335"
---
# <a name="how-to-share-sizing-properties-between-grids"></a><span data-ttu-id="30d99-102">如何：在 Grid 之间共享重设大小属性</span><span class="sxs-lookup"><span data-stu-id="30d99-102">How to: Share Sizing Properties Between Grids</span></span>
<span data-ttu-id="30d99-103">此示例演示如何共享列的大小调整数据和行之间<xref:System.Windows.Controls.Grid>元素，以使大小调整保持一致。</span><span class="sxs-lookup"><span data-stu-id="30d99-103">This example shows how to share the sizing data of columns and rows between <xref:System.Windows.Controls.Grid> elements in order to keep sizing consistent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30d99-104">示例</span><span class="sxs-lookup"><span data-stu-id="30d99-104">Example</span></span>  
 <span data-ttu-id="30d99-105">下面的示例引入了两处<xref:System.Windows.Controls.Grid>元素作为父级的子元素<xref:System.Windows.Controls.DockPanel>。</span><span class="sxs-lookup"><span data-stu-id="30d99-105">The following example introduces two <xref:System.Windows.Controls.Grid> elements as child elements of a parent <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="30d99-106"><xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>附加属性的<xref:System.Windows.Controls.Grid>的父级上定义<xref:System.Windows.Controls.DockPanel>。</span><span class="sxs-lookup"><span data-stu-id="30d99-106">The <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> attached property of <xref:System.Windows.Controls.Grid> is defined on the parent <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="30d99-107">该示例通过使用两个操作的属性值<xref:System.Windows.Controls.Button>元素; 每个元素表示一个布尔属性值。</span><span class="sxs-lookup"><span data-stu-id="30d99-107">The example manipulates the property value by using two <xref:System.Windows.Controls.Button> elements; each element represents one of the Boolean property values.</span></span> <span data-ttu-id="30d99-108">当<xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>属性值设置为`true`，每个列或行成员<xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>共享大小调整信息，无论行或列的内容。</span><span class="sxs-lookup"><span data-stu-id="30d99-108">When the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> property value is set to `true`, each column or row member of a <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> shares sizing information, regardless of the content of a row or column.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="30d99-109">...</span><span class="sxs-lookup"><span data-stu-id="30d99-109">...</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="30d99-110">下面的代码隐藏示例处理方法，该按钮<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件引发。</span><span class="sxs-lookup"><span data-stu-id="30d99-110">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event raises.</span></span> <span data-ttu-id="30d99-111">该示例将写入到这些方法调用的结果<xref:System.Windows.Controls.TextBlock>元素使用相关的 get 方法以输出新属性值作为字符串。</span><span class="sxs-lookup"><span data-stu-id="30d99-111">The example writes the results of these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="30d99-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="30d99-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [<span data-ttu-id="30d99-113">面板概述</span><span class="sxs-lookup"><span data-stu-id="30d99-113">Panels Overview</span></span>](panels-overview.md)
