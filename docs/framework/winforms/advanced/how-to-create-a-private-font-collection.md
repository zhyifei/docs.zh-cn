---
title: 如何：创建专用的字体集合
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: f78d48c88b72388676f5e7ae963b98d8f1b4beac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210681"
---
# <a name="how-to-create-a-private-font-collection"></a><span data-ttu-id="4d431-102">如何：创建专用的字体集合</span><span class="sxs-lookup"><span data-stu-id="4d431-102">How to: Create a Private Font Collection</span></span>
<span data-ttu-id="4d431-103"><xref:System.Drawing.Text.PrivateFontCollection>类继承自<xref:System.Drawing.Text.FontCollection>抽象基类。</span><span class="sxs-lookup"><span data-stu-id="4d431-103">The <xref:System.Drawing.Text.PrivateFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="4d431-104">可以使用<xref:System.Drawing.Text.PrivateFontCollection>对象来维护一组专门为应用程序的字体。</span><span class="sxs-lookup"><span data-stu-id="4d431-104">You can use a <xref:System.Drawing.Text.PrivateFontCollection> object to maintain a set of fonts specifically for your application.</span></span> <span data-ttu-id="4d431-105">专用字体集合可以包含已安装的系统字体，以及在计算机尚未安装的字体。</span><span class="sxs-lookup"><span data-stu-id="4d431-105">A private font collection can include installed system fonts as well as fonts that have not been installed on the computer.</span></span> <span data-ttu-id="4d431-106">若要将字体文件添加到专用字体集合，调用<xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A>方法的<xref:System.Drawing.Text.PrivateFontCollection>对象。</span><span class="sxs-lookup"><span data-stu-id="4d431-106">To add a font file to a private font collection, call the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> method of a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="4d431-107"><xref:System.Drawing.Text.FontCollection.Families%2A>的属性<xref:System.Drawing.Text.PrivateFontCollection>对象包含的数组<xref:System.Drawing.FontFamily>对象。</span><span class="sxs-lookup"><span data-stu-id="4d431-107">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of a <xref:System.Drawing.Text.PrivateFontCollection> object contains an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
 <span data-ttu-id="4d431-108">专用字体集合中的字体系列数不一定是已添加到集合的字体文件数量相同。</span><span class="sxs-lookup"><span data-stu-id="4d431-108">The number of font families in a private font collection is not necessarily the same as the number of font files that have been added to the collection.</span></span> <span data-ttu-id="4d431-109">例如，假设 ArialBd.tff、 Times.tff 和 TimesBd.tff 文件添加到集合。</span><span class="sxs-lookup"><span data-stu-id="4d431-109">For example, suppose you add the files ArialBd.tff, Times.tff, and TimesBd.tff to a collection.</span></span> <span data-ttu-id="4d431-110">将有三个文件，但在集合中的只有两个系列因为 Times.tff TimesBd.tff 属于同一系列。</span><span class="sxs-lookup"><span data-stu-id="4d431-110">There will be three files but only two families in the collection because Times.tff and TimesBd.tff belong to the same family.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d431-111">示例</span><span class="sxs-lookup"><span data-stu-id="4d431-111">Example</span></span>  
 <span data-ttu-id="4d431-112">以下示例将添加到以下三个字体文件<xref:System.Drawing.Text.PrivateFontCollection>对象：</span><span class="sxs-lookup"><span data-stu-id="4d431-112">The following example adds the following three font files to a <xref:System.Drawing.Text.PrivateFontCollection> object:</span></span>  
  
-   <span data-ttu-id="4d431-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span><span class="sxs-lookup"><span data-stu-id="4d431-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span></span>  
  
-   <span data-ttu-id="4d431-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New，加粗倾斜)</span><span class="sxs-lookup"><span data-stu-id="4d431-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, bold italic)</span></span>  
  
