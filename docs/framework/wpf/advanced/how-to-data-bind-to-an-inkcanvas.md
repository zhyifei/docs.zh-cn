---
title: "如何：将数据绑定到 InkCanvas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c8c4f558386edd8da213f8a8af75b6a4c6a98b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a>如何：将数据绑定到 InkCanvas
## <a name="example"></a>示例  
 下面的示例演示如何将绑定<xref:System.Windows.Controls.InkCanvas.Strokes%2A>属性<xref:System.Windows.Controls.InkCanvas>到另一个<xref:System.Windows.Controls.InkCanvas>。  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 下面的示例演示如何将绑定<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>到数据源的属性。  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 下面的示例声明了两个<xref:System.Windows.Controls.InkCanvas>XAML 中的对象，并建立它们和其他数据源之间的数据绑定。  第一个<xref:System.Windows.Controls.InkCanvas>、 调用`ic`，绑定到两个数据源。  <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>和<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>属性`ic`绑定到<xref:System.Windows.Controls.ListBox>又绑定到在 XAML 中定义的数组的对象。  <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>， <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>，和<xref:System.Windows.Controls.InkCanvas.Strokes%2A>第二个属性<xref:System.Windows.Controls.InkCanvas>绑定到第一个<xref:System.Windows.Controls.InkCanvas>， `ic`。  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
