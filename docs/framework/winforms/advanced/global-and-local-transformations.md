---
title: "全局转换和局部转换"
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
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e8d05bd0c3e76d643d56b652c8849eef1045ea8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="global-and-local-transformations"></a>全局转换和局部转换
全局转换是一个转换，它适用于通过绘制每一项给定<xref:System.Drawing.Graphics>对象。 与此相反，本地转换是适用于特定项要绘制一个转换。  
  
## <a name="global-transformations"></a>全局转换  
 若要创建的全局转换，构造<xref:System.Drawing.Graphics>对象，以及然后操作其<xref:System.Drawing.Graphics.Transform%2A>属性。 <xref:System.Drawing.Graphics.Transform%2A>属性是<xref:System.Drawing.Drawing2D.Matrix>对象，因此它可以存放仿射转换的任何序列。 转换存储在<xref:System.Drawing.Graphics.Transform%2A>称为世界转换的属性。 <xref:System.Drawing.Graphics>类提供了构建复合世界转换的几种方法： <xref:System.Drawing.Graphics.MultiplyTransform%2A>， <xref:System.Drawing.Graphics.RotateTransform%2A>， <xref:System.Drawing.Graphics.ScaleTransform%2A>，和<xref:System.Drawing.Graphics.TranslateTransform%2A>。 下面的示例绘制一个椭圆两次： 一次之前创建的世界变换和之后的一次。 转换第一次在 y 方向，0.5 的按比例调整然后平移在 x 方向的 50 个单位并且然后将旋转 30 度。  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 下图显示了所涉及的转换矩阵。  
  
 ![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
>  在前面的示例中，坐标系统，这是客户端区域的左上角原点顺转动椭圆。 这将生成不同的结果比轮换围绕其自身中心椭圆。  
  
## <a name="local-transformations"></a>局部变换  
 本地转换适用于要绘制的特定项。 例如，<xref:System.Drawing.Drawing2D.GraphicsPath>对象具有<xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A>，可以将转换该路径的数据点的方法。 下面的示例绘制一个具有任何转换的矩形和具有旋转转换的路径。 （假定没有任何世界转换。）  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 你可以组合与局部变换以实现各种结果的世界转换。 例如，可以使用世界转换修改坐标系统，并使用局部变换旋转和缩放绘制在新的坐标系统上的对象。  
  
 假设您希望一个坐标系统中已从工作区左边缘的原点 200 像素以及从客户端区域的顶部 150 像素。 此外，假设你想要像素，且 x 轴指向右侧和朝上 y 轴的度量单位。 默认坐标系统有指向下，y 轴，因此你需要在水平轴执行反射。 下图显示此类反射的矩阵。  
  
 ![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 接下来，假定你需要执行转换 200 个单位的向右和向下的 150 个单位。  
  
 下面的示例建立刚刚介绍的设置的世界变换的坐标系<xref:System.Drawing.Graphics>对象。  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 下面的代码 （在前面的示例中的末尾放置） 创建包含单个矩形与新的坐标系统的原点在其左下角的路径。 一次不使用局部变换和局部变换，将一次填充的矩形。 按 2 的 30 度旋转后跟的系数水平缩放包含的局部变换。  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 下图显示新的坐标系统和两个矩形。  
  
 ![转换](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>请参阅  
 [坐标系统和转换](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [在托管 GDI+ 中使用转换](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
