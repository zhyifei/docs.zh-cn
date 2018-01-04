---
title: "如何：从元素移除所有装饰器"
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
helpviewer_keywords: adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f7bb16c2cd641579706609ff14ca16cc57bd620
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>如何：从元素移除所有装饰器
此示例演示如何以编程方式移除所有装饰器，从指定<xref:System.Windows.UIElement>。  
  
## <a name="example"></a>示例  
 此详细的代码示例中移除所有装饰器返回的装饰器数组中<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>。  此示例碰巧上检索装饰器<xref:System.Windows.UIElement>名为*myTextBox*。  如果该元素指定的调用中<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>没有装饰器，`null`返回。  此代码显式检查 null 数组，并最适合应用程序的其中一个空数组应为相对常见。  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>示例  
 此简化的代码示例在功能上等效于详细示例如上所示。 此代码不显式检查 null 数组，因此很可能，<xref:System.NullReferenceException>可能引发异常。  此代码最适合应用程序是一个空数组的地方很少见。  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>请参阅  
 [装饰器概述](../../../../docs/framework/wpf/controls/adorners-overview.md)
