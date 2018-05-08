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
ms.openlocfilehash: 824d42c40b07e8662395e7a1286b9a5a6112c415
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-private-font-collection"></a>如何：创建专用的字体集合
<xref:System.Drawing.Text.PrivateFontCollection>类继承自<xref:System.Drawing.Text.FontCollection>抽象基类。 你可以使用<xref:System.Drawing.Text.PrivateFontCollection>要维护一组专门为你的应用程序的字体的对象。 专用字体集合可以包含已安装的系统字体，以及在计算机尚未安装的字体。 若要将字体文件添加到专用字体集合中，调用<xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A>方法<xref:System.Drawing.Text.PrivateFontCollection>对象。  
  
 <xref:System.Drawing.Text.FontCollection.Families%2A>属性<xref:System.Drawing.Text.PrivateFontCollection>对象包含的数组<xref:System.Drawing.FontFamily>对象。  
  
 专用字体集合中的字体系列数不一定是已添加到集合的字体文件数相同。 例如，假设 ArialBd.tff、 Times.tff 和 TimesBd.tff 的文件添加到集合。 将有三个文件，但在集合中的只有两个系列因为 Times.tff 和 TimesBd.tff 属于相同的系列。  
  
## <a name="example"></a>示例  
 下面的示例将添加到以下三个字体文件<xref:System.Drawing.Text.PrivateFontCollection>对象：  
  
-   C:\\*systemroot*\Fonts\Arial.tff (Arial，正则)  
  
-   C:\\*systemroot*\Fonts\CourBI.tff （媒体新功能，加粗倾斜）  
  
-   C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman，粗体)  
  
 此代码会检索的数组<xref:System.Drawing.FontFamily>对象从<xref:System.Drawing.Text.FontCollection.Families%2A>属性<xref:System.Drawing.Text.PrivateFontCollection>对象。  
  
 每个<xref:System.Drawing.FontFamily>对象在集合中，该代码调用<xref:System.Drawing.FontFamily.IsStyleAvailable%2A>方法来确定是否有各种样式 （常规、 粗体、 斜体、 加粗倾斜、 下划线和删除线）。 自变量传递给<xref:System.Drawing.FontFamily.IsStyleAvailable%2A>方法属于<xref:System.Drawing.FontStyle>枚举。  
  
 如果给定的系列样式组合不可用，<xref:System.Drawing.Font>构造对象时使用该系列和样式。 第一个自变量传递给<xref:System.Drawing.Font.%23ctor%2A>构造函数是字体系列名称 (不<xref:System.Drawing.FontFamily>对象的所有其他变体的情况一样<xref:System.Drawing.Font.%23ctor%2A>构造函数)。 后<xref:System.Drawing.Font>构造对象时，传递到<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>类来显示家族名称以及样式的名称。  
  
 下面的输出是代码的类似于下图中所示的输出。  
  
 ![字体文本](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")  
  
 Arial.tff （该功能已添加到下面的代码示例中的专用字体集合） 是宋体正则样式的字体文件。 但是，请注意，该程序的输出显示不是 Arial 字体系列的常规的几种可用样式。 这是因为[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]可以模拟的正则样式中的粗体、 斜体和加粗的斜体样式。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 此外可以生成下划线和正则样式中的字形。  
  
 同样，[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]可以模拟从粗体或斜体样式的粗体斜体样式。 程序输出显示即使 TimesBd.tff (Times New Roman，粗体) 是唯一是否可用的时间系列粗体斜体样式集合中的次文件。  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [使用字体和文本](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
