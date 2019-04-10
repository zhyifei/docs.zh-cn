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
ms.openlocfilehash: 0a9dcd00d4bc3e64ae4fc9a1d4884fac18521825
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181215"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="7b743-102">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="7b743-102">How to: Construct Font Families and Fonts</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="7b743-103">分组为字体系列字样相同但不同的样式使用的字体。</span><span class="sxs-lookup"><span data-stu-id="7b743-103">groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="7b743-104">例如，Arial 字体系列包含以下字体：</span><span class="sxs-lookup"><span data-stu-id="7b743-104">For example, the Arial font family contains the following fonts:</span></span>  
  
-   <span data-ttu-id="7b743-105">Arial 常规</span><span class="sxs-lookup"><span data-stu-id="7b743-105">Arial Regular</span></span>  
  
-   <span data-ttu-id="7b743-106">Arial 粗体</span><span class="sxs-lookup"><span data-stu-id="7b743-106">Arial Bold</span></span>  
  
-   <span data-ttu-id="7b743-107">Arial 斜体</span><span class="sxs-lookup"><span data-stu-id="7b743-107">Arial Italic</span></span>  
  
-   <span data-ttu-id="7b743-108">宋体</span><span class="sxs-lookup"><span data-stu-id="7b743-108">Arial Bold Italic</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="7b743-109">使用四种字形形成系列： 常规、 粗体、 斜体和粗体斜体。</span><span class="sxs-lookup"><span data-stu-id="7b743-109">uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="7b743-110">如形容词*缩小*并*舍入*不被视为样式; 而不是它们是系列名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="7b743-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="7b743-111">例如，Arial 窄是字体系列包含下列成员：</span><span class="sxs-lookup"><span data-stu-id="7b743-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
-   <span data-ttu-id="7b743-112">Arial 窄常规</span><span class="sxs-lookup"><span data-stu-id="7b743-112">Arial Narrow Regular</span></span>  
  
-   <span data-ttu-id="7b743-113">姚粗体</span><span class="sxs-lookup"><span data-stu-id="7b743-113">Arial Narrow Bold</span></span>  
  
-   <span data-ttu-id="7b743-114">Arial 窄斜体</span><span class="sxs-lookup"><span data-stu-id="7b743-114">Arial Narrow Italic</span></span>  
  
-   <span data-ttu-id="7b743-115">Arial 窄的加粗倾斜</span><span class="sxs-lookup"><span data-stu-id="7b743-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="7b743-116">您可以绘制与文本之前[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，则需构造<xref:System.Drawing.FontFamily>对象和一个<xref:System.Drawing.Font>对象。</span><span class="sxs-lookup"><span data-stu-id="7b743-116">Before you can draw text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="7b743-117"><xref:System.Drawing.FontFamily>对象指定 （例如，Arial） 字样和<xref:System.Drawing.Font>对象指定的大小、 样式和单位。</span><span class="sxs-lookup"><span data-stu-id="7b743-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b743-118">示例</span><span class="sxs-lookup"><span data-stu-id="7b743-118">Example</span></span>  
 <span data-ttu-id="7b743-119">下面的示例构造正则样式 Arial 字体大小为 16 像素。</span><span class="sxs-lookup"><span data-stu-id="7b743-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="7b743-120">下面的代码中的第一个参数传递给<xref:System.Drawing.Font.%23ctor%2A>构造函数是<xref:System.Drawing.FontFamily>对象。</span><span class="sxs-lookup"><span data-stu-id="7b743-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="7b743-121">第二个参数指定度量单位由第四个参数标识的字体的大小。</span><span class="sxs-lookup"><span data-stu-id="7b743-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="7b743-122">第三个参数标识的样式。</span><span class="sxs-lookup"><span data-stu-id="7b743-122">The third argument identifies the style.</span></span>  
  
 <xref:System.Drawing.GraphicsUnit.Pixel> <span data-ttu-id="7b743-123">是的成员<xref:System.Drawing.GraphicsUnit>枚举，并<xref:System.Drawing.FontStyle.Regular>属于<xref:System.Drawing.FontStyle>枚举。</span><span class="sxs-lookup"><span data-stu-id="7b743-123">is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7b743-124">编译代码</span><span class="sxs-lookup"><span data-stu-id="7b743-124">Compiling the Code</span></span>  
 <span data-ttu-id="7b743-125">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs>`e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="7b743-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b743-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b743-126">See also</span></span>

- [<span data-ttu-id="7b743-127">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="7b743-127">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="7b743-128">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="7b743-128">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
