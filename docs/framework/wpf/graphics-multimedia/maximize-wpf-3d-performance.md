---
title: 最大化 3D 性能
ms.date: 03/30/2017
helpviewer_keywords:
- 3D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
ms.openlocfilehash: 3825ea8e57c6863e2ee654072efda623db21c2a8
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111993"
---
# <a name="maximize-wpf-3d-performance"></a>最大程度地提高 WPF 三维性能
当您使用[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]生成 3D 控件并在应用程序中包含 3D 场景时，考虑性能优化非常重要。 本主题提供了对应用程序具有性能影响的 3D 类和属性的列表，以及用于在使用时优化性能的建议。  
  
 本主题假定对 3D[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]功能的高级理解。 本文档中的建议适用于"呈现第 2 层"-大致定义为支持像素底影版本 2.0 和顶点底影版 2.0 的硬件。 有关详细信息，请参阅[图形呈现层](../advanced/graphics-rendering-tiers.md)。  
  
## <a name="performance-impact-high"></a>性能影响：高  
  
|properties|建议|  
|-|-|  
|<xref:System.Windows.Media.Brush>|画笔速度（最快到最慢）：<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>（缓存）<br /><br /> <xref:System.Windows.Media.VisualBrush>（缓存）<br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush>（未缓存）<br /><br /> <xref:System.Windows.Media.VisualBrush>（未缓存）|  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|只要`Viewport3D.ClipToBounds`不需要[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]显式剪辑 到 Viewport3D 矩形的内容<xref:System.Windows.Controls.Viewport3D>，则设置为 false。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]防锯齿裁剪可能非常慢，并且`ClipToBounds`默认在 上<xref:System.Windows.Controls.Viewport3D>启用（慢速）。|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|每当`Viewport3D.IsHitTestVisible`执行鼠标命中测试时，只要[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]不考虑 的内容<xref:System.Windows.Controls.Viewport3D>，则设置为 false。  命中测试 3D 内容在软件中完成，并且使用大型网中速度很慢。 <xref:System.Windows.UIElement.IsHitTestVisible%2A>默认情况下启用（慢速）在<xref:System.Windows.Controls.Viewport3D>。|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|仅当不同模型需要不同的材质或变换时，才创建不同的模型。  否则，请尝试将多个<xref:System.Windows.Media.Media3D.GeometryModel3D>实例与相同的材质合并，并将转换为几个较大的<xref:System.Windows.Media.Media3D.GeometryModel3D>实例。 <xref:System.Windows.Media.Media3D.MeshGeometry3D>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|网格动画 （按帧更改网格的各个顶点） 并不总是有效[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。  为了在修改每个顶点时将更改通知的性能影响降至最低，请先从可视树中分离网格，然后再执行每个顶点修改。  修改网格后，将其重新附加到可视化树。  此外，尝试最小化以这种方式进行动画处理的网数的大小。|  
|3D 抗锯齿|要提高渲染速度，<xref:System.Windows.Controls.Viewport3D>请通过将附加属性<xref:System.Windows.Media.RenderOptions.EdgeMode%2A>设置为 禁用 上的多`Aliased`采样。  默认情况下，在 Windows 上启用 3D 防锯齿，每像素有 4 个样本。|  
|文本|3D 场景中的实时文本（实时，因为它位于<xref:System.Windows.Media.DrawingBrush>或<xref:System.Windows.Media.VisualBrush>） 中，速度可能很慢。 请尝试使用文本的图像（通过<xref:System.Windows.Media.Imaging.RenderTargetBitmap>），除非文本将更改。|  
|<xref:System.Windows.Media.TileBrush>|如果由于画笔的内容不是<xref:System.Windows.Media.VisualBrush>静态的<xref:System.Windows.Media.DrawingBrush>，必须在 3D 场景中使用 或 ， 请尝试缓存画笔（将附加属性<xref:System.Windows.Media.RenderOptions.CachingHint%2A>设置为 。 `Cache`  设置最小和最大比例失效阈值（具有附加属性<xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A>和<xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A>），以便缓存的画笔不会过于频繁地重新生成，同时仍保持所需的质量级别。  默认情况下，<xref:System.Windows.Media.DrawingBrush>并且<xref:System.Windows.Media.VisualBrush>不会缓存，这意味着每次必须重新渲染使用画笔绘制的内容时，必须首先将画笔的整个内容重新渲染到中间曲面。|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect>强制呈现所有受影响的内容，而不进行硬件加速。  为获得最佳性能，请勿使用<xref:System.Windows.Media.Effects.BitmapEffect>。|  
  
## <a name="performance-impact-medium"></a>性能影响：中等  
  
|properties|建议|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|当网格定义为具有共享顶点的顶点的靠边三角形，并且这些顶点具有相同的位置、法线和纹理坐标时，仅定义每个共享顶点一次，然后使用 索引定义三角形<xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>。|  
|<xref:System.Windows.Media.ImageBrush>|当您对大小具有显式控制时（当您使用<xref:System.Windows.Media.Imaging.RenderTargetBitmap>和/或 时），尝试最小化纹理大小。 <xref:System.Windows.Media.ImageBrush>  请注意，较低的分辨率纹理可能会降低视觉质量，因此请尝试在质量和性能之间找到适当的平衡。|  
|不透明度|渲染半透明 3D 内容（如反射）时，请使用画笔或材质上的不透明属性（<xref:System.Windows.Media.Brush.Opacity%2A>通过或<xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A>），而不是通过设置为<xref:System.Windows.Controls.Viewport3D>`Viewport3D.Opacity`小于 1 的值来创建单独的半透明。|  
|<xref:System.Windows.Controls.Viewport3D>|最小化场景中使用的对象<xref:System.Windows.Controls.Viewport3D>数。  将许多 3D 模型放在相同的 Viewport3D 中，而不是为每个模型创建单独的 Viewport3D 实例。|  
|<xref:System.Windows.Freezable>|通常，重复使用<xref:System.Windows.Media.Media3D.MeshGeometry3D>、、<xref:System.Windows.Media.Media3D.GeometryModel3D>画笔和材质是有好处的。  它们都是多父级的，因为它们派生自`Freezable`。|  
|<xref:System.Windows.Freezable>|在应用程序中<xref:System.Windows.Freezable.Freeze%2A>，当其属性保持不变时，在"可冻结"上调用该方法。  冻结可以减少工作集和提高速度。|  
|<xref:System.Windows.Media.Brush>|使用<xref:System.Windows.Media.ImageBrush>而不是<xref:System.Windows.Media.VisualBrush>或<xref:System.Windows.Media.DrawingBrush>当画笔的内容不会更改时。  2D 内容可以转换为通通<xref:System.Windows.Controls.Image>，<xref:System.Windows.Media.Imaging.RenderTargetBitmap>然后在 中使用<xref:System.Windows.Media.ImageBrush>。|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|不要使用<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>，除非你确实需要看到你的<xref:System.Windows.Media.Media3D.GeometryModel3D>背面。|  
|<xref:System.Windows.Media.Media3D.Light>|光速（最快到最慢）：<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|尝试将网格大小保持在以下限制下：<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>： 20，001<xref:System.Windows.Media.Media3D.Point3D>个实例<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>： 60，003<xref:System.Int32>个实例|  
|<xref:System.Windows.Media.Media3D.Material>|材料速度（最快到最慢）：<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]3D 不会以一致的方式选择退出不可见的画笔（黑色环境画笔、透明画笔等）。  请考虑从场景中省略这些。|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|每个<xref:System.Windows.Media.Media3D.Material>渲染<xref:System.Windows.Media.Media3D.MaterialGroup>通道都会导致另一个渲染通道，因此包括许多材质，甚至简单的材料，可以显著提高 GPU 的填充需求。  最小化 中的材料数量<xref:System.Windows.Media.Media3D.MaterialGroup>。|  
  
