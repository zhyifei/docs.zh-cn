---
title: 三维图形概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D graphics [WPF]
- graphics [WPF], 3-D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: 6d44f27ccd82d535436be03092c3864e3155d1d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="3-d-graphics-overview"></a>三维图形概述
<a name="introduction"></a>通过 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 功能，开发人员可以使用标记和程序代码绘制和转换 3D 图形，并对其进行动画处理。 开发人员可以合并 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] 和 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 图形以创建丰富的控件、提供复杂的数据图解，或者增强用户对应用程序界面的体验。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 支持并非旨在提供功能齐全的游戏开发平台。 本主题概述了 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 图形系统中的 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 功能。  
 
  
<a name="threed_in_2d"></a>   
## <a name="3-d-in-a-2-d-container"></a>2D 容器中的 3D  
 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 图形中的内容[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]封装在一个元素， <xref:System.Windows.Controls.Viewport3D>，该元素可以参与二维元素结构。 图形系统将<xref:System.Windows.Controls.Viewport3D>作为一个二维的可见元素，如中的许多其他[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 <xref:System.Windows.Controls.Viewport3D> 为窗口函数-视区-三维场景。 更准确地说，它是 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 场景所投影到的图面。  
  
 中的传统[!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]应用程序，使用<xref:System.Windows.Controls.Viewport3D>就像另一个容器元素，如网格或画布。  尽管可以使用<xref:System.Windows.Controls.Viewport3D>与其他[!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]你在相同的场景关系图中绘制对象，不能内部渗透[!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]和[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]对象内<xref:System.Windows.Controls.Viewport3D>。  本主题将重点介绍如何绘制[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]内的图形<xref:System.Windows.Controls.Viewport3D>。  
  
<a name="coord_space"></a>   
## <a name="3-d-coordinate-space"></a>3D 坐标空间  
 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 图形的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 坐标系将原点定位在呈现区域（通常是屏幕）的左上角。 在 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 系统中，x 轴上的正值朝右，y 轴上的正值朝下。  但是，在 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 坐标系中，原点位于呈现区域的中心，x 轴上的正值朝右，但是 y 轴上的正值朝上，z 轴上的正值从原点向外朝向观察者。  
  
 ![坐标系统](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-1.png "CoordSystem 1")  
传统的 2D 和 3D 坐标系表示形式  
  
 由这些轴定义的空间是 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 对象在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的固定参考框架。 当在该空间中生成模型并创建光源和照相机以查看这些模型时，一定要在向每个模型应用转换时，将固定参考框架或“全局空间”与为该模型创建的局部参考框架区分开。 另请记住，根据光源和照相机设置，全局空间中的对象可能会看上去完全不同或者根本不可见，但是照相机的位置不会改变对象在全局空间中的位置。  
  
<a name="cameras"></a>   
## <a name="cameras-and-projections"></a>照相机和投影  
 处理 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 的开发人员习惯于将绘图基元置于二维屏幕上。 创建 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 场景时，务必记住实际上是要创建 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 对象的 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 表示形式。 由于 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 场景的外观会因观察者的观察位置而异，因此必须指定观察位置。 <xref:System.Windows.Media.Media3D.Camera>类，可指定有关此角度来看[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]场景。  
  
 了解 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 场景如何在 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 图面上表示的另一种方法就是将场景描述为到观察表面上的投影。 <xref:System.Windows.Media.Media3D.ProjectionCamera>允许您指定不同的投影和其属性以更改观察者如何查看[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]模型。 A<xref:System.Windows.Media.Media3D.PerspectiveCamera>指定 foreshortens 场景的投影。  换而言之，<xref:System.Windows.Media.Media3D.PerspectiveCamera>提供消失点透视。  可以指定照相机在场景坐标系中的位置、照相机的方向和视野以及用来定义场景中“向上”方向的矢量。 下图说明了<xref:System.Windows.Media.Media3D.PerspectiveCamera>的投影。  
  
 <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>和<xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A>属性<xref:System.Windows.Media.Media3D.ProjectionCamera>限制的照相机的投影的范围。 由于照相机可以位于场景中的任何位置，因此照相机实际上可能会位于模型内部或者紧靠模型，这使正确区分对象变得很困难。  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A> 使用此选项可以指定从相机超过该值将不绘制对象的最小距离。  相反，<xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A>可指定超出该不将绘制对象，这样可以确保不会在场景中包含对象太远是可以识别的照相机的距离。  
  
 ![照相机设置](../../../../docs/framework/wpf/graphics-multimedia/media/coordsystem-6.png "CoordSystem 6")  
照相机位置  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera> 指定的正交投影[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]模型到[!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]可视化图面。 与其他照相机一样，它指定位置、观察方向和“向上”方向。 与不同<xref:System.Windows.Media.Media3D.PerspectiveCamera>，但<xref:System.Windows.Media.Media3D.OrthographicCamera>描述不包含透视收缩投影。 换而言之，<xref:System.Windows.Media.Media3D.OrthographicCamera>说明边是并行的而不是一个在相机上的点的边满足这种查看。 下图显示相同的模型，如使用查看<xref:System.Windows.Media.Media3D.PerspectiveCamera>和<xref:System.Windows.Media.Media3D.OrthographicCamera>。  
  
 ![正射透视投影](../../../../docs/framework/wpf/graphics-multimedia/media/camera-projections4.png "Camera_projections4")  
透视投影和正投影  
  
 下面的代码演示一些典型的照相机设置。  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>   
## <a name="model-and-mesh-primitives"></a>模型和网格基元  
  
 <xref:System.Windows.Media.Media3D.Model3D> 是表示泛型的抽象基类[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]对象。 若要生成[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]场景，您需要某些对象，若要查看，而且构成场景关系图的对象派生自<xref:System.Windows.Media.Media3D.Model3D>。 目前，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]支持建模与几何图形<xref:System.Windows.Media.Media3D.GeometryModel3D>。 <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>此模型的属性采用网格基元。  
  
 若要生成模型，请首先生成一个基元或网格。 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 基元是一系列构成单个 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 实体的顶点。 大多数 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 系统都提供在最简单的闭合图（由三个顶点定义的三角形）上建模的基元。  由于三角形的三个点在一个平面上，因此可以继续添加三角形，以便对网格这样较为复杂的形状建模。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]系统当前提供<xref:System.Windows.Media.Media3D.MeshGeometry3D>类，该编辑器可以指定任何几何图形; 当前不支持预定义[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]基元如球体和三次方窗体。 开始创建<xref:System.Windows.Media.Media3D.MeshGeometry3D>通过指定的顶点列表的三角形作为其<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>属性。 每个顶点指定为<xref:System.Windows.Media.Media3D.Point3D>。  （在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 中，将该属性指定为三个一组的数字列表，每组中的三个数字表示每个顶点的坐标）。根据网格的几何形状，网格可能会由多个三角形组成，有些三角形共用相同的角（顶点）。 若要正确绘制网格，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 需要有关哪些顶点由哪些三角形共用的信息。 通过指定与三角形索引的列表提供此信息<xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>属性。 此列表指定点中指定的顺序<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>列表将确定一个三角形。  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 在前面的示例中，<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>列表指定八个顶点来定义多维数据集调整的网格。 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>属性指定的三个索引的 12 个组的列表。  该列表中的每个数是指的偏移量<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>列表。  例如，由指定的前三个顶点<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>列表是否 (1,1,0) (0,1,0) 和 (0,0,0)。 指定的前三个索引<xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>列表是 0、 2 和 1，其中第三，对应于第一个和第二个中的点<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>列表。 因此，构成立方体模型的第一个三角形将按照从 (1,1,0) 到 (0,1,0) 再到 (0,0,0) 的顺序组合而成，其余的十一个三角形将按照类似方式确定。  
  
 你可以继续通过指定的值定义模型<xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>和<xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>属性。  为了呈现模型的图面，图形系统需要有关曲面在任何给定三角形上的朝向信息。 图形系统使用此信息来针对该模型进行照明计算：正对光源的图面比偏离光源的图面显得更亮。 尽管 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 可以使用位置坐标来确定默认的法矢量，但是你还可以指定不同的法矢量来近似计算曲面的外观。  
  
 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>属性指定的集合<xref:System.Windows.Point>告诉图形系统如何确定如何将纹理绘制到网格的顶点的坐标映射的 s。 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> 指定为介于 0 与 1，（含) 之间的值。  与<xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>图形系统可以计算属性，默认纹理坐标，但你可以选择设置不同的纹理坐标，包括对部分重复模式，例如对纹理的映射进行控制。 有关纹理坐标的详细信息，可在后续主题或 Managed Direct3D SDK 中找到。  
  
 下面的示例演示如何在过程代码中创建立方体模型的一面。 请注意，可以将整个立方体绘制为单个 GeometryModel3D；此示例将该立方体面绘制为一个不同的模型，以便在以后向每个面应用不同的纹理。  
  
 [!code-csharp[3doverview#3DOverview3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>   
## <a name="applying-materials-to-the-model"></a>向模型应用材料  
  
 为了使网格看上去像三维对象，必须向其应用纹理，以便覆盖由顶点和三角形定义的图面，从而使其可以由照相机照明和投影。 在[!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)]，你使用<xref:System.Windows.Media.Brush>类应用于的屏幕的区域的颜色、 模式、 渐变或其他可视内容。  但是，[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 对象的外观是照明模型的功能，而不只是应用于它们的颜色或图案。 实际对象的图面质量不同，它们反射光的方式也会有所不同：光亮的图面与粗糙或不光滑的图面看上去不同，某些对象似乎可以吸收光，而某些对象似乎能够发光。 可以向 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 对象应用与应用于 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 对象的完全相同的画笔，但是不能直接应用它们。  
  
 若要定义的模型的面的特征[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用<xref:System.Windows.Media.Media3D.Material>抽象类。 Material 的具体子类用来确定模型图面的某些外观特征，每个子类还提供一个可以向其传递 SolidColorBrush、TileBrush 或 VisualBrush 的 Brush 属性。  
  
-   <xref:System.Windows.Media.Media3D.DiffuseMaterial> 指定将向该模型应用画笔，就好像该模型已漫射照明。 使用 DiffuseMaterial 与直接针对 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 模型使用画笔非常相似；模型表面不反射光，就好像是自发光一样。  
  
-   <xref:System.Windows.Media.Media3D.SpecularMaterial> 指定将对模型应用画笔，就像模型的图面是硬或亮，能够反映突出显示。 您可以通过指定的值设置到的纹理将建议此反射质量或"增加亮点，"的程度<xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A>属性。  
  
-   <xref:System.Windows.Media.Media3D.EmissiveMaterial> 使用此选项可以指定将应用纹理，就像模型所发出的相等的画笔的颜色的光一样。 这不会使模型成为光源；但是它参与阴影设置的方式将不同于用 DiffuseMaterial 或 SpecularMaterial 设置纹理时的情况。  
  
 为了提高性能的背面<xref:System.Windows.Media.Media3D.GeometryModel3D>（这些不视图，因为它们是相机的模型的另一侧） 剔除从场景。  若要指定<xref:System.Windows.Media.Media3D.Material>若要将应用于背面的类似这样一个平面的模型，将设置模型的<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>属性。  
  
 为了实现某些图面质量（如发光或发射效果），用户可能希望向模型连续应用几个不同的画笔。 你可以应用并重复多个材料使用通过<xref:System.Windows.Media.Media3D.MaterialGroup>类。 MaterialGroup 的子级在多个呈现过程中按照从头到尾的顺序来应用。  
  
 下面的代码示例演示如何将纯色和绘图以画笔形式应用于 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 模型。  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  
 [!code-xaml[3doverview#3DOverview3DN9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
  
 [!code-csharp[3doverview#3DOverview3DN8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
 [!code-vb[3doverview#3DOverview3DN8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>   
## <a name="illuminating-the-scene"></a>照亮场景  
 与实际的光一样，[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 图形中的光能够使图面可见。 更确切地说，光确定了场景的哪个部分将包括在投影中。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的光对象创建了各种光和阴影效果，并且按照各种实际光的行为进行了建模。 必须至少在场景中包括一个光，否则模型将不可见。  
  
 下面的光派生自的基类<xref:System.Windows.Media.Media3D.Light>:  
  
-   <xref:System.Windows.Media.Media3D.AmbientLight>： 提供环境的照明，照亮统一而不考虑其位置或方向的所有对象。  
  
-   <xref:System.Windows.Media.Media3D.DirectionalLight>： 像远距离的光源那样照亮。  方向性光源具有<xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A>指定为 Vector3D，但没有指定的位置。  
  
-   <xref:System.Windows.Media.Media3D.PointLight>： 像附近光源那样照亮。 PointLights 具有一个位置并从该位置投射光。 场景中的对象根据对象相对于光源的位置和距离被照亮。 <xref:System.Windows.Media.Media3D.PointLightBase> 公开<xref:System.Windows.Media.Media3D.PointLightBase.Range%2A>属性，确定超过该模型将不会由光源照亮的距离。 PointLight 还公开了多个衰减属性，这些属性确定光源的亮度如何随距离的增加而减小。 可以为光源的衰减指定恒定、线性或二次内插算法。  
  
-   <xref:System.Windows.Media.Media3D.SpotLight>： 继承自<xref:System.Windows.Media.Media3D.PointLight>。 Spotlights 的照亮方式与 PointLight 类似，但是它既具有位置又具有方向。 这些项目设置的锥形区域采用浅色<xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A>和<xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A>以度为单位指定的属性。  
  
 灯都<xref:System.Windows.Media.Media3D.Model3D>对象，因此你可以转换和浅色属性，包括位置、 颜色、 方向和范围进行动画处理。  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>   
## <a name="transforming-models"></a>转换模型  
 创建模型时，它们在场景中有特定的位置。 为了在场景中移动、旋转这些模型或者更改这些模型的大小而更改用来定义模型本身的顶点不切实际。  而正如在 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 中一样，可以向模型应用转换。  
  
 每个模型对象具有<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>属性与其可以移动、 重定向，或调整大小的模型。  应用转换时，实际上是按照由转换功能指定的矢量或值（以适用者为准）来偏移模型的所有点。 换言之，用户已经转换了在其中定义模型的坐标空间（“模型空间”），但是尚未更改在整个场景的坐标系（“全局空间”）中构成模型几何形状的值。  
  
 有关转换模型的详细信息，请参阅 [3D 转换概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)。  
  
<a name="animations"></a>   
## <a name="animating-models"></a>对模型进行动画处理  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 实现与 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 图形参与同一个计时和动画系统。 换言之，若要对 3D 场景进行动画处理，需要对其模型的属性进行动画处理。 可以直接对基元的属性进行动画处理，但是通常很容易对用来更改模型位置或外观的转换进行动画处理。 由于转换可以应用到<xref:System.Windows.Media.Media3D.Model3DGroup>对象及其各个模型，可以将一组动画应用于的 Model3DGroup 子和另一组到一组子对象的动画。 还可以通过对场景的照明属性进行动画处理来实现各种视觉效果。 最后，可以选择通过对照相机的位置或视野进行动画处理来对投影本身进行动画处理。 有关 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 计时和动画系统的背景信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)、[演示图板概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)和 [Freezable 对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)主题。  
  
 若要对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的对象进行动画处理，可以创建时间线、定义动画（实际上是随着时间的推移而更改某个属性值）并指定要向其应用动画的属性。 因为中的所有对象[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]场景是子级<xref:System.Windows.Controls.Viewport3D>，针对你想要应用于场景任何的动画的属性是 Viewport3D 的属性的属性。  
  
 假设你希望实现模型看上去是在原地摇摆的效果。 你可以选择要应用<xref:System.Windows.Media.Media3D.RotateTransform3D>为模式，并进行动画处理到另一个向量从其旋转的轴。 下面的代码示例演示如何将 Vector3DAnimation 应用于该转换的 Rotation3D 的 Axis 属性，并假设 RotateTransform3D 是应用于具有 TransformGroup 的模型的几个转换之一。  
  
 [!code-csharp[3doverview#3DOverview3DN1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>   
## <a name="add-3-d-content-to-the-window"></a>向窗口中添加 3D 内容  
 若要呈现的场景，添加模型和到灯<xref:System.Windows.Media.Media3D.Model3DGroup>，然后设置<xref:System.Windows.Media.Media3D.Model3DGroup>作为<xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A>的<xref:System.Windows.Media.Media3D.ModelVisual3D>。 添加<xref:System.Windows.Media.Media3D.ModelVisual3D>到<xref:System.Windows.Controls.Viewport3D.Children%2A>集合<xref:System.Windows.Controls.Viewport3D>。 添加到的摄像头<xref:System.Windows.Controls.Viewport3D>通过设置其<xref:System.Windows.Controls.Viewport3D.Camera%2A>属性。  
  
 最后，添加<xref:System.Windows.Controls.Viewport3D>到窗口。 当<xref:System.Windows.Controls.Viewport3D>画布，如布局元素的内容通过设置指定 Viewport3D 的大小是包含其<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>属性 (继承自<xref:System.Windows.FrameworkElement>)。  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Viewport3D>  
 <xref:System.Windows.Media.Media3D.PerspectiveCamera>  
 <xref:System.Windows.Media.Media3D.DirectionalLight>  
 <xref:System.Windows.Media.Media3D.Material>  
 [3D 转换概述](../../../../docs/framework/wpf/graphics-multimedia/3-d-transformations-overview.md)  
 [最大限度地提升 WPF 3D 性能](../../../../docs/framework/wpf/graphics-multimedia/maximize-wpf-3d-performance.md)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-how-to-topics.md)  
 [WPF 中的形状和基本绘图概述](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
