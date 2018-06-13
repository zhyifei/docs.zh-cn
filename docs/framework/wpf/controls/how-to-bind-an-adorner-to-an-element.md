---
title: 如何：将装饰器绑定到元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: fb419ee5a57e81e7e3bc72ae04fd200703b80cd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552547"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="ed609-102">如何：将装饰器绑定到元素</span><span class="sxs-lookup"><span data-stu-id="ed609-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="ed609-103">此示例演示如何以编程方式将装饰器绑定到指定<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="ed609-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed609-104">示例</span><span class="sxs-lookup"><span data-stu-id="ed609-104">Example</span></span>  
 <span data-ttu-id="ed609-105">若要将装饰器绑定到特定<xref:System.Windows.UIElement>，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ed609-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ed609-106">调用`static`方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>获取<xref:System.Windows.Documents.AdornerLayer>对象<xref:System.Windows.UIElement>装饰。</span><span class="sxs-lookup"><span data-stu-id="ed609-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="ed609-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 上移到可视化树，开始指定**UIElement**，并返回它找到的第一个装饰器层。</span><span class="sxs-lookup"><span data-stu-id="ed609-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="ed609-108">（如果未发现装饰器层，该方法将返回 null。）</span><span class="sxs-lookup"><span data-stu-id="ed609-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="ed609-109">调用<xref:System.Windows.Documents.AdornerLayer.Add%2A>方法将装饰器绑定到目标**UIElement**。</span><span class="sxs-lookup"><span data-stu-id="ed609-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="ed609-110">下面的示例将绑定 （上面所述） 到 SimpleCircleAdorner<xref:System.Windows.Controls.TextBox>名为*myTextBox*。</span><span class="sxs-lookup"><span data-stu-id="ed609-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="ed609-111">目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。</span><span class="sxs-lookup"><span data-stu-id="ed609-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed609-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed609-112">See Also</span></span>  
 [<span data-ttu-id="ed609-113">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="ed609-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
