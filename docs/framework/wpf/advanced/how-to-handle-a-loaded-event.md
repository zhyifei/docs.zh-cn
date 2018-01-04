---
title: "如何：处理 Loaded 事件"
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
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 794de0e64e2f4d974091b92f211d7472d04ecd26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-a-loaded-event"></a>如何：处理 Loaded 事件
此示例演示如何处理<xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType>事件，并处理该事件的相应方案。 该处理程序创建<xref:System.Windows.Controls.Button>加载页面时。  
  
## <a name="example"></a>示例  
 下面的示例使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]以及代码隐藏文件。  
  
 [!code-xaml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.FrameworkElement>  
 [对象生存期事件](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