## <a name="performance-impact-low"></a>性能影响：低  
  
|properties|建议|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|当不需要动画或数据绑定时，不使用包含多个转换的转换组，而是使用单个<xref:System.Windows.Media.Media3D.MatrixTransform3D>，将其设置为转换组中独立存在的所有转换的组成。|  
|<xref:System.Windows.Media.Media3D.Light>|最小化场景中的灯光数。 场景中的灯光过多将迫使[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]其回退到软件渲染。  限制大约 110<xref:System.Windows.Media.Media3D.DirectionalLight>个对象、70<xref:System.Windows.Media.Media3D.PointLight>个对象或<xref:System.Windows.Media.Media3D.SpotLight>40 个对象。|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|通过将移动对象放在单独的实例中，将移动对象<xref:System.Windows.Media.Media3D.ModelVisual3D>与静态对象分开。  ModelVisual3D 比缓存转换的边界<xref:System.Windows.Media.Media3D.GeometryModel3D>"更重"。  几何模型3D被优化为模型;ModelVisual3D 已优化为场景节点。  使用 ModelVisual3D 将几何模型 3D 的共享实例放入场景中。|  
|<xref:System.Windows.Media.Media3D.Light>|最小化更改场景中灯光数的次数。  光计数的每个更改都会强制进行底带再生和重新编译，除非该配置以前存在（因此缓存了其底带）。|  
|浅色|黑光不可见，但它们会增加渲染时间;考虑省略它们。|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|为了最小化 在 中[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]的大型集合的构造时间，例如 MeshGeometry3D<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>的<xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>、和<xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>，在值填充之前预调整集合的大小。 如果可能，传递集合的构造函数预填充的数据结构，如数组或列表。|  
  
## <a name="see-also"></a>另请参阅

- [3D 图形概述](3-d-graphics-overview.md)
