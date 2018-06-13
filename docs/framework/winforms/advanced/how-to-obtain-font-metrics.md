---
title: 如何：获取字体规格
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 3cc5ee303efe6c703a61eef6c7448979b487f6bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524204"
---
# <a name="how-to-obtain-font-metrics"></a>如何：获取字体规格
<xref:System.Drawing.FontFamily>类提供下列方法来检索特定的系列样式组合的各种指标：  
  
-   <xref:System.Drawing.FontFamily.GetEmHeight%2A>（要）  
  
-   <xref:System.Drawing.FontFamily.GetCellAscent%2A>（要）  
  
-   <xref:System.Drawing.FontFamily.GetCellDescent%2A>（要）  
  
-   <xref:System.Drawing.FontFamily.GetLineSpacing%2A>（要）  
  
 由这些方法返回的数字是采用字体设计单位，因此它们是独立的大小和单位特定于<xref:System.Drawing.Font>对象。  
  
 下图显示的各种度量值。  
  
 ![字体文本](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")  
  
## <a name="example"></a>示例  
 下面的示例显示 Arial 字体系列的正则样式的度量值。 该代码还创建<xref:System.Drawing.Font>具有大小为 16 像素和显示的度量值 （以像素为单位） 对该特定对象 （基于 Arial 系列）<xref:System.Drawing.Font>对象。  
  
 下图显示示例代码的输出。  
  
 ![字体文本](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")  
  
 请注意在上图中的前两个行。 <xref:System.Drawing.Font>对象返回的大小为 16，和<xref:System.Drawing.FontFamily>对象返回的 em 高度为 2048。 这两个数字 （16 和 2048） 是字体设计单位和单位 （在本例中为像素） 之间进行转换的关键<xref:System.Drawing.Font>对象。  
  
 例如，你可以将转换上升从设计单位为像素，如下所示：  
  
 ![字体文本](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")  
  
 下面的代码放置文本垂直通过设置<xref:System.Drawing.PointF.Y%2A>数据成员的<xref:System.Drawing.PointF>对象。 通过增加 y 坐标`font.Height`每个新行的文本。 <xref:System.Drawing.Font.Height%2A>属性<xref:System.Drawing.Font>对象返回的行间距 （以像素为单位） 对该特定<xref:System.Drawing.Font>对象。 在此示例中，数由<xref:System.Drawing.Font.Height%2A>为 19。 请注意，这是通过将行间距度量值转换为像素得到数字 （向上舍入为整数） 相同。  
  
 请注意，全身高度 （也称为大小或 em 大小） 不是上升和下降的总和。 上升和下降的总和称为单元格的高度。 减去内部间隙的单元格高度等于全身高度。 单元格高度加外部间隙等于行间距。  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [使用字体和文本](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
