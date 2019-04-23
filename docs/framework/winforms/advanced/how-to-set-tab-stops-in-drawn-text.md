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
ms.openlocfilehash: 68dbebfc4fab773fe749f9443d0c61883099d2ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197485"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="aa496-102">如何：在绘制的文本中设置制表位</span><span class="sxs-lookup"><span data-stu-id="aa496-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="aa496-103">可以通过调用设置文本的所有制表位<xref:System.Drawing.StringFormat.SetTabStops%2A>方法<xref:System.Drawing.StringFormat>对象，然后将其传递<xref:System.Drawing.StringFormat>对象传递给<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="aa496-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa496-104"><xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType>不支持添加制表位与绘制的文本，尽管您可以扩展现有选项卡会停止使用的作用<xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType>标志。</span><span class="sxs-lookup"><span data-stu-id="aa496-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa496-105">示例</span><span class="sxs-lookup"><span data-stu-id="aa496-105">Example</span></span>  
 <span data-ttu-id="aa496-106">下面的示例在 150、 250 和 350 设置制表位。</span><span class="sxs-lookup"><span data-stu-id="aa496-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="aa496-107">然后，代码显示选项卡式的列表的名称和测试分数。</span><span class="sxs-lookup"><span data-stu-id="aa496-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="aa496-108">下图显示的选项卡式的文本：</span><span class="sxs-lookup"><span data-stu-id="aa496-108">The following illustration shows the tabbed text:</span></span>  
  
 ![显示选项卡式的姓名和分数列表的屏幕截图。](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 <span data-ttu-id="aa496-110">以下代码将传递到两个参数<xref:System.Drawing.StringFormat.SetTabStops%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="aa496-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="aa496-111">第二个参数是一个数组，包含制表位偏移量。</span><span class="sxs-lookup"><span data-stu-id="aa496-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="aa496-112">第一个参数传递给<xref:System.Drawing.StringFormat.SetTabStops%2A>为 0，指示数组中的第一个偏移量从边界的矩形的左边缘的位置 0，来度量。</span><span class="sxs-lookup"><span data-stu-id="aa496-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aa496-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="aa496-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="aa496-114">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="aa496-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa496-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa496-115">See also</span></span>

- [<span data-ttu-id="aa496-116">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="aa496-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="aa496-117">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="aa496-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
