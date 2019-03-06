---
title: 如何：枚举系统字体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: c7e81b5d1b70ba911a0b505219f7977e019038cf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352433"
---
# <a name="how-to-enumerate-system-fonts"></a><span data-ttu-id="6751a-102">如何：枚举系统字体</span><span class="sxs-lookup"><span data-stu-id="6751a-102">How to: Enumerate System Fonts</span></span>
## <a name="example"></a><span data-ttu-id="6751a-103">示例</span><span class="sxs-lookup"><span data-stu-id="6751a-103">Example</span></span>  
 <span data-ttu-id="6751a-104">下面的示例说明如何枚举系统字体集合中的字体。</span><span class="sxs-lookup"><span data-stu-id="6751a-104">The following example shows how to enumerate the fonts in the system font collection.</span></span> <span data-ttu-id="6751a-105">字体系列名称的每个<xref:System.Windows.Media.FontFamily>内<xref:System.Windows.Media.Fonts.SystemFontFamilies%2A>作为一项添加到组合框。</span><span class="sxs-lookup"><span data-stu-id="6751a-105">The font family name of each <xref:System.Windows.Media.FontFamily> within <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> is added as an item to a combo box.</span></span>  
  
 [!code-csharp[TextOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 <span data-ttu-id="6751a-106">如果多个版本的相同的字体系列驻留在同一个目录，[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]字体枚举返回的字体的最新版本。</span><span class="sxs-lookup"><span data-stu-id="6751a-106">If multiple versions of the same font family reside in the same directory, the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] font enumeration returns the most recent version of the font.</span></span> <span data-ttu-id="6751a-107">如果版本信息不提供解决方法，则返回具有最新时间戳的字体。</span><span class="sxs-lookup"><span data-stu-id="6751a-107">If the version information does not provide resolution, the font with latest timestamp is returned.</span></span> <span data-ttu-id="6751a-108">如果时间戳信息是等效的则返回第一次按字母顺序的字体文件。</span><span class="sxs-lookup"><span data-stu-id="6751a-108">If the timestamp information is equivalent, the font file that is first in alphabetical order is returned.</span></span>
