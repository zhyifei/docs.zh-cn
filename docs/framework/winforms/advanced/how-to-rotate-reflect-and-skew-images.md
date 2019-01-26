---
title: 如何：旋转、 反射和倾斜图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 2150e7797095b88227b499ec5481a3ce521270e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667906"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>如何：旋转、 反射和倾斜图像
可以旋转、 反射和倾斜图像通过指定的原始图像的左上角、 右上方和左下角的目标点。 三个目标点确定将原始矩形图像映射到一个平行四边形的仿射转换。  
  
## <a name="example"></a>示例  
 例如，假设原始图像是一个矩形，左上角位于 （0，0），在右上角 （100，0），并在左下角 （0，50）。 现在假设您将它们映射三个指向目标点，如下所示。  
  
|原始点|目标点|  
|--------------------|-----------------------|  
|左上角 （0，0）|(200, 20)|  
|右上方 （100，0）|(110, 100)|  
|左下角 （0，50）|(250, 30)|  
  
 下图显示了原始映像和映像映射到的平行四边形。 原始图像具有已倾斜、 反映、 旋转、 和转换。 原始图像的上边缘沿 x 轴映射到通过运行的行 （200，20） 和 （110，100）。 沿左边缘原始图像的 y 轴映射到通过运行的行 （200，20） 和 （250，30）。  
  
 ![条带化](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 下图显示了类似的转换应用于摄影图像。  
  
 ![转换的 Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 下图显示了类似的转换应用于图元文件。  
  
 ![转换图元文件](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 下面的示例生成第一个图例中所显示的图像。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。 请务必替换`Stripes.bmp`替换为你的系统上有效的图像的路径。  
  
## <a name="see-also"></a>请参阅
- [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
