---
title: 如何：在绘制的文本中设置制表位
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 8821f6170b8ba588e3197ef54eab14c2719a6cc3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947822"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="07e00-102">如何：在绘制的文本中设置制表位</span><span class="sxs-lookup"><span data-stu-id="07e00-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="07e00-103"><xref:System.Drawing.StringFormat.SetTabStops%2A>可以通过调用<xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.StringFormat>对象的方法, 然后将该对象传递给类的方法, 为文本设置制表位。 <xref:System.Drawing.StringFormat></span><span class="sxs-lookup"><span data-stu-id="07e00-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07e00-104">虽然您可以<xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType>使用标志展开现有制表位, 但不支持向绘制文本添加制表位。 <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="07e00-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07e00-105">示例</span><span class="sxs-lookup"><span data-stu-id="07e00-105">Example</span></span>  
 <span data-ttu-id="07e00-106">下面的示例将制表位设置为150、250和350。</span><span class="sxs-lookup"><span data-stu-id="07e00-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="07e00-107">然后, 该代码显示名称和测试分数的选项卡式列表。</span><span class="sxs-lookup"><span data-stu-id="07e00-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="07e00-108">下图显示了选项卡式文本:</span><span class="sxs-lookup"><span data-stu-id="07e00-108">The following illustration shows the tabbed text:</span></span>  
  
 ![显示姓名和分数的选项卡式列表的屏幕截图。](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 <span data-ttu-id="07e00-110">下面的代码将两个参数传递<xref:System.Drawing.StringFormat.SetTabStops%2A>给方法。</span><span class="sxs-lookup"><span data-stu-id="07e00-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="07e00-111">第二个参数是包含制表符偏移量的数组。</span><span class="sxs-lookup"><span data-stu-id="07e00-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="07e00-112">传递给<xref:System.Drawing.StringFormat.SetTabStops%2A>的第一个参数为 0, 指示数组中的第一个偏移量是从位置 0 (边框的左边缘) 度量的。</span><span class="sxs-lookup"><span data-stu-id="07e00-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="07e00-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="07e00-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="07e00-114">前面的示例旨在与 Windows 窗体一起使用, 并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`, <xref:System.Windows.Forms.PaintEventHandler>这是的参数。</span><span class="sxs-lookup"><span data-stu-id="07e00-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e00-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="07e00-115">See also</span></span>

- [<span data-ttu-id="07e00-116">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="07e00-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="07e00-117">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="07e00-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
