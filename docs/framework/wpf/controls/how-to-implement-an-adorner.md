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
ms.openlocfilehash: a3f69fee64ea65e8d49cce523c85669993cc6bce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="33632-102">如何：实现装饰器</span><span class="sxs-lookup"><span data-stu-id="33632-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="33632-103">此示例显示最小装饰器实现。</span><span class="sxs-lookup"><span data-stu-id="33632-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="33632-104">实施者注意事项</span><span class="sxs-lookup"><span data-stu-id="33632-104">Notes for Implementers</span></span>  
 <span data-ttu-id="33632-105">请务必注意，装饰器不包括任何继承呈现行为，确保装饰器呈现是装饰器实施者的责任。</span><span class="sxs-lookup"><span data-stu-id="33632-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="33632-106">实现呈现行为的常用方法是重写<xref:System.Windows.UIElement.OnRender%2A>方法并使用一个或多个<xref:System.Windows.Media.DrawingContext>对象来呈现装饰器的视觉对象根据需要 （如本示例中所示）。</span><span class="sxs-lookup"><span data-stu-id="33632-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33632-107">示例</span><span class="sxs-lookup"><span data-stu-id="33632-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="33632-108">描述</span><span class="sxs-lookup"><span data-stu-id="33632-108">Description</span></span>  
 <span data-ttu-id="33632-109">通过实现从抽象继承的类创建一个自定义的装饰器<xref:System.Windows.Documents.Adorner>类。</span><span class="sxs-lookup"><span data-stu-id="33632-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="33632-110">本示例装饰器简单地装饰的角<xref:System.Windows.UIElement>使用通过重写的圆圈<xref:System.Windows.UIElement.OnRender%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="33632-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="33632-111">代码</span><span class="sxs-lookup"><span data-stu-id="33632-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="33632-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33632-112">See Also</span></span>  
 [<span data-ttu-id="33632-113">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="33632-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
