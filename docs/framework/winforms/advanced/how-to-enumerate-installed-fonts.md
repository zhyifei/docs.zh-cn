---
title: 如何：枚举已安装的字体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 9f31880cbfb42c03122fc7d2730b9ca89db49226
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524434"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="68a00-102">如何：枚举已安装的字体</span><span class="sxs-lookup"><span data-stu-id="68a00-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="68a00-103"><xref:System.Drawing.Text.InstalledFontCollection>类继承自<xref:System.Drawing.Text.FontCollection>抽象基类。</span><span class="sxs-lookup"><span data-stu-id="68a00-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="68a00-104">你可以使用<xref:System.Drawing.Text.InstalledFontCollection>对象枚举计算机上安装的字体。</span><span class="sxs-lookup"><span data-stu-id="68a00-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="68a00-105"><xref:System.Drawing.Text.FontCollection.Families%2A>属性<xref:System.Drawing.Text.InstalledFontCollection>对象是一个数组<xref:System.Drawing.FontFamily>对象。</span><span class="sxs-lookup"><span data-stu-id="68a00-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68a00-106">示例</span><span class="sxs-lookup"><span data-stu-id="68a00-106">Example</span></span>  
 <span data-ttu-id="68a00-107">下面的示例列出计算机上安装的所有字体系列的名称。</span><span class="sxs-lookup"><span data-stu-id="68a00-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="68a00-108">此代码会检索<xref:System.Drawing.FontFamily.Name%2A>每个属性<xref:System.Drawing.FontFamily>中返回的数组对象<xref:System.Drawing.Text.FontCollection.Families%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="68a00-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="68a00-109">系列名称检索，因为它们被串联到窗体的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="68a00-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="68a00-110">则<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>类在矩形中绘制的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="68a00-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="68a00-111">如果你运行此代码示例，输出将类似于下图中所示。</span><span class="sxs-lookup"><span data-stu-id="68a00-111">If you run the example code, the output will be similar to that shown in the following illustration.</span></span>  
  
 <span data-ttu-id="68a00-112">![安装字体](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span><span class="sxs-lookup"><span data-stu-id="68a00-112">![Installed Fonts](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="68a00-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="68a00-113">Compiling the Code</span></span>  
 <span data-ttu-id="68a00-114">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。</span><span class="sxs-lookup"><span data-stu-id="68a00-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="68a00-115">此外，您应该导入<xref:System.Drawing.Text>命名空间。</span><span class="sxs-lookup"><span data-stu-id="68a00-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a00-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="68a00-116">See Also</span></span>  
 [<span data-ttu-id="68a00-117">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="68a00-117">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
