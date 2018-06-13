---
title: 如何：构造字体系列和字体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: ceace5950ec135ea4d52081da7d1de7a820583ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520885"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="813f2-102">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="813f2-102">How to: Construct Font Families and Fonts</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="813f2-103"> 分组到字体系列的字体的字体相同但不同的样式。</span><span class="sxs-lookup"><span data-stu-id="813f2-103"> groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="813f2-104">例如，Arial 字体系列包含以下字体：</span><span class="sxs-lookup"><span data-stu-id="813f2-104">For example, the Arial font family contains the following fonts:</span></span>  
  
-   <span data-ttu-id="813f2-105">Arial 常规</span><span class="sxs-lookup"><span data-stu-id="813f2-105">Arial Regular</span></span>  
  
-   <span data-ttu-id="813f2-106">Arial 粗体</span><span class="sxs-lookup"><span data-stu-id="813f2-106">Arial Bold</span></span>  
  
-   <span data-ttu-id="813f2-107">Arial 斜体</span><span class="sxs-lookup"><span data-stu-id="813f2-107">Arial Italic</span></span>  
  
-   <span data-ttu-id="813f2-108">宋体</span><span class="sxs-lookup"><span data-stu-id="813f2-108">Arial Bold Italic</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="813f2-109"> 使用窗体系列的四种样式： 常规、 粗体、 斜体和粗斜体。</span><span class="sxs-lookup"><span data-stu-id="813f2-109"> uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="813f2-110">如形容词*缩小*和*舍入*不被视为样式; 而是它们是系列名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="813f2-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="813f2-111">例如，Arial 窄是字体系列包含下列成员：</span><span class="sxs-lookup"><span data-stu-id="813f2-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
-   <span data-ttu-id="813f2-112">Arial 窄常规</span><span class="sxs-lookup"><span data-stu-id="813f2-112">Arial Narrow Regular</span></span>  
  
-   <span data-ttu-id="813f2-113">粗体的姚</span><span class="sxs-lookup"><span data-stu-id="813f2-113">Arial Narrow Bold</span></span>  
  
-   <span data-ttu-id="813f2-114">Arial 窄斜体</span><span class="sxs-lookup"><span data-stu-id="813f2-114">Arial Narrow Italic</span></span>  
  
-   <span data-ttu-id="813f2-115">窄宋体</span><span class="sxs-lookup"><span data-stu-id="813f2-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="813f2-116">你可以绘制文本之前[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，你需要构造<xref:System.Drawing.FontFamily>对象和一个<xref:System.Drawing.Font>对象。</span><span class="sxs-lookup"><span data-stu-id="813f2-116">Before you can draw text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="813f2-117"><xref:System.Drawing.FontFamily>对象指定 （例如，Arial） 字样和<xref:System.Drawing.Font>对象指定大小、 样式和单位。</span><span class="sxs-lookup"><span data-stu-id="813f2-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="813f2-118">示例</span><span class="sxs-lookup"><span data-stu-id="813f2-118">Example</span></span>  
 <span data-ttu-id="813f2-119">下面的示例构造正则样式 Arial 字体大小为 16 个像素。</span><span class="sxs-lookup"><span data-stu-id="813f2-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="813f2-120">在下面的代码中，第一个自变量传递给<xref:System.Drawing.Font.%23ctor%2A>构造函数是<xref:System.Drawing.FontFamily>对象。</span><span class="sxs-lookup"><span data-stu-id="813f2-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="813f2-121">第二个参数指定的测量单位由第四个参数标识的字体的大小。</span><span class="sxs-lookup"><span data-stu-id="813f2-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="813f2-122">第三个参数标识的样式。</span><span class="sxs-lookup"><span data-stu-id="813f2-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="813f2-123"><xref:System.Drawing.GraphicsUnit.Pixel> 为属于<xref:System.Drawing.GraphicsUnit>枚举，和<xref:System.Drawing.FontStyle.Regular>为属于<xref:System.Drawing.FontStyle>枚举。</span><span class="sxs-lookup"><span data-stu-id="813f2-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="813f2-124">编译代码</span><span class="sxs-lookup"><span data-stu-id="813f2-124">Compiling the Code</span></span>  
 <span data-ttu-id="813f2-125">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="813f2-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="813f2-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="813f2-126">See Also</span></span>  
 [<span data-ttu-id="813f2-127">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="813f2-127">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="813f2-128">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="813f2-128">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
