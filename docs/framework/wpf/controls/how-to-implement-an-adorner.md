---
title: "如何：实现装饰器"
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
helpviewer_keywords: adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76bceae5b69fad4c217127617309484edcf18108
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-an-adorner"></a>如何：实现装饰器
此示例显示最小装饰器实现。  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 请务必注意，装饰器不包括任何继承呈现行为，确保装饰器呈现是装饰器实施者的责任。   实现呈现行为的常用方法是重写<xref:System.Windows.UIElement.OnRender%2A>方法并使用一个或多个<xref:System.Windows.Media.DrawingContext>对象来呈现装饰器的视觉对象根据需要 （如本示例中所示）。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 通过实现从抽象继承的类创建一个自定义的装饰器<xref:System.Windows.Documents.Adorner>类。  本示例装饰器简单地装饰的角<xref:System.Windows.UIElement>使用通过重写的圆圈<xref:System.Windows.UIElement.OnRender%2A>方法。  
  
### <a name="code"></a>代码  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>请参阅  
 [装饰器概述](../../../../docs/framework/wpf/controls/adorners-overview.md)
