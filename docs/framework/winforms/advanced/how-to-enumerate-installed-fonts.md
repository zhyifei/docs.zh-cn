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
ms.openlocfilehash: 34234ee0400e1d2ca36f2f559b63d282f590ca0d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709874"
---
# <a name="how-to-enumerate-installed-fonts"></a>如何：枚举已安装的字体
<xref:System.Drawing.Text.InstalledFontCollection>类继承自<xref:System.Drawing.Text.FontCollection>抽象基类。 可以使用<xref:System.Drawing.Text.InstalledFontCollection>对象枚举在计算机上安装的字体。 <xref:System.Drawing.Text.FontCollection.Families%2A>的属性<xref:System.Drawing.Text.InstalledFontCollection>对象是一个数组<xref:System.Drawing.FontFamily>对象。  
  
## <a name="example"></a>示例  
 下面的示例列出所有计算机上安装的字体系列的名称。 代码检索<xref:System.Drawing.FontFamily.Name%2A>每个属性<xref:System.Drawing.FontFamily>中返回的数组对象<xref:System.Drawing.Text.FontCollection.Families%2A>属性。 如检索字体系列名称时，系统会将它们连接起来到窗体的逗号分隔列表。 然后<xref:System.Drawing.Graphics.DrawString%2A>方法的<xref:System.Drawing.Graphics>类在矩形中绘制的以逗号分隔列表。  
  
 如果你运行示例代码，输出将类似于下图中所示。  
  
 ![安装字体](./media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。 此外，应导入<xref:System.Drawing.Text>命名空间。  
  
## <a name="see-also"></a>请参阅
- [使用字体和文本](using-fonts-and-text.md)
