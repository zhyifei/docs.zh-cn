---
title: 最大程度地提高 WPF 三维性能
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
ms.openlocfilehash: 6677ee3a6d17ea38636d49327d7af22b53bc900e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565433"
---
# <a name="maximize-wpf-3d-performance"></a>最大程度地提高 WPF 三维性能
当你使用[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]生成 3D 控件并将三维场景包括在你的应用程序，务必考虑性能优化。 本主题提供 3D 类和产生性能影响你的应用程序，以及有关使用它们时优化性能的建议的属性的列表。  
  
 本主题假定已深入的了解[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]三维功能。 本文档中的建议适用于"呈现层 2"-大致定义为支持像素着色器版本 2.0 和顶点着色器版本 2.0 的硬件。 有关更多详细信息，请参阅[图形呈现层](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)。  
  
## <a name="performance-impact-high"></a>对性能的影响： 高  
  
|属性|建议|  
|-|-|  
|<xref:System.Windows.Media.Brush>|画笔速度 （最快到最慢）：<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> （已缓存）<br /><br /> <xref:System.Windows.Media.VisualBrush> （已缓存）<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> （缓存）<br /><br /> <xref:System.Windows.Media.VisualBrush> （缓存）|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|设置`Viewport3D.ClipToBounds`为 false 时不需要具有[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]显式剪辑的内容<xref:System.Windows.Controls.Viewport3D>到 Viewport3D 的矩形。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 消除锯齿剪辑可能会很慢，和`ClipToBounds`默认处于启用状态 （较慢） 上<xref:System.Windows.Controls.Viewport3D>。|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|设置`Viewport3D.IsHitTestVisible`为 false 时不需要[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]要考虑的内容<xref:System.Windows.Controls.Viewport3D>执行鼠标命中测试。  命中测试的 3D 内容在软件中完成，并可能会遇到大型网格很慢。 <xref:System.Windows.UIElement.IsHitTestVisible%2A> （较慢） 上默认启用<xref:System.Windows.Controls.Viewport3D>。|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|仅当它们需要不同的材料或转换时，请创建不同的模型。  否则，尝试将合并许多<xref:System.Windows.Media.Media3D.GeometryModel3D>实例具有相同的材料和转换到更大一些<xref:System.Windows.Media.Media3D.GeometryModel3D>和<xref:System.Windows.Media.Media3D.MeshGeometry3D>实例。|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|网格动画-更改每个帧基于网格的各个顶点-并不总是有效地[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。  为了尽量减少对性能的影响更改通知，修改每个顶点时，请在执行每个顶点修改之前分离从可视化树网格。  后已修改网格，将其重新附加到的可视化树。  此外，应尝试尽量减少将以这种方式进行动画处理的网格的大小。|  
|三维抗锯齿|若要提高呈现速度，禁用多级采样上<xref:System.Windows.Controls.Viewport3D>通过设置附加的属性<xref:System.Windows.Media.RenderOptions.EdgeMode%2A>到`Aliased`。  默认情况下上, 禁用三维抗锯齿[!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]并已启用上[!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)]具有 4 个样本每个像素。|  
|Text|在三维场景中实时文本 (因为它在实时<xref:System.Windows.Media.DrawingBrush>或<xref:System.Windows.Media.VisualBrush>) 可能会很慢。 尝试改为使用文本的图像 (通过<xref:System.Windows.Media.Imaging.RenderTargetBitmap>) 除非文本会更改。|  
|<xref:System.Windows.Media.TileBrush>|如果必须使用<xref:System.Windows.Media.VisualBrush>或<xref:System.Windows.Media.DrawingBrush>三维场景中由于画笔的内容不是静态的请尝试缓存画笔 (设置附加的属性<xref:System.Windows.Media.RenderOptions.CachingHint%2A>到`Cache`)。  设置最小和最大刻度失效阈值 (具有附加属性<xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A>和<xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>)，以便缓存的画笔都不会同时仍保持你所需的质量级别过于频繁，重新生成。  默认情况下，<xref:System.Windows.Media.DrawingBrush>和<xref:System.Windows.Media.VisualBrush>不缓存，这意味着，每次使用画笔绘制的内容必须是重新呈现，画笔的整个内容必须首先重新呈现到中间面。|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect> 强制所有受影响的内容，而无需硬件加速呈现。  为了获得最佳性能，不要使用<xref:System.Windows.Media.Effects.BitmapEffect>。|  
  
## <a name="performance-impact-medium"></a>对性能的影响： 中型  
  
