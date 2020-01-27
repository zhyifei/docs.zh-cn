---
title: 最大化三维性能
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
ms.openlocfilehash: 414a4677a1e05cd69c382e35194328d6ce1bddf9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744592"
---
# <a name="maximize-wpf-3d-performance"></a>WPF 3D 성능 최대화
当你使用 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 生成3D 控件并在应用程序中包括三维场景时，考虑性能优化很重要。 本主题提供了对应用程序性能产生影响的3D 类和属性的列表，以及在使用这些类和属性时优化性能的建议。  
  
 本主题假定你对 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D 功能的高级了解。 本文档中的建议适用于 "呈现层 2"，其大致定义为支持像素着色器版本2.0 和顶点着色器版本2.0 的硬件。 有关更多详细信息，请参阅[图形呈现层](../advanced/graphics-rendering-tiers.md)。  
  
## <a name="performance-impact-high"></a>性能影响：高  
  
|속성|권장 구성|  
|-|-|  
|<xref:System.Windows.Media.Brush>|画笔速度（从最快到最慢）：<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> （已缓存）<br /><br /> <xref:System.Windows.Media.VisualBrush> （已缓存）<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> （未缓存）<br /><br /> <xref:System.Windows.Media.VisualBrush> （未缓存）|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|每当无需 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 将 <xref:System.Windows.Controls.Viewport3D> 内容显式剪裁到 Viewport3D's 矩形时，将 `Viewport3D.ClipToBounds` 设置为 false。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 抗锯齿剪辑可能非常慢，并且默认情况下 `ClipToBounds` 在 <xref:System.Windows.Controls.Viewport3D>上启用（慢）。|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|当你在执行鼠标命中测试时无需 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 考虑 <xref:System.Windows.Controls.Viewport3D> 内容时，将 `Viewport3D.IsHitTestVisible` 设置为 false。  对3D 内容进行命中测试是在软件中完成的，很大的网格可能会很慢。 默认情况下，<xref:System.Windows.UIElement.IsHitTestVisible%2A> 在 <xref:System.Windows.Controls.Viewport3D>上启用（慢）。|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|仅当需要不同的材料或转换时才创建不同的模型。  否则，请尝试合并多个具有相同材料的 <xref:System.Windows.Media.Media3D.GeometryModel3D> 实例，并将其转换为更大的 <xref:System.Windows.Media.Media3D.GeometryModel3D> 和 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 的实例。|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|网格动画-基于每个帧更改网格的各个顶点，在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]中并不总是有效。  若要在每个顶点被修改时最大程度地降低更改通知的性能影响，请在执行按顶点修改之前，先将网格从可视化树中分离出来。  修饰网格后，将其重新附加到可视化树。  同时，尝试最大程度地减少将以这种方式进行动画处理的网格的大小。|  
|三维消除锯齿|若要提高呈现速度，请通过将附加属性 <xref:System.Windows.Media.RenderOptions.EdgeMode%2A> 设置为 `Aliased`，禁用 <xref:System.Windows.Controls.Viewport3D> 上的多级多级。  默认情况下，在 Windows 上启用3D 消除，每像素4个样本。|  
|텍스트|三维场景中的实时文本（实时，因为它处于 <xref:System.Windows.Media.DrawingBrush> 或 <xref:System.Windows.Media.VisualBrush>中）可能会很慢。 尝试改用文本图像（通过 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>），除非文本将更改。|  
|<xref:System.Windows.Media.TileBrush>|如果在三维场景中必须使用 <xref:System.Windows.Media.VisualBrush> 或 <xref:System.Windows.Media.DrawingBrush>，因为画笔的内容不是静态的，请尝试缓存画笔（将附加属性 <xref:System.Windows.Media.RenderOptions.CachingHint%2A> 设置为 `Cache`）。  设置最小和最大缩放失效阈值（其中包含附加属性 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> 和 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>），以便不会频繁地重新生成缓存的画笔，同时仍保持所需的质量级别。  默认情况下，不缓存 <xref:System.Windows.Media.DrawingBrush> 和 <xref:System.Windows.Media.VisualBrush>，这意味着，每次必须重新呈现使用画笔绘制的内容时，必须先将该画笔的整个内容重新呈现到中间图面。|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect> 强制呈现所有受影响的内容，而不进行硬件加速。  为了获得最佳性能，请不要使用 <xref:System.Windows.Media.Effects.BitmapEffect>。|  
  
## <a name="performance-impact-medium"></a>性能影响：中型  
  
