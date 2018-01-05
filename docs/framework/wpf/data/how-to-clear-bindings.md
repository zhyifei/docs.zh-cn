---
title: "如何：清除绑定"
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
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af45d504eb4e7d45808f787925a90c8e0ed19476
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="843e1-102">如何：清除绑定</span><span class="sxs-lookup"><span data-stu-id="843e1-102">How to: Clear Bindings</span></span>
<span data-ttu-id="843e1-103">此示例演示如何从对象中清除绑定。</span><span class="sxs-lookup"><span data-stu-id="843e1-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="843e1-104">示例</span><span class="sxs-lookup"><span data-stu-id="843e1-104">Example</span></span>  
 <span data-ttu-id="843e1-105">若要清除从对象上的单个属性的绑定，请调用<xref:System.Windows.Data.BindingOperations.ClearBinding%2A>下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="843e1-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="843e1-106">下面的示例删除从绑定<xref:System.Windows.Controls.TextBlock.TextProperty>的*mytext*、<xref:System.Windows.Controls.TextBlock>对象。</span><span class="sxs-lookup"><span data-stu-id="843e1-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="843e1-107">清除绑定会移除绑定，这样依赖属性的值会更改为过去尚未绑定时的值。</span><span class="sxs-lookup"><span data-stu-id="843e1-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="843e1-108">此值可以是默认值、继承值或来自数据模板绑定的值。</span><span class="sxs-lookup"><span data-stu-id="843e1-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="843e1-109">若要清除从对象上的所有可能的属性的绑定，使用<xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>。</span><span class="sxs-lookup"><span data-stu-id="843e1-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="843e1-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="843e1-110">See Also</span></span>  
 <xref:System.Windows.Data.BindingOperations>  
 [<span data-ttu-id="843e1-111">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="843e1-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="843e1-112">帮助主题</span><span class="sxs-lookup"><span data-stu-id="843e1-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
