---
title: 如何：搜寻演示图板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: 440b2dd157b56a1616f7137b1e311cb981b33861
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604452"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="71885-102">如何：搜寻演示图板</span><span class="sxs-lookup"><span data-stu-id="71885-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="71885-103">下面的示例演示如何使用<xref:System.Windows.Media.Animation.Storyboard.Seek%2A>方法的<xref:System.Windows.Media.Animation.Storyboard>跳转到演示图板动画中的任意位置。</span><span class="sxs-lookup"><span data-stu-id="71885-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71885-104">示例</span><span class="sxs-lookup"><span data-stu-id="71885-104">Example</span></span>  
 <span data-ttu-id="71885-105">下面是此示例的 XAML 标记。</span><span class="sxs-lookup"><span data-stu-id="71885-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="71885-106">示例</span><span class="sxs-lookup"><span data-stu-id="71885-106">Example</span></span>  
 <span data-ttu-id="71885-107">下面是上述 XAML 代码中所用的代码。</span><span class="sxs-lookup"><span data-stu-id="71885-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="71885-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="71885-108">See also</span></span>
- [<span data-ttu-id="71885-109">同步搜寻演示图板</span><span class="sxs-lookup"><span data-stu-id="71885-109">Seek a Storyboard Synchronously</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md)
