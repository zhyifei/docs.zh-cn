---
title: "如何：在绘制的文本中设置制表位"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2acc46a9a3fa2c84138cd9a168113f88ab08e4a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="acf35-102">如何：在绘制的文本中设置制表位</span><span class="sxs-lookup"><span data-stu-id="acf35-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="acf35-103">你可以通过调用设置文本的制表位<xref:System.Drawing.StringFormat.SetTabStops%2A>方法<xref:System.Drawing.StringFormat>对象，然后将该<xref:System.Drawing.StringFormat>对象传递给<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="acf35-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acf35-104"><xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType>执行不支持添加制表位与绘制的文本，尽管你可以扩展现有的选项卡停止使用<xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType>标志。</span><span class="sxs-lookup"><span data-stu-id="acf35-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acf35-105">示例</span><span class="sxs-lookup"><span data-stu-id="acf35-105">Example</span></span>  
 <span data-ttu-id="acf35-106">下面的示例在 150、 250 和 350 设置制表位。</span><span class="sxs-lookup"><span data-stu-id="acf35-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="acf35-107">然后，代码将显示名称和测试分数的选项卡式的列表。</span><span class="sxs-lookup"><span data-stu-id="acf35-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="acf35-108">下图显示的选项卡式的文本。</span><span class="sxs-lookup"><span data-stu-id="acf35-108">The following illustration shows the tabbed text.</span></span>  
  
 <span data-ttu-id="acf35-109">![字体文本](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span><span class="sxs-lookup"><span data-stu-id="acf35-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span></span>  
  
 <span data-ttu-id="acf35-110">下面的代码将传递到两个自变量<xref:System.Drawing.StringFormat.SetTabStops%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="acf35-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="acf35-111">第二个参数是一个数组，包含制表位偏移量。</span><span class="sxs-lookup"><span data-stu-id="acf35-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="acf35-112">第一个自变量传递给<xref:System.Drawing.StringFormat.SetTabStops%2A>为 0，它表示数组中的第一个偏移量从位置 0，边界矩形的左边缘开始测量。</span><span class="sxs-lookup"><span data-stu-id="acf35-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="acf35-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="acf35-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="acf35-114">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。</span><span class="sxs-lookup"><span data-stu-id="acf35-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf35-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="acf35-115">See Also</span></span>  
 [<span data-ttu-id="acf35-116">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="acf35-116">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="acf35-117">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="acf35-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