-   <span data-ttu-id="4d431-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman，粗体显示)</span><span class="sxs-lookup"><span data-stu-id="4d431-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span></span>  
  
 <span data-ttu-id="4d431-116">该代码检索的数组<xref:System.Drawing.FontFamily>中的对象<xref:System.Drawing.Text.FontCollection.Families%2A>属性的<xref:System.Drawing.Text.PrivateFontCollection>对象。</span><span class="sxs-lookup"><span data-stu-id="4d431-116">The code retrieves an array of <xref:System.Drawing.FontFamily> objects from the <xref:System.Drawing.Text.FontCollection.Families%2A> property of the <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="4d431-117">每个<xref:System.Drawing.FontFamily>对象在集合中，该代码调用<xref:System.Drawing.FontFamily.IsStyleAvailable%2A>方法，以确定是否有可用的各种样式 （常规、 粗体、 斜体、 粗体斜体、 下划线和删除线）。</span><span class="sxs-lookup"><span data-stu-id="4d431-117">For each <xref:System.Drawing.FontFamily> object in the collection, the code calls the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method to determine whether various styles (regular, bold, italic, bold italic, underline, and strikeout) are available.</span></span> <span data-ttu-id="4d431-118">自变量传递给<xref:System.Drawing.FontFamily.IsStyleAvailable%2A>方法均隶属于<xref:System.Drawing.FontStyle>枚举。</span><span class="sxs-lookup"><span data-stu-id="4d431-118">The arguments passed to the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method are members of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 <span data-ttu-id="4d431-119">如果给定的系列样式组合不可用，<xref:System.Drawing.Font>构造对象时使用该系列和样式。</span><span class="sxs-lookup"><span data-stu-id="4d431-119">If a given family/style combination is available, a <xref:System.Drawing.Font> object is constructed using that family and style.</span></span> <span data-ttu-id="4d431-120">第一个参数传递给<xref:System.Drawing.Font.%23ctor%2A>构造函数是字体系列名称 (不<xref:System.Drawing.FontFamily>对象的所有其他变体情况一样<xref:System.Drawing.Font.%23ctor%2A>构造函数)。</span><span class="sxs-lookup"><span data-stu-id="4d431-120">The first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the font family name (not a <xref:System.Drawing.FontFamily> object as is the case for other variations of the <xref:System.Drawing.Font.%23ctor%2A> constructor).</span></span> <span data-ttu-id="4d431-121">之后<xref:System.Drawing.Font>构造对象时，传递到<xref:System.Drawing.Graphics.DrawString%2A>方法的<xref:System.Drawing.Graphics>类，以显示该系列的名称以及的样式的名称。</span><span class="sxs-lookup"><span data-stu-id="4d431-121">After the <xref:System.Drawing.Font> object is constructed, it is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class to display the family name along with the name of the style.</span></span>  
  
 <span data-ttu-id="4d431-122">以下代码的输出结果类似于下图中所示的输出：</span><span class="sxs-lookup"><span data-stu-id="4d431-122">The output of the following code is similar to the output shown in the following illustration:</span></span>  
  
 ![在各种字体显示文本的屏幕截图。](./media/how-to-create-a-private-font-collection/various-fonts-text-output.png)  
  
 <span data-ttu-id="4d431-124">Arial.tff （其中已添加到下面的代码示例中的专用字体集合） 是 Arial 常规字形的字体文件。</span><span class="sxs-lookup"><span data-stu-id="4d431-124">Arial.tff (which was added to the private font collection in the following code example) is the font file for the Arial regular style.</span></span> <span data-ttu-id="4d431-125">但请注意，该程序的输出显示了几种可用样式不是常规的 Arial 字体系列。</span><span class="sxs-lookup"><span data-stu-id="4d431-125">Note, however, that the program output shows several available styles other than regular for the Arial font family.</span></span> <span data-ttu-id="4d431-126">这是因为[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]可以模拟中的正则样式的粗体、 斜体和粗体斜体样式。</span><span class="sxs-lookup"><span data-stu-id="4d431-126">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold, italic, and bold italic styles from the regular style.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="4d431-127">可以还字形生成下划线和从常规的样式。</span><span class="sxs-lookup"><span data-stu-id="4d431-127">can also produce underlines and strikeouts from the regular style.</span></span>  
  
 <span data-ttu-id="4d431-128">同样，[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]可以模拟从粗体样式或斜体样式的粗体斜体样式。</span><span class="sxs-lookup"><span data-stu-id="4d431-128">Similarly, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold italic style from either the bold style or the italic style.</span></span> <span data-ttu-id="4d431-129">程序输出显示即使 TimesBd.tff (Times New Roman，粗体显示) 是唯一的粗体斜体样式是可用于时间系列集合中的次文件。</span><span class="sxs-lookup"><span data-stu-id="4d431-129">The program output shows that the bold italic style is available for the Times family even though TimesBd.tff (Times New Roman, bold) is the only Times file in the collection.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d431-130">编译代码</span><span class="sxs-lookup"><span data-stu-id="4d431-130">Compiling the Code</span></span>  
 <span data-ttu-id="4d431-131">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="4d431-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d431-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d431-132">See also</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection>
- [<span data-ttu-id="4d431-133">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="4d431-133">Using Fonts and Text</span></span>](using-fonts-and-text.md)
