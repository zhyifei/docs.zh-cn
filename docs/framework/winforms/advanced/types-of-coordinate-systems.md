---
title: 坐标系类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: ff53942cb90721d5411f99b261f90366d039e151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="types-of-coordinate-systems"></a>坐标系类型
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 使用三个坐标空间： world、 页和设备。 世界坐标是用于模型对特定图形世界的坐标，将传递到.NET Framework 中的方法的坐标。 页坐标是指由绘图图面，如窗体或控件使用的坐标系统。 设备坐标是由进行绘制，如屏幕或张纸的物理设备的坐标。 进行调用时`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`，传递给点<xref:System.Drawing.Graphics.DrawLine%2A>方法-`(0, 0)`和`(160, 80)`-位于世界坐标空间。 之前[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]可以在屏幕上绘制线条、 坐标传递的转换序列。 一个转换，调用的世界变换，将世界坐标转换为的页坐标，并调用页转换，另一个转换将页坐标转换为设备坐标。  
  
## <a name="transforms-and-coordinate-systems"></a>转换和坐标系统  
 假设你想要使用的原点在正文中的工作区，而不是左上角的坐标系统。 例如，假设你想要从工作区左边缘的 100 个像素和从客户端区域的顶部 50 像素的原点。 下图显示了这样的坐标系统。  
  
 ![坐标系统](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 进行调用时`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`，获取显示在下图中的行。  
  
 ![坐标系统](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 您在三个坐标空间中的行的终结点的坐标如下所示：  
  
|||  
|-|-|  
|World|（0，0） 到 （160、 80）|  
|页|（100，50） 到 （260，130）|  
|设备|（100，50） 到 （260，130）|  
  
 请注意的页坐标空间的左上角的工作区中; 具有其源这将始终是这种情况。 另请注意，由于的度量单位是像素，设备坐标是相同的页坐标。 如果你设置的度量单位为像素为单位 （例如，英寸为单位） 以外，设备坐标将不同于页坐标。  
  
 世界变换，将映射到的页坐标世界坐标，会保留在<xref:System.Drawing.Graphics.Transform%2A>属性<xref:System.Drawing.Graphics>类。 在前面的示例中，世界转换是在 x 方向翻译 100 单元和 y 方向的 50 个单位。 下面的示例设置的世界变换<xref:System.Drawing.Graphics>对象，然后使用该<xref:System.Drawing.Graphics>对象中要绘制前面的图中所示的行：  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 页转换将页坐标映射到设备坐标。 <xref:System.Drawing.Graphics>类提供<xref:System.Drawing.Graphics.PageUnit%2A>和<xref:System.Drawing.Graphics.PageScale%2A>操作页转换的属性。 <xref:System.Drawing.Graphics>类还提供了两个只读属性，<xref:System.Drawing.Graphics.DpiX%2A>和<xref:System.Drawing.Graphics.DpiY%2A>，以检查水平和垂直每英寸点数为显示设备。  
  
 你可以使用<xref:System.Drawing.Graphics.PageUnit%2A>属性<xref:System.Drawing.Graphics>类指定一个像素以外的度量单位。  
  
> [!NOTE]
>  无法设置<xref:System.Drawing.Graphics.PageUnit%2A>属性<xref:System.Drawing.GraphicsUnit.World>，如这不是一个物理单元，将会引发异常。  
  
 下面的示例绘制中的一行 （0，0） 到 （2，1），其中 （2，1） 的点是 2 英寸向右和向下的 1 英寸，从点 （0，0）：  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  如果不指定钢笔的宽度，构造笔时，前面的示例将绘制一英寸宽的行。 你可以在第二个参数中指定钢笔的宽度<xref:System.Drawing.Pen>构造函数：  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 如果我们假定显示设备具有 96 每英寸点数为沿水平方向和垂直方向中每英寸 96 点，前面示例中的行的终结点将具有三个坐标空间中的以下坐标：  
  
|||  
|-|-|  
|World|（0，0） 到 （2，1）|  
|页|（0，0） 到 （2，1）|  
|设备|(0，0，到 192 (96）|  
  
 请注意，由于的源的全局坐标空间是在客户端区域的左上角，页坐标与世界坐标相同。  
  
 你可以组合世界变换和页变换以实现各种效果。 例如，假设你想要使用英寸作为度量单位，并且你想要从左边缘的客户端区域和从客户端区域的顶部的 1/2 英寸的 2 英寸你坐标系统的原点。 下面的示例设置世界变换和页变换的<xref:System.Drawing.Graphics>对象，然后绘制中的一行 （0，0） 到 （2，1）：  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 下图显示的行和坐标系统。  
  
 ![坐标系统](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 如果我们假定显示设备具有 96 每英寸点数为沿水平方向和垂直方向中每英寸 96 点，前面示例中的行的终结点将具有三个坐标空间中的以下坐标：  
  
|||  
|-|-|  
|World|（0，0） 到 （2，1）|  
|页|（2，0.5） 到 （4、 1.5）|  
|设备|（192，48） 到 （384，144）|  
  
## <a name="see-also"></a>请参阅  
 [坐标系统和转换](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [转换的矩阵表示形式](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)
