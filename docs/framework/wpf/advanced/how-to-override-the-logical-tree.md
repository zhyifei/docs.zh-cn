---
title: "如何：重写逻辑树"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e487220f8b06515f3d37f7d55ab7ff6214c85d92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-override-the-logical-tree"></a>如何：重写逻辑树
尽管在大多数情况下不必重写逻辑树，但资深的控件创作者可选择执行此操作。  
  
## <a name="example"></a>示例  
 本示例介绍了如何子类<xref:System.Windows.Controls.StackPanel>重写逻辑树中，在这种情况下强制执行面板可能只能有并且将仅呈现单个子元素的行为。 这不一定是实际需要的行为，但在这里进行演示是为了举例说明重写元素的正常逻辑树的情况。  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 有关逻辑树的详细信息，请参阅 [WPF 中的树](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)。
