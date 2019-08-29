---
title: 最大程度地提高 WPF 三维性能
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
ms.openlocfilehash: e1a90406423e36dd10b8b108e076fe73f99947f0
ms.sourcegitcommit: 77e33b682db39955e331b8e8eda4ef1925a24e78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2019
ms.locfileid: "70133850"
---
# <a name="maximize-wpf-3d-performance"></a>最大程度地提高 WPF 三维性能
当你使用[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]生成3d 控件并在应用程序中包括三维场景时, 考虑性能优化很重要。 本主题提供了对应用程序性能产生影响的3D 类和属性的列表, 以及在使用这些类和属性时优化性能的建议。  
  
 本主题假定你已了解[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3d 功能。 本文档中的建议适用于 "呈现层 2", 其大致定义为支持像素着色器版本2.0 和顶点着色器版本2.0 的硬件。 有关更多详细信息, 请参阅[图形呈现层](../advanced/graphics-rendering-tiers.md)。  
  
## <a name="performance-impact-high"></a>性能影响:高  
  
|属性|建议|  
|-|-|  
|<xref:System.Windows.Media.Brush>|画笔速度 (从最快到最慢):<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>起来<br /><br /> <xref:System.Windows.Media.VisualBrush>起来<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>高速<br /><br /> <xref:System.Windows.Media.VisualBrush>高速|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|每当`Viewport3D.ClipToBounds`不需要[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]将的内容显式<xref:System.Windows.Controls.Viewport3D>剪裁到 Viewport3D's 矩形时, 将设置为 false。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]消除锯齿剪辑的速度可能非常慢`ClipToBounds` , <xref:System.Windows.Controls.Viewport3D>默认情况下启用 (慢)。|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|如果`Viewport3D.IsHitTestVisible`在执行鼠标命中测试时无[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]需考虑的<xref:System.Windows.Controls.Viewport3D>内容, 则设置为 false。  对3D 内容进行命中测试是在软件中完成的, 很大的网格可能会很慢。 <xref:System.Windows.UIElement.IsHitTestVisible%2A>默认情况下<xref:System.Windows.Controls.Viewport3D>启用 (慢)。|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|仅当需要不同的材料或转换时才创建不同的模型。  否则, 请尝试合并多<xref:System.Windows.Media.Media3D.GeometryModel3D>个具有相同材料的实例, 并将转换为<xref:System.Windows.Media.Media3D.GeometryModel3D>一些<xref:System.Windows.Media.Media3D.MeshGeometry3D>更大的实例。|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|网格动画-基于每个帧更改网格的各个顶点, 在中[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]并非始终有效。  若要在每个顶点被修改时最大程度地降低更改通知的性能影响, 请在执行按顶点修改之前, 先将网格从可视化树中分离出来。  修饰网格后, 将其重新附加到可视化树。  同时, 尝试最大程度地减少将以这种方式进行动画处理的网格的大小。|  
|三维消除锯齿|若要提高呈现速度, 请通过将<xref:System.Windows.Controls.Viewport3D>附加属性<xref:System.Windows.Media.RenderOptions.EdgeMode%2A>设置为来`Aliased`禁用的多级。  默认情况下, 在 Windows 上启用3D 消除, 每像素4个样本。|  
|文本|三维场景中的实时文本 (实时, 因为它处于<xref:System.Windows.Media.DrawingBrush>或<xref:System.Windows.Media.VisualBrush>中) 可能会很慢。 尝试改用文本图像 (通过<xref:System.Windows.Media.Imaging.RenderTargetBitmap>), 除非文本将更改。|  
|<xref:System.Windows.Media.TileBrush>|<xref:System.Windows.Media.VisualBrush>如果在三维场景<xref:System.Windows.Media.DrawingBrush>中必须使用或, 因为画笔的内容不是静态的, 请尝试缓存画笔 (将附加属性<xref:System.Windows.Media.RenderOptions.CachingHint%2A>设置为`Cache`)。  设置最小和最大缩放失效阈值 (包含附加属性<xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A>和<xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>), 以便不会频繁地重新生成缓存的画笔, 同时仍保持所需的质量级别。  默认情况下<xref:System.Windows.Media.DrawingBrush> , <xref:System.Windows.Media.VisualBrush>和不会被缓存, 这意味着, 每次必须重新呈现使用画笔绘制的内容时, 必须先将该画笔的整个内容重新呈现到中间图面。|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect>强制呈现所有受影响的内容而不进行硬件加速。  为了获得最佳性能, 请不要<xref:System.Windows.Media.Effects.BitmapEffect>使用。|  
  
## <a name="performance-impact-medium"></a>性能影响:中等  
  
|Property|建议|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|如果将网格定义为带有共享顶点的相邻三角形, 并且这些顶点具有相同的位置、法线和纹理坐标, 则只需定义一次每个共享顶点, 然后使用<xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>索引定义三角形。|  
|<xref:System.Windows.Media.ImageBrush>|当你显式控制大小 (使用<xref:System.Windows.Media.Imaging.RenderTargetBitmap>和/ <xref:System.Windows.Media.ImageBrush>或) 时, 请尝试最大程度地减小纹理大小。  请注意, 较低的分辨率纹理会降低视觉质量, 因此请尝试在质量和性能之间找到适当的平衡点。|  
|不透明度|呈现半透明三维内容 (如反射) 时, 请使用画笔或材料的不透明度属性 (通过<xref:System.Windows.Media.Brush.Opacity%2A>或<xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>), 而不是通过将<xref:System.Windows.Controls.Viewport3D>设置`Viewport3D.Opacity`为小于1的值来创建单独的半透明。|  
|<xref:System.Windows.Controls.Viewport3D>|最大程度地<xref:System.Windows.Controls.Viewport3D>减少场景中使用的对象数。  在相同的 Viewport3D 中放置许多3D 模型, 而不是为每个模型创建单独的 Viewport3D 实例。|  
|<xref:System.Windows.Freezable>|通常, 重复使用<xref:System.Windows.Media.Media3D.MeshGeometry3D>、 <xref:System.Windows.Media.Media3D.GeometryModel3D>、画笔和材料是有益的。  所有都是 multiparentable, 因为它们是`Freezable`从派生的。|  
|<xref:System.Windows.Freezable>|当应用<xref:System.Windows.Freezable.Freeze%2A>程序中的属性保持不变时, 在可冻结对象上调用方法。  冻结可降低工作集和提高速度。|  
|<xref:System.Windows.Media.Brush>|当画笔的<xref:System.Windows.Media.VisualBrush>内容不会更改时使用<xref:System.Windows.Media.ImageBrush> , 而不是。 <xref:System.Windows.Media.DrawingBrush>  可以<xref:System.Windows.Controls.Image> <xref:System.Windows.Media.ImageBrush>通过<xref:System.Windows.Media.Imaging.RenderTargetBitmap>将二维内容转换为, 然后在中使用。|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|不要使用<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> , 除非确实需要查看的背面<xref:System.Windows.Media.Media3D.GeometryModel3D>。|  
|<xref:System.Windows.Media.Media3D.Light>|光速 (速度最快到最慢):<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|尝试在这些限制下保留网格大小:<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>：20001 <xref:System.Windows.Media.Media3D.Point3D>实例<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>：60003 <xref:System.Int32>实例|  
|<xref:System.Windows.Media.Media3D.Material>|材料速度 (从最快到最慢):<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]3D 不会以一致的方式选择不使用不可见的画笔 (黑色环境画笔、清除画笔等)。  请考虑从场景中省略这些。|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|中<xref:System.Windows.Media.Media3D.Material>的每<xref:System.Windows.Media.Media3D.MaterialGroup>个都将导致另一个呈现阶段, 其中包括许多材料, 甚至是简单的材料, 这会大幅增加对 GPU 的填充需求。  最大程度地减少中<xref:System.Windows.Media.Media3D.MaterialGroup>的资料数量。|  
  
