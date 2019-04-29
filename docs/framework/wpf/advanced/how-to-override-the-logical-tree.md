---
title: 如何：重写逻辑树
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768441"
---
# <a name="how-to-override-the-logical-tree"></a><span data-ttu-id="86fec-102">如何：重写逻辑树</span><span class="sxs-lookup"><span data-stu-id="86fec-102">How to: Override the Logical Tree</span></span>
<span data-ttu-id="86fec-103">尽管在大多数情况下不必重写逻辑树，但资深的控件创作者可选择执行此操作。</span><span class="sxs-lookup"><span data-stu-id="86fec-103">Although it is not necessary in most cases, advanced control authors have the option to override the logical tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86fec-104">示例</span><span class="sxs-lookup"><span data-stu-id="86fec-104">Example</span></span>  
 <span data-ttu-id="86fec-105">本示例介绍了如何创建子类<xref:System.Windows.Controls.StackPanel>重写逻辑树中，在这种情况下强制执行面板可能只有，并且将仅呈现单个子元素的行为。</span><span class="sxs-lookup"><span data-stu-id="86fec-105">This example describes how to subclass <xref:System.Windows.Controls.StackPanel> to override the logical tree, in this case to enforce a behavior that the panel may only have and will only render a single child element.</span></span> <span data-ttu-id="86fec-106">这不一定是实际需要的行为，但在这里进行演示是为了举例说明重写元素的正常逻辑树的情况。</span><span class="sxs-lookup"><span data-stu-id="86fec-106">This isn't necessarily a practically desirable behavior, but is shown here as a means of illustrating the scenario for overriding an element's normal logical tree.</span></span>  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 <span data-ttu-id="86fec-107">有关逻辑树的详细信息，请参阅 [WPF 中的树](trees-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="86fec-107">For more information on the logical tree, see [Trees in WPF](trees-in-wpf.md).</span></span>
