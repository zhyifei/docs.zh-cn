---
title: "如何：装饰面板的子级"
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
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d30e9e5ac15f48dabf983123ba007674a14626d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="30008-102">如何：装饰面板的子级</span><span class="sxs-lookup"><span data-stu-id="30008-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="30008-103">此示例演示如何以编程方式将装饰器绑定到指定的子级<xref:System.Windows.Controls.Panel>。</span><span class="sxs-lookup"><span data-stu-id="30008-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30008-104">示例</span><span class="sxs-lookup"><span data-stu-id="30008-104">Example</span></span>  
 <span data-ttu-id="30008-105">若要将装饰器绑定到的子级<xref:System.Windows.Controls.Panel>，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="30008-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="30008-106">声明新<xref:System.Windows.Documents.AdornerLayer>对象并调用`static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>方法以查找要装饰的子级的元素的装饰器层。</span><span class="sxs-lookup"><span data-stu-id="30008-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="30008-107">枚举的子级的父元素和调用<xref:System.Windows.Documents.AdornerLayer.Add%2A>方法将装饰器绑定到每个子元素。</span><span class="sxs-lookup"><span data-stu-id="30008-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="30008-108">下面的示例将绑定 （上面所述） 的子级 SimpleCircleAdorner<xref:System.Windows.Controls.StackPanel>名为*myStackPanel*。</span><span class="sxs-lookup"><span data-stu-id="30008-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="30008-109">目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。</span><span class="sxs-lookup"><span data-stu-id="30008-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30008-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30008-110">See Also</span></span>  
 [<span data-ttu-id="30008-111">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="30008-111">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
