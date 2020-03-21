---
title: 使用嵌套的 Graphics 容器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
ms.openlocfilehash: 460ebb37ee62691a1e282f756840121fd378ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182467"
---
# <a name="using-nested-graphics-containers"></a>使用嵌套的 Graphics 容器
GDI+ 提供了可用于临时替换或增强<xref:System.Drawing.Graphics>对象中部分状态的容器。 通过调用<xref:System.Drawing.Graphics.BeginContainer%2A><xref:System.Drawing.Graphics>对象的方法创建容器。 您可以重复调用<xref:System.Drawing.Graphics.BeginContainer%2A>以形成嵌套容器。 到 的每个<xref:System.Drawing.Graphics.BeginContainer%2A>调用都必须与 调用<xref:System.Drawing.Graphics.EndContainer%2A>配对。  
  
## <a name="transformations-in-nested-containers"></a>嵌套容器中的转换  
 下面的示例在该<xref:System.Drawing.Graphics><xref:System.Drawing.Graphics>对象中创建一个对象和一个容器。 <xref:System.Drawing.Graphics>物体的世界变换是 x 方向的平移 100 个单位，y 方向为 80 个单位。 容器的世界变换是30度的旋转。 代码发出调用`DrawRectangle(pen, -60, -30, 120, 60)`两次。 第<xref:System.Drawing.Graphics.DrawRectangle%2A>一个调用是在容器内;也就是说，调用位于 调用<xref:System.Drawing.Graphics.BeginContainer%2A>和<xref:System.Drawing.Graphics.EndContainer%2A>之间的调用中。 的第二个调用<xref:System.Drawing.Graphics.DrawRectangle%2A>是在调用<xref:System.Drawing.Graphics.EndContainer%2A>之后。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 在前面的代码中，从容器内部绘制的矩形首先由容器的世界变换（旋转）转换，然后由<xref:System.Drawing.Graphics>对象的世界变换（转换）转换。 仅由<xref:System.Drawing.Graphics>对象的世界变换（转换）从容器外部绘制的矩形进行转换。 下图显示了两个矩形：
  
 ![显示嵌套容器的插图。](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>在嵌套容器中剪切  
 下面的示例演示嵌套容器如何处理裁剪区域。 该代码在该<xref:System.Drawing.Graphics><xref:System.Drawing.Graphics>对象中创建一个对象和一个容器。 <xref:System.Drawing.Graphics>对象的裁剪区域是一个矩形，容器的裁剪区域是一个椭圆。 代码对<xref:System.Drawing.Graphics.DrawLine%2A>该方法进行两次调用。 向的第一个<xref:System.Drawing.Graphics.DrawLine%2A>调用在容器内，第二个调用<xref:System.Drawing.Graphics.DrawLine%2A>在容器外部（在调用 之后）。 <xref:System.Drawing.Graphics.EndContainer%2A> 第一行由两个裁剪区域的交点剪切。 第二行仅由<xref:System.Drawing.Graphics>对象的矩形裁剪区域进行剪切。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 下图显示了两条剪贴线：
  
 ![显示带有剪切线的嵌套容器的插图。](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 如前两个示例所示，转换和剪切区域在嵌套容器中是累积的。 如果设置容器和<xref:System.Drawing.Graphics>对象的世界变换，则两个转换将应用于从容器内部提取的项目。 将首先应用容器的变换，然后应用<xref:System.Drawing.Graphics>对象的变换。 如果设置容器和<xref:System.Drawing.Graphics>对象的剪切区域，则从容器内部绘制的项目将由两个裁剪区域的交点剪切。  
  
## <a name="quality-settings-in-nested-containers"></a>嵌套容器中的质量设置  
 嵌套容器中<xref:System.Drawing.Graphics.SmoothingMode%2A>的质量<xref:System.Drawing.Graphics.TextRenderingHint%2A>设置 （、等） 不是累积的;相反，容器的质量设置会暂时替换<xref:System.Drawing.Graphics>对象的质量设置。 创建新容器时，该容器的质量设置将设置为默认值。 例如，假设您有一个<xref:System.Drawing.Graphics>具有平滑模式的对象。 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 创建容器时，容器内的平滑模式是默认平滑模式。 您可以自由设置容器的平滑模式，并且从容器内部绘制的任何项目都将根据您设置的模式绘制。 调用后绘制的项目<xref:System.Drawing.Graphics.EndContainer%2A>将根据调用<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias><xref:System.Drawing.Graphics.BeginContainer%2A>之前就位的平滑模式 （） 绘制。  
  
## <a name="several-layers-of-nested-containers"></a>嵌套容器的几个层  
 您不限于对象中的一个<xref:System.Drawing.Graphics>容器。 您可以创建一系列容器，每个容器都嵌套在前面，并且可以指定每个嵌套容器的世界转换、剪切区域和质量设置。 如果从最内层容器内调用绘图方法，则转换将按顺序应用，从最内层容器开始，到最外层容器结束。 从最内侧容器内绘制的项目将由所有剪切区域的交集剪切。  
  
 下面的示例创建一个<xref:System.Drawing.Graphics>对象，并将其文本呈现提示设置到<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>。 代码创建两个容器，一个嵌套在另一个容器中。 外部容器的文本呈现提示设置为<xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>，内部容器的文本呈现提示设置为<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>。 代码绘制三个字符串：一个来自内部容器，一个来自外部容器，一个来自<xref:System.Drawing.Graphics>对象本身。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 下图显示了三个字符串。 从内部容器和对象绘制的<xref:System.Drawing.Graphics>字符串通过抗锯齿平滑。 从外部容器绘制的字符串不会通过反锯齿平滑，<xref:System.Drawing.Graphics.TextRenderingHint%2A>因为属性设置为<xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>。  
  
 ![显示从嵌套容器中提取的字符串的插图。](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics>
- [管理 Graphics 对象的状态](managing-the-state-of-a-graphics-object.md)
