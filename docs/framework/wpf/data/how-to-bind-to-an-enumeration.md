---
title: "如何：绑定到枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31fb9adbda47514e5405d465c0b5e2493b966d8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-an-enumeration"></a>如何：绑定到枚举
此示例演示如何将绑定到通过绑定到枚举的 GetValues 方法的枚举。  
  
## <a name="example"></a>示例  
 在下面的示例中，<xref:System.Windows.Controls.ListBox>显示的列表<xref:System.Windows.HorizontalAlignment>通过数据绑定的枚举值。 <xref:System.Windows.Controls.ListBox>和<xref:System.Windows.Controls.Button>绑定，这样，你可以更改<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性值<xref:System.Windows.Controls.Button>通过选择中的值<xref:System.Windows.Controls.ListBox>。  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>另请参阅  
 [绑定到方法](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