## <a name="performance-impact-low"></a>性能影响:低  
  
|Property|建议|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|如果不需要动画或数据绑定, 请使用单个<xref:System.Windows.Media.Media3D.MatrixTransform3D>, 而不是使用包含多个转换的转换组, 而是将其设置为在转换组中独立存在的所有转换的乘积。|  
|<xref:System.Windows.Media.Media3D.Light>|最大程度地减少场景中光线的数目。 场景中的光太多将强制[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]回退到软件呈现。  限制大约为 110 <xref:System.Windows.Media.Media3D.DirectionalLight>个对象、70 <xref:System.Windows.Media.Media3D.PointLight>个对象或 40 <xref:System.Windows.Media.Media3D.SpotLight>个对象。|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|将对象放入不同<xref:System.Windows.Media.Media3D.ModelVisual3D>的实例, 从而将其从静态对象中分离出来。  ModelVisual3D 比<xref:System.Windows.Media.Media3D.GeometryModel3D> "更粗", 因为它会缓存已转换的边界。  GeometryModel3D 优化为模型;ModelVisual3D 优化为场景节点。  使用 ModelVisual3D 将 GeometryModel3D 的共享实例放入场景。|  
|<xref:System.Windows.Media.Media3D.Light>|最大程度地减少场景中灯光数量的更改次数。  对于每次更改的光源, 都将强制重新生成和重新编译着色器, 除非该配置以前已存在 (因此缓存了其着色器)。|  
|浅|黑色光源不可见, 但会将其添加到渲染时间;请考虑省略它们。|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|若要最大程度地减少[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]中大型集合的构造时间, 如 MeshGeometry3D's <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>、 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>、 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>和, 请在值填充之前预先调整集合的大小。 如果可能, 请传递集合的构造函数预填充的数据结构, 例如数组或列表。|  
  
## <a name="see-also"></a>请参阅

- [3D 图形概述](3-d-graphics-overview.md)
