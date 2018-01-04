---
title: "如何：枚举系统字体"
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
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf917dc2af256cdd0f3a0c579f86847e1bf4f1e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-system-fonts"></a><span data-ttu-id="a4691-102">如何：枚举系统字体</span><span class="sxs-lookup"><span data-stu-id="a4691-102">How to: Enumerate System Fonts</span></span>
## <a name="example"></a><span data-ttu-id="a4691-103">示例</span><span class="sxs-lookup"><span data-stu-id="a4691-103">Example</span></span>  
 <span data-ttu-id="a4691-104">下面的示例演示如何枚举系统字体集合中的字体。</span><span class="sxs-lookup"><span data-stu-id="a4691-104">The following example shows how to enumerate the fonts in the system font collection.</span></span> <span data-ttu-id="a4691-105">每个字体系列名称<xref:System.Windows.Media.FontFamily>内<xref:System.Windows.Media.Fonts.SystemFontFamilies%2A>作为一项添加到组合框。</span><span class="sxs-lookup"><span data-stu-id="a4691-105">The font family name of each <xref:System.Windows.Media.FontFamily> within <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> is added as an item to a combo box.</span></span>  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 <span data-ttu-id="a4691-106">如果多个版本的相同的字体系列驻留在相同的目录中，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]字体枚举返回的字体的最新版本。</span><span class="sxs-lookup"><span data-stu-id="a4691-106">If multiple versions of the same font family reside in the same directory, the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] font enumeration returns the most recent version of the font.</span></span> <span data-ttu-id="a4691-107">如果版本信息不提供解析，则返回具有最新时间戳的字体。</span><span class="sxs-lookup"><span data-stu-id="a4691-107">If the version information does not provide resolution, the font with latest timestamp is returned.</span></span> <span data-ttu-id="a4691-108">如果时间戳信息是等效的则返回的字体文件，按字母顺序中排名第一。</span><span class="sxs-lookup"><span data-stu-id="a4691-108">If the timestamp information is equivalent, the font file that is first in alphabetical order is returned.</span></span>
