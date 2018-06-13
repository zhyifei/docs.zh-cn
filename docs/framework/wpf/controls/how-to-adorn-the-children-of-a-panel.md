---
title: 如何：装饰面板的子级
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 4babbf1df57f340a3f6be218f213ad1c868ec9f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550214"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="6e606-102">如何：装饰面板的子级</span><span class="sxs-lookup"><span data-stu-id="6e606-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="6e606-103">此示例演示如何以编程方式将装饰器绑定到指定的子级<xref:System.Windows.Controls.Panel>。</span><span class="sxs-lookup"><span data-stu-id="6e606-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e606-104">示例</span><span class="sxs-lookup"><span data-stu-id="6e606-104">Example</span></span>  
 <span data-ttu-id="6e606-105">若要将装饰器绑定到的子级<xref:System.Windows.Controls.Panel>，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="6e606-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="6e606-106">声明新<xref:System.Windows.Documents.AdornerLayer>对象并调用`static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>方法以查找要装饰的子级的元素的装饰器层。</span><span class="sxs-lookup"><span data-stu-id="6e606-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="6e606-107">枚举的子级的父元素和调用<xref:System.Windows.Documents.AdornerLayer.Add%2A>方法将装饰器绑定到每个子元素。</span><span class="sxs-lookup"><span data-stu-id="6e606-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="6e606-108">下面的示例将绑定 （上面所述） 的子级 SimpleCircleAdorner<xref:System.Windows.Controls.StackPanel>名为*myStackPanel*。</span><span class="sxs-lookup"><span data-stu-id="6e606-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="6e606-109">目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。</span><span class="sxs-lookup"><span data-stu-id="6e606-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e606-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e606-110">See Also</span></span>  
 [<span data-ttu-id="6e606-111">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="6e606-111">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
