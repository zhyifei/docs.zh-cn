---
title: "如何：创建简单绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a595f255b014e08b4b5b2036a7b1940e46df268f
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2018
---
# <a name="how-to-create-a-simple-binding"></a>如何：创建简单绑定
此示例演示如何创建一个简单<xref:System.Windows.Data.Binding>。  
  
## <a name="example"></a>示例  
 在此示例中，你有`Person`具有名为的字符串属性对象`PersonName`。 `Person`对象在调用的命名空间中定义`SDKSample`。  
  
 突出显示的行将包含`<src>`元素在下面的示例实例化`Person`对象`PersonName`属性值`Joe`。 将执行此操作`Resources`部分并分配`x:Key`。  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 突出显示的行将包含`<TextBlock>`元素然后将绑定<xref:System.Windows.Controls.TextBlock>控制转移到`PersonName`属性。 因此，<xref:System.Windows.Controls.TextBlock>出现包含值"Joe"。  
  
## <a name="see-also"></a>请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
