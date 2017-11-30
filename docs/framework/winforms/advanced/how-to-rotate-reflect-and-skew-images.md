---
title: "如何：旋转、反射和扭曲图像"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eaa6286731d196dad387e1648644ca3e8103da03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>如何：旋转、反射和扭曲图像
你可以旋转、 反射和扭曲图像通过指定的原始图像的左上角、 右上角和左下角的目标点。 三个目标点确定映射到一个平行四边形的原始矩形图像仿射转换。  
  
## <a name="example"></a>示例  
 例如，假设原始图像是一个具有在左上角的矩形 （0，0），在右上角 （100，0），并在左下角 （0，50）。 现在假设你将它们映射三个指向目标点，如下所示。  
  
|原始点|目标点|  
|--------------------|-----------------------|  
|左上角 （0，0）|(200, 20)|  
|右上角 （100，0）|(110, 100)|  
|左下方 （0，50）|(250, 30)|  
  
 下图显示原始的图像和图像映射到的平行四边形。 原始图像已偏差、 反映、 旋转和转换。 原始图像的上边缘沿 x 轴映射到通过运行的行 （200，20） 和 （110，100）。 原始图像的左边缘沿 y 轴映射到通过运行的行 （200，20） 和 （250，30）。  
  
 ![条带化](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 下图显示应用到照片图像的类似变换。  
  
 ![转换的 Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 下图显示类似转换应用于图元文件。  
  
 ![转换图元文件](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 下面的示例生成第一个图中所显示的图像。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 请确保将`Stripes.bmp`替换为你系统上有效的映像的路径。  
  
## <a name="see-also"></a>另请参阅  
 [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