|属性|建议|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|当网格定义为邻接通过共享顶点的三角形，这些顶点具有相同的位置、 正常、 和纹理坐标时，定义每个共享的顶点仅一次，然后通过使用索引来定义三角形<xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>。|  
|<xref:System.Windows.Media.ImageBrush>|尝试时你可以显式控制大小减小纹理大小 (当你使用<xref:System.Windows.Media.Imaging.RenderTargetBitmap>和/或<xref:System.Windows.Media.ImageBrush>)。  请注意较低分辨率纹理可以减少视觉质量，因此尝试查找之间质量和性能的最佳平衡。|  
|不透明度|当呈现半透明的三维内容 （如反射）、 画笔或材料上使用的不透明度属性 (通过<xref:System.Windows.Media.Brush.Opacity%2A>或<xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>) 而不是创建单独的半透明<xref:System.Windows.Controls.Viewport3D>通过设置`Viewport3D.Opacity`为小于 1 的值。|  
|<xref:System.Windows.Controls.Viewport3D>|数量降至最低<xref:System.Windows.Controls.Viewport3D>对象正在使用场景中。  将多个三维模型放置在同一 Viewport3D，而无需创建单独 Viewport3D 实例以供每个模型。|  
|<xref:System.Windows.Freezable>|通常是有益重用<xref:System.Windows.Media.Media3D.MeshGeometry3D>， <xref:System.Windows.Media.Media3D.GeometryModel3D>，画笔和材料。  所有都 multiparentable，因为它们源自`Freezable`。|  
|<xref:System.Windows.Freezable>|调用<xref:System.Windows.Freezable.Freeze%2A>上时将保持其属性的可冻结对象的方法在你的应用程序中不变。  冻结可以降低工作集和提高速度。|  
|<xref:System.Windows.Media.Brush>|使用<xref:System.Windows.Media.ImageBrush>而不是<xref:System.Windows.Media.VisualBrush>或<xref:System.Windows.Media.DrawingBrush>时的画笔的内容将不会更改。  二维内容可以转换为<xref:System.Windows.Controls.Image>通过<xref:System.Windows.Media.Imaging.RenderTargetBitmap>，然后再在<xref:System.Windows.Media.ImageBrush>。|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|不要使用<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>除非你确实需要查看的背面你<xref:System.Windows.Media.Media3D.GeometryModel3D>。|  
|<xref:System.Windows.Media.Media3D.Light>|浅色速度 （最快到最慢）：<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|尝试使网格大小小于这些限制：<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>: 20001 个<xref:System.Windows.Media.Media3D.Point3D>实例<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>: 60003 个<xref:System.Int32>实例|  
|<xref:System.Windows.Media.Media3D.Material>|材料速度 （最快到最慢）：<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 三维不一致的方式来取消不可见的画笔 （黑色的环境画笔、 清除画笔等）。  请考虑省略这些场景。|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|每个<xref:System.Windows.Media.Media3D.Material>中<xref:System.Windows.Media.Media3D.MaterialGroup>导致另一个呈现处理过程，因此包含多个材料，甚至简单材料，可以极大地提高你的 GPU 上的填充请求。  中 material 的数量降至最低你<xref:System.Windows.Media.Media3D.MaterialGroup>。|  
  
## <a name="performance-impact-low"></a>对性能的影响： 低  
  
|属性|建议|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|当你不需要动画或数据绑定，而不使用包含多个转换的转换组使用单个<xref:System.Windows.Media.Media3D.MatrixTransform3D>，将其设置为要将否则转换组中独立存在的所有转换的产品。|  
|<xref:System.Windows.Media.Media3D.Light>|灯场景中的数量降至最低。 太多灯在场景中的将强制[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]为回退到软件呈现。  限制大致是 110<xref:System.Windows.Media.Media3D.DirectionalLight>对象，70<xref:System.Windows.Media.Media3D.PointLight>对象或 40<xref:System.Windows.Media.Media3D.SpotLight>对象。|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|分隔将对象从静态对象移通过将它们放在单独<xref:System.Windows.Media.Media3D.ModelVisual3D>实例。  ModelVisual3D 是"多于"<xref:System.Windows.Media.Media3D.GeometryModel3D>因为它将缓存转换后的边界。  GeometryModel3D 经过优化，可以模型ModelVisual3D 经过优化，可以场景节点。  使用 ModelVisual3D 将 GeometryModel3D 的共享的实例放入场景。|  
|<xref:System.Windows.Media.Media3D.Light>|最小化的更改的场景中光源的数目的次数。  浅色计数的每个更改强制着色器重新生成和重新编译，除非该配置具有以前存在 （并且因此缓存具有其着色器）。|  
|浅|黑色光源是不可见，但它们会增加呈现时间;请考虑省略它们。|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|若要尽量减少大型集合中的构造时间[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]，如 MeshGeometry3D <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>， <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>， <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>，和<xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>，预先大小之前值填充的集合。 如果可能，请将传递如数组或列表的集合的构造函数预先填充的数据结构。|  
  
## <a name="see-also"></a>请参阅  
 [3D 图形概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
