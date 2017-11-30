---
title: "如何：使用 IScrollInfo 接口来滚动内容"
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
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1895507c30ad5267d4c2b1afff3acf004e872d40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a><span data-ttu-id="2c916-102">如何：使用 IScrollInfo 接口来滚动内容</span><span class="sxs-lookup"><span data-stu-id="2c916-102">How to: Scroll Content by Using the IScrollInfo Interface</span></span>
<span data-ttu-id="2c916-103">此示例演示如何通过使用滚动内容<xref:System.Windows.Controls.Primitives.IScrollInfo>接口。</span><span class="sxs-lookup"><span data-stu-id="2c916-103">This example shows how to scroll content by using the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c916-104">示例</span><span class="sxs-lookup"><span data-stu-id="2c916-104">Example</span></span>  
 <span data-ttu-id="2c916-105">下面的示例演示的功能<xref:System.Windows.Controls.Primitives.IScrollInfo>接口。</span><span class="sxs-lookup"><span data-stu-id="2c916-105">The following example demonstrates the features of the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span> <span data-ttu-id="2c916-106">该示例创建<xref:System.Windows.Controls.StackPanel>中的元素[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]嵌套在父<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="2c916-106">The example creates a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that is nested in a parent <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="2c916-107">子元素<xref:System.Windows.Controls.StackPanel>可通过使用由定义的方法逻辑上滚动<xref:System.Windows.Controls.Primitives.IScrollInfo>接口和强制转换为的实例<xref:System.Windows.Controls.StackPanel>(`sp1`) 在代码中。</span><span class="sxs-lookup"><span data-stu-id="2c916-107">The child elements of the <xref:System.Windows.Controls.StackPanel> can be scrolled logically by using the methods defined by the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface and cast to the instance of <xref:System.Windows.Controls.StackPanel> (`sp1`) in code.</span></span>  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="2c916-108">每个<xref:System.Windows.Controls.Button>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件触发控制滚动行为中的关联自定义方法<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="2c916-108">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file triggers an associated custom method that controls scrolling behavior in <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="2c916-109">下面的示例演示如何使用<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A>和<xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>方法; 它还大致演示了如何使用所有定位方法的<xref:System.Windows.Controls.Primitives.IScrollInfo>类定义。</span><span class="sxs-lookup"><span data-stu-id="2c916-109">The following example shows how to use the <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> methods; it also generically shows how to use all the positioning methods that the <xref:System.Windows.Controls.Primitives.IScrollInfo> class defines.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2c916-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c916-110">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 <xref:System.Windows.Controls.StackPanel>  
 [<span data-ttu-id="2c916-111">ScrollViewer 概述</span><span class="sxs-lookup"><span data-stu-id="2c916-111">ScrollViewer Overview</span></span>](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)  
 [<span data-ttu-id="2c916-112">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="2c916-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)  
 [<span data-ttu-id="2c916-113">面板概述</span><span class="sxs-lookup"><span data-stu-id="2c916-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
