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
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>如何：将装饰器绑定到元素
此示例演示如何以编程方式将装饰器绑定到指定<xref:System.Windows.UIElement>。  
  
## <a name="example"></a>示例  
 若要将装饰器绑定到特定<xref:System.Windows.UIElement>，请按照下列步骤：  
  
1.  调用`static`方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>获取<xref:System.Windows.Documents.AdornerLayer>对象<xref:System.Windows.UIElement>装饰。 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 上移到可视化树，开始指定**UIElement**，并返回它找到的第一个装饰器层。 （如果未发现装饰器层，该方法将返回 null。）  
  
2.  调用<xref:System.Windows.Documents.AdornerLayer.Add%2A>方法将装饰器绑定到目标**UIElement**。  
  
 下面的示例将绑定 （上面所述） 到 SimpleCircleAdorner<xref:System.Windows.Controls.TextBox>名为*myTextBox*。  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。  
  
## <a name="see-also"></a>请参阅  
 [装饰器概述](../../../../docs/framework/wpf/controls/adorners-overview.md)
