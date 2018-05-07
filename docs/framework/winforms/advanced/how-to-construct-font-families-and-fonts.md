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
---
# <a name="how-to-construct-font-families-and-fonts"></a>如何：构造字体系列和字体
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 分组到字体系列的字体的字体相同但不同的样式。 例如，Arial 字体系列包含以下字体：  
  
-   Arial 常规  
  
-   Arial 粗体  
  
-   Arial 斜体  
  
-   宋体  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 使用窗体系列的四种样式： 常规、 粗体、 斜体和粗斜体。 如形容词*缩小*和*舍入*不被视为样式; 而是它们是系列名称的一部分。 例如，Arial 窄是字体系列包含下列成员：  
  
-   Arial 窄常规  
  
-   粗体的姚  
  
-   Arial 窄斜体  
  
-   窄宋体  
  
 你可以绘制文本之前[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，你需要构造<xref:System.Drawing.FontFamily>对象和一个<xref:System.Drawing.Font>对象。 <xref:System.Drawing.FontFamily>对象指定 （例如，Arial） 字样和<xref:System.Drawing.Font>对象指定大小、 样式和单位。  
  
## <a name="example"></a>示例  
 下面的示例构造正则样式 Arial 字体大小为 16 个像素。 在下面的代码中，第一个自变量传递给<xref:System.Drawing.Font.%23ctor%2A>构造函数是<xref:System.Drawing.FontFamily>对象。 第二个参数指定的测量单位由第四个参数标识的字体的大小。 第三个参数标识的样式。  
  
 <xref:System.Drawing.GraphicsUnit.Pixel> 为属于<xref:System.Drawing.GraphicsUnit>枚举，和<xref:System.Drawing.FontStyle.Regular>为属于<xref:System.Drawing.FontStyle>枚举。  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅  
 [使用字体和文本](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
