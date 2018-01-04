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
# <a name="how-to-override-the-logical-tree"></a><span data-ttu-id="4897b-102">如何：重写逻辑树</span><span class="sxs-lookup"><span data-stu-id="4897b-102">How to: Override the Logical Tree</span></span>
<span data-ttu-id="4897b-103">尽管在大多数情况下不必重写逻辑树，但资深的控件创作者可选择执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4897b-103">Although it is not necessary in most cases, advanced control authors have the option to override the logical tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4897b-104">示例</span><span class="sxs-lookup"><span data-stu-id="4897b-104">Example</span></span>  
 <span data-ttu-id="4897b-105">本示例介绍了如何子类<xref:System.Windows.Controls.StackPanel>重写逻辑树中，在这种情况下强制执行面板可能只能有并且将仅呈现单个子元素的行为。</span><span class="sxs-lookup"><span data-stu-id="4897b-105">This example describes how to subclass <xref:System.Windows.Controls.StackPanel> to override the logical tree, in this case to enforce a behavior that the panel may only have and will only render a single child element.</span></span> <span data-ttu-id="4897b-106">这不一定是实际需要的行为，但在这里进行演示是为了举例说明重写元素的正常逻辑树的情况。</span><span class="sxs-lookup"><span data-stu-id="4897b-106">This isn't necessarily a practically desirable behavior, but is shown here as a means of illustrating the scenario for overriding an element's normal logical tree.</span></span>  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 <span data-ttu-id="4897b-107">有关逻辑树的详细信息，请参阅 [WPF 中的树](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="4897b-107">For more information on the logical tree, see [Trees in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).</span></span>
