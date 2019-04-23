---
title: 如何：使用设计器设置 Windows 窗体控件显示的文本
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: a0f567befb1e0c323dd16fffedec279ff836cbf8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337950"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="2324e-102">如何：使用设计器设置 Windows 窗体控件显示的文本</span><span class="sxs-lookup"><span data-stu-id="2324e-102">How to: Set the Text Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="2324e-103">Windows 窗体控件通常显示与该控件的主要功能相关的一些文本。</span><span class="sxs-lookup"><span data-stu-id="2324e-103">Windows Forms controls typically display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="2324e-104">例如，<xref:System.Windows.Forms.Button>控件通常显示的标题，该值指示当单击该按钮时，将执行什么操作。</span><span class="sxs-lookup"><span data-stu-id="2324e-104">For example, a <xref:System.Windows.Forms.Button> control typically displays a caption that indicates what action will be performed when the button is clicked.</span></span> <span data-ttu-id="2324e-105">对于所有控件而言，都可通过使用 <xref:System.Windows.Forms.Control.Text%2A> 属性来设置或返回文本。</span><span class="sxs-lookup"><span data-stu-id="2324e-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="2324e-106">可以使用 <xref:System.Windows.Forms.Control.Font%2A> 属性更改字体。</span><span class="sxs-lookup"><span data-stu-id="2324e-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a><span data-ttu-id="2324e-107">若要设置的文本和字体与设计器</span><span class="sxs-lookup"><span data-stu-id="2324e-107">To set the text and font with the designer</span></span>  
  
1. <span data-ttu-id="2324e-108">在属性窗口中设置<xref:System.Windows.Forms.Control.Text%2A>为适当的字符串控件属性。</span><span class="sxs-lookup"><span data-stu-id="2324e-108">In the Properties window, set the <xref:System.Windows.Forms.Control.Text%2A> property of the control to an appropriate string.</span></span>  
  
     <span data-ttu-id="2324e-109">若要创建带下划线的快捷键，包含一个 & 号 (&) 将是快捷键的字母前。</span><span class="sxs-lookup"><span data-stu-id="2324e-109">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>  
  
2. <span data-ttu-id="2324e-110">在属性窗口中，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.Control.Font%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="2324e-110">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
     <span data-ttu-id="2324e-111">在标准字体对话框中，选择字体、 字体样式、 大小、 效果 （如删除线或下划线） 和脚本所需。</span><span class="sxs-lookup"><span data-stu-id="2324e-111">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2324e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2324e-112">See also</span></span>

- [<span data-ttu-id="2324e-113">如何：设置显示的文本的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="2324e-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="2324e-114">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="2324e-114">Using Fonts and Text</span></span>](../advanced/using-fonts-and-text.md)
- [<span data-ttu-id="2324e-115">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="2324e-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