|속성|권장 구성|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|如果将网格定义为带有共享顶点的相邻三角形，并且这些顶点具有相同的位置、法线和纹理坐标，则仅定义每个共享顶点一次，然后使用 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>按索引定义三角形。|  
|<xref:System.Windows.Media.ImageBrush>|在显式控制大小（使用 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 和/或 <xref:System.Windows.Media.ImageBrush>）时，请尝试最大程度地减小纹理大小。  请注意，较低的分辨率纹理会降低视觉质量，因此请尝试在质量和性能之间找到适当的平衡点。|  
|蒙|呈现半透明三维内容（如反射）时，请使用画笔或材料的不透明度属性（通过 <xref:System.Windows.Media.Brush.Opacity%2A> 或 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>），而不是通过将 `Viewport3D.Opacity` 设置为小于1的值来创建单独的半透明 <xref:System.Windows.Controls.Viewport3D>。|  
|<xref:System.Windows.Controls.Viewport3D>|最大程度地减少场景中正在使用的 <xref:System.Windows.Controls.Viewport3D> 对象的数量。  在相同的 Viewport3D 中放置许多3D 模型，而不是为每个模型创建单独的 Viewport3D 实例。|  
|<xref:System.Windows.Freezable>|通常，重复使用 <xref:System.Windows.Media.Media3D.MeshGeometry3D>、<xref:System.Windows.Media.Media3D.GeometryModel3D>、画笔和材料是有益的。  所有这些都是 multiparentable，因为它们派生自 `Freezable`。|  
|<xref:System.Windows.Freezable>|当可冻结对象在应用程序中的属性保持不变时，对其调用 <xref:System.Windows.Freezable.Freeze%2A> 方法。  冻结可降低工作集和提高速度。|  
|<xref:System.Windows.Media.Brush>|如果画笔的内容不会更改，请使用 <xref:System.Windows.Media.ImageBrush> 而不是 <xref:System.Windows.Media.VisualBrush> 或 <xref:System.Windows.Media.DrawingBrush>。  可以通过 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 将二维内容转换为 <xref:System.Windows.Controls.Image>，然后在 <xref:System.Windows.Media.ImageBrush>中使用。|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|不要使用 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>，除非确实需要查看 <xref:System.Windows.Media.Media3D.GeometryModel3D>的背面。|  
|<xref:System.Windows.Media.Media3D.Light>|光速（速度最快到最慢）：<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|尝试在这些限制下保留网格大小：<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>： 20001 <xref:System.Windows.Media.Media3D.Point3D> 实例<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>： 60003 <xref:System.Int32> 实例|  
|<xref:System.Windows.Media.Media3D.Material>|材料速度（从最快到最慢）：<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 3D 不会以一致的方式退出不可见的画笔（黑色环境画笔、清除画笔等）。  请考虑从场景中省略这些。|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|<xref:System.Windows.Media.Media3D.MaterialGroup> 中的每个 <xref:System.Windows.Media.Media3D.Material> 都会导致另一个呈现过程，其中包括许多材料（甚至是简单的材料）会大幅增加对 GPU 的填充需求。  最大程度地减少 <xref:System.Windows.Media.Media3D.MaterialGroup>的材料数量。|  
  
## <a name="performance-impact-low"></a>性能影响：低  
  
|속성|권장 구성|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|如果不需要动画或数据绑定，而是使用单个 <xref:System.Windows.Media.Media3D.MatrixTransform3D>，而不是使用包含多个转换的转换组，请将其设置为在转换组中独立存在的所有转换的乘积。|  
|<xref:System.Windows.Media.Media3D.Light>|最大程度地减少场景中光线的数目。 场景中的光太多将强制 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 回退到软件呈现。  限制大约为 110 <xref:System.Windows.Media.Media3D.DirectionalLight> 对象、70 <xref:System.Windows.Media.Media3D.PointLight> 对象或 40 <xref:System.Windows.Media.Media3D.SpotLight> 对象。|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|通过将对象放置在单独的 <xref:System.Windows.Media.Media3D.ModelVisual3D> 实例中，将它们从静态对象分离。  ModelVisual3D 比 <xref:System.Windows.Media.Media3D.GeometryModel3D> "更粗"，因为它会缓存已转换的边界。  GeometryModel3D 优化为模型;ModelVisual3D 优化为场景节点。  使用 ModelVisual3D 将 GeometryModel3D 的共享实例放入场景。|  
|<xref:System.Windows.Media.Media3D.Light>|最大程度地减少场景中灯光数量的更改次数。  对于每次更改的光源，都将强制重新生成和重新编译着色器，除非该配置以前已存在（因此缓存了其着色器）。|  
|밝게|黑色光源不可见，但会将其添加到渲染时间;请考虑省略它们。|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|为了最大程度地减少 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]中大型集合（如 MeshGeometry3D's <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>、<xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>、<xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>和 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>）的构造时间，在值填充之前预先调整集合的大小。 如果可能，请传递集合的构造函数预填充的数据结构，例如数组或列表。|  
  
## <a name="see-also"></a>另请参阅

- [3차원 그래픽 개요](3-d-graphics-overview.md)
