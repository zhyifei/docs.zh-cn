---
title: 3D 图形概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D graphics [WPF]
- graphics [WPF], 3D
ms.assetid: 67f31ed4-e36b-4b02-9889-dcce245d7afc
ms.openlocfilehash: b8a3876030c533dd37eca0b00ebd50bccf309e53
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112383"
---
# <a name="3d-graphics-overview"></a>3D 图形概述
<a name="introduction"></a>中的[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]3D 功能使开发人员能够在标记和程序代码中绘制、转换和设置 3D 图形的动画。 开发人员可以组合 2D 和 3D 图形以创建丰富的控件、提供复杂的数据插图或增强应用程序界面的用户体验。 3D[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]支持不是旨在提供功能齐全的游戏开发平台。 本主题概述了图形系统中的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]3D 功能。  

<a name="threed_in_2d"></a>
## <a name="3d-in-a-2d-container"></a>2D 容器中的 3D  
 中的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]3D 图形内容封装在可以参与二<xref:System.Windows.Controls.Viewport3D>维元素结构的元素中。 图形系统像<xref:System.Windows.Controls.Viewport3D>中的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]许多其他元素一样被视为二维视觉元素。 <xref:System.Windows.Controls.Viewport3D>作为窗口（视口）进入三维场景。 更准确地说，它是投影 3D 场景的曲面。  
  
 在传统的 2D 应用程序中，<xref:System.Windows.Controls.Viewport3D>使用另一个容器元素（如网格或画布）时，将一样使用。  尽管可以在同一<xref:System.Windows.Controls.Viewport3D>场景图中与其他 2D 图形对象一起使用，但不能在 中<xref:System.Windows.Controls.Viewport3D>渗透 2D 和 3D 对象。  本主题将重点介绍如何在 中<xref:System.Windows.Controls.Viewport3D>绘制 3D 图形。  
  
<a name="coord_space"></a>
## <a name="3d-coordinate-space"></a>3D 坐标空间  
 2D 图形的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]坐标系定位渲染区域左上角的原点（通常是屏幕）。 在 2D 系统中，正 x 轴值向右，正 y 轴值向下。  但是，在 3D 坐标系中，原点位于渲染区域的中心，正 x 轴值向右移动，但正 y 轴值则朝上，正 z 轴值从原点向外移动，对查看器。  
  
 ![坐标系](./media/coordsystem-1.png "库德系统-1")  
传统的 2D 和 3D 坐标系表示  
  
 这些轴定义的空间是 中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]3D 对象的固定参考框架。 当在该空间中生成模型并创建光源和照相机以查看这些模型时，一定要在向每个模型应用转换时，将固定参考框架或“全局空间”与为该模型创建的局部参考框架区分开。 另请记住，根据光源和照相机设置，全局空间中的对象可能会看上去完全不同或者根本不可见，但是照相机的位置不会改变对象在全局空间中的位置。  
  
<a name="cameras"></a>
## <a name="cameras-and-projections"></a>照相机和投影  
 使用 2D 工作的开发人员习惯于在二维屏幕上定位绘图基元。 创建 3D 场景时，请务必记住，您确实在创建 3D 对象的 2D 表示形式。 由于 3D 场景的外观因旁观者的观点而异，因此必须指定该视图。 该<xref:System.Windows.Media.Media3D.Camera>类允许您为 3D 场景指定此视图。  
  
 了解 3D 场景在 2D 表面上的表示方式的另一种方法是将场景描述为投影到查看表面上。 <xref:System.Windows.Media.Media3D.ProjectionCamera>允许您指定不同的投影及其属性，以更改旁观者看到 3D 模型的方式。 指定<xref:System.Windows.Media.Media3D.PerspectiveCamera>预测使场景缩短。  换句话说，提供<xref:System.Windows.Media.Media3D.PerspectiveCamera>消失点透视。  可以指定照相机在场景坐标系中的位置、照相机的方向和视野以及用来定义场景中“向上”方向的矢量。 下图说明了<xref:System.Windows.Media.Media3D.PerspectiveCamera>的投影。  
  
 限制<xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>摄像机<xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A>投影范围<xref:System.Windows.Media.Media3D.ProjectionCamera>的 和 属性。 由于照相机可以位于场景中的任何位置，因此照相机实际上可能会位于模型内部或者紧靠模型，这使正确区分对象变得很困难。  <xref:System.Windows.Media.Media3D.ProjectionCamera.NearPlaneDistance%2A>允许您指定与摄像机的最小距离，超出该距离，这样对象就不会绘制。  相反，<xref:System.Windows.Media.Media3D.ProjectionCamera.FarPlaneDistance%2A>允许您指定与摄像机的距离，超出该距离，这样对象就不会绘制，这可确保距离太远而无法识别的对象不会包含在场景中。  
  
 ![照相机设置](./media/coordsystem-6.png "库德系统-6")  
照相机位置  
  
 <xref:System.Windows.Media.Media3D.OrthographicCamera>指定 3D 模型到 2D 视觉表面的正交投影。 与其他照相机一样，它指定位置、观察方向和“向上”方向。 但是<xref:System.Windows.Media.Media3D.PerspectiveCamera>，<xref:System.Windows.Media.Media3D.OrthographicCamera>与 描述不包括透视预缩短的投影不同。 换句话说，<xref:System.Windows.Media.Media3D.OrthographicCamera>描述一个视图框的两侧是平行的，而不是一个侧面在摄像机的点中相遇的。 下图显示了使用<xref:System.Windows.Media.Media3D.PerspectiveCamera>和<xref:System.Windows.Media.Media3D.OrthographicCamera>查看的相同模型。  
  
 ![正投影和透视投影](./media/camera-projections4.png "Camera_projections4")  
透视投影和正投影  
  
 下面的代码演示一些典型的照相机设置。  
  
 [!code-csharp[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexampleinline1)]
 [!code-vb[3dgallery_procedural_snip#Basic3DShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexampleinline1)]  
  
<a name="models_meshes"></a>
## <a name="model-and-mesh-primitives"></a>模型和网格基元  
  
 <xref:System.Windows.Media.Media3D.Model3D>是表示泛型 3D 对象的抽象基类。 要构建 3D 场景，需要查看一些对象，构成场景图的对象派生自<xref:System.Windows.Media.Media3D.Model3D>。 目前，支持[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用 对几何体<xref:System.Windows.Media.Media3D.GeometryModel3D>进行建模。 此<xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>模型的属性采用网格基元。  
  
 若要生成模型，请首先生成一个基元或网格。 3D 基元是单个 3D 实体中的顶点的集合。 大多数 3D 系统提供以最简单的闭合图建模的原始元：由三个顶点定义的三角形。  由于三角形的三个点在一个平面上，因此可以继续添加三角形，以便对网格这样较为复杂的形状建模。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 3D 系统当前提供类<xref:System.Windows.Media.Media3D.MeshGeometry3D>，允许您指定任何几何体;它当前不支持预定义的 3D 基元，如球体和立方形式。 通过指定三<xref:System.Windows.Media.Media3D.MeshGeometry3D>角形顶点列表作为其<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>属性，开始创建 。 每个顶点指定为<xref:System.Windows.Media.Media3D.Point3D>。  （在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中，将此属性指定为以三为单位的表示每个顶点的坐标的数字的列表。根据其几何体，网格可能由许多三角形组成，其中一些三角形共享相同的角（顶点）。 若要正确绘制网格，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 需要有关哪些顶点由哪些三角形共用的信息。 通过指定具有 属性的三角形索引列表来<xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>提供此信息。 此列表指定<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>列表中指定的点将确定三角形的顺序。  
  
 [!code-xaml[basic3d#Basic3DXAML3DN3](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn3)]  
  
 在前面的示例中，<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>列表指定八个顶点来定义立方体形状的网格。 属性<xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>指定十二组三个索引的列表。  列表中的每个数字都引用列表中的<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>偏移量。  例如，<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>列表指定的前三个顶点是 （1，1，0）、（0，1，0）和 （0，0，0）。 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>列表指定的前三个索引是 0、2 和 1，它们对应于<xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>列表中的第一点、第三个点和第二个点。 因此，构成立方体模型的第一个三角形将按照从 (1,1,0) 到 (0,1,0) 再到 (0,0,0) 的顺序组合而成，其余的十一个三角形将按照类似方式确定。  
  
 可以通过指定 和<xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A><xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>属性的值来继续定义模型。  为了呈现模型的图面，图形系统需要有关曲面在任何给定三角形上的朝向信息。 图形系统使用此信息来针对该模型进行照明计算：正对光源的图面比偏离光源的图面显得更亮。 尽管 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 可以使用位置坐标来确定默认的法矢量，但是你还可以指定不同的法矢量来近似计算曲面的外观。  
  
 属性<xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>指定一个<xref:System.Windows.Point>s 集合，告诉图形系统如何映射确定纹理如何绘制到网格顶点的坐标。 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A>指定为介于零和 1 之间的值，包括。  与<xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A>属性一样，图形系统可以计算默认纹理坐标，但您可以选择设置不同的纹理坐标，以控制包含重复图案的一部分的纹理的映射。例如。 有关纹理坐标的详细信息，可在后续主题或 Managed Direct3D SDK 中找到。  
  
 下面的示例演示如何在过程代码中创建立方体模型的一面。 请注意，可以将整个立方体绘制为单个 GeometryModel3D；此示例将该立方体面绘制为一个不同的模型，以便在以后向每个面应用不同的纹理。  
  
 [!code-csharp[3doverview#3DOverview3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn6)]
 [!code-vb[3doverview#3DOverview3DN6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn6)]  
  
 [!code-csharp[3doverview#3DOverview3DN7](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn7)]
 [!code-vb[3doverview#3DOverview3DN7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn7)]  
  
<a name="materials"></a>'
## <a name="applying-materials-to-the-model"></a>向模型应用材料  
  
 为了使网格看上去像三维对象，必须向其应用纹理，以便覆盖由顶点和三角形定义的图面，从而使其可以由照相机照明和投影。 在 2D 中，<xref:System.Windows.Media.Brush>使用 类将颜色、图案、渐变或其他视觉内容应用于屏幕区域。  但是，3D 对象的外观是照明模型的函数，而不仅仅是应用于它们的颜色或图案的函数。 实际对象的图面质量不同，它们反射光的方式也会有所不同：光亮的图面与粗糙或不光滑的图面看上去不同，某些对象似乎可以吸收光，而某些对象似乎能够发光。 您可以将所有相同的画笔应用于可应用于 2D 对象的 3D 对象，但不能直接应用它们。  
  
 要定义模型曲面的特征，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]请使用<xref:System.Windows.Media.Media3D.Material>抽象类。 Material 的具体子类用来确定模型图面的某些外观特征，每个子类还提供一个可以向其传递 SolidColorBrush、TileBrush 或 VisualBrush 的 Brush 属性。  
  
- <xref:System.Windows.Media.Media3D.DiffuseMaterial>指定画笔将应用于模型，就像模型被漫射一样。 使用漫反射材质最类似于直接在 2D 模型上使用画笔;模型表面不会反射光线，如光泽。  
  
- <xref:System.Windows.Media.Media3D.SpecularMaterial>指定画笔将应用于模型，就像模型的表面是坚硬的或有光泽的，能够反射高光。 您可以通过指定<xref:System.Windows.Media.Media3D.SpecularMaterial.SpecularPower%2A>属性的值来设置纹理将建议此反射质量或"光泽"的程度。  
  
- <xref:System.Windows.Media.Media3D.EmissiveMaterial>允许您指定纹理将应用，就像模型发出的光等于画笔的颜色一样。 这不会使模型成为光源；但是它参与阴影设置的方式将不同于用 DiffuseMaterial 或 SpecularMaterial 设置纹理时的情况。  
  
 为了更好的性能，从场景中剔除<xref:System.Windows.Media.Media3D.GeometryModel3D>a 的背面（那些由于位于相机模型的另一侧而偏离视图的面）。  要指定<xref:System.Windows.Media.Media3D.Material>要应用于模型的背面（如平面），请设置模型的属性<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>。  
  
 为了实现某些图面质量（如发光或发射效果），用户可能希望向模型连续应用几个不同的画笔。 您可以使用<xref:System.Windows.Media.Media3D.MaterialGroup>类应用和重用多个材质。 MaterialGroup 的子级在多个呈现过程中按照从头到尾的顺序来应用。  
  
 以下代码示例演示如何将纯色和绘图作为画笔应用于 3D 模型。  
  
 [!code-xaml[basic3d#Basic3DXAML3DN5](~/samples/snippets/xaml/VS_Snippets_Wpf/Basic3D/XAML/Window1.xaml#basic3dxaml3dn5)]  
  ' [!code-xaml[3doverview#3DOverview3DN9](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/app.xaml#3doverview3dn9)]  
 ' [!code-csharp[3doverview#3DOverview3DN8](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn8)]
  [!code-vb[3doverview#3DOverview3DN8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn8)]  
  
<a name="lights"></a>
## <a name="illuminating-the-scene"></a>照亮场景  
 3D 图形中的灯光可以像灯光在现实世界中一起做什么：它们使曲面可见。 更确切地说，光确定了场景的哪个部分将包括在投影中。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的光对象创建了各种光和阴影效果，并且按照各种实际光的行为进行了建模。 必须至少在场景中包括一个光，否则模型将不可见。  
  
 以下灯光派生自基类<xref:System.Windows.Media.Media3D.Light>：  
  
- <xref:System.Windows.Media.Media3D.AmbientLight>： 提供环境照明，无论所有对象的位置或方向如何，都能均匀地照亮所有对象。  
  
- <xref:System.Windows.Media.Media3D.DirectionalLight>：像远处的光源一样发光。  方向灯光指定<xref:System.Windows.Media.Media3D.DirectionalLight.Direction%2A>为 Vector3D，但没有指定的位置。  
  
- <xref:System.Windows.Media.Media3D.PointLight>：像附近的光源一样发光。 PointLights 具有一个位置并从该位置投射光。 场景中的对象根据对象相对于光源的位置和距离被照亮。 <xref:System.Windows.Media.Media3D.PointLightBase>公开属性<xref:System.Windows.Media.Media3D.PointLightBase.Range%2A>，该属性确定模型不会被光线照亮的距离。 PointLight 还公开了多个衰减属性，这些属性确定光源的亮度如何随距离的增加而减小。 可以为光源的衰减指定恒定、线性或二次内插算法。  
  
- <xref:System.Windows.Media.Media3D.SpotLight>：从<xref:System.Windows.Media.Media3D.PointLight>继承。 Spotlights 的照亮方式与 PointLight 类似，但是它既具有位置又具有方向。 它们在由<xref:System.Windows.Media.Media3D.SpotLight.InnerConeAngle%2A>和<xref:System.Windows.Media.Media3D.SpotLight.OuterConeAngle%2A>属性设置的锥形区域中投射光线，以度为单位指定。  
  
 灯光是<xref:System.Windows.Media.Media3D.Model3D>对象，因此您可以变换和设置灯光属性的动画，包括位置、颜色、方向和范围。  
  
 [!code-xaml[hittest3d#HitTest3D3DN6](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml#hittest3d3dn6)]  
  
 [!code-csharp[basic3d#Basic3D3DN11](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn11)]
 [!code-vb[basic3d#Basic3D3DN11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn11)]  
  
 [!code-csharp[basic3d#Basic3D3DN12](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn12)]
 [!code-vb[basic3d#Basic3D3DN12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn12)]  
  
 [!code-csharp[basic3d#Basic3D3DN13](~/samples/snippets/csharp/VS_Snippets_Wpf/Basic3D/CSharp/Window1.xaml.cs#basic3d3dn13)]
 [!code-vb[basic3d#Basic3D3DN13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Basic3D/visualbasic/window1.xaml.vb#basic3d3dn13)]  
  
<a name="transforms"></a>
## <a name="transforming-models"></a>转换模型  
 创建模型时，它们在场景中有特定的位置。 为了在场景中移动、旋转这些模型或者更改这些模型的大小而更改用来定义模型本身的顶点不切实际。  相反，就像在 2D 中一样，您将变换应用于模型。  
  
 每个模型对象都有一<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>个属性，您可以使用该属性移动、重新定向或调整模型的大小。  应用转换时，实际上是按照由转换功能指定的矢量或值（以适用者为准）来偏移模型的所有点。 换言之，用户已经转换了在其中定义模型的坐标空间（“模型空间”），但是尚未更改在整个场景的坐标系（“全局空间”）中构成模型几何形状的值。  
  
 有关变换模型的详细信息，请参阅[3D 变换概述](3-d-transformations-overview.md)。  
  
<a name="animations"></a>
## <a name="animating-models"></a>对模型进行动画处理  
 3D[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]实现与 2D 图形参与相同的计时和动画系统。 换句话说，要为 3D 场景设置动画，为其模型的属性设置动画。 可以直接对基元的属性进行动画处理，但是通常很容易对用来更改模型位置或外观的转换进行动画处理。 由于转换可以应用于<xref:System.Windows.Media.Media3D.Model3DGroup>对象以及单个模型，因此可以将一组动画应用于 Model3DGroup 的子级动画，将另一组动画应用于一组子对象。 还可以通过对场景的照明属性进行动画处理来实现各种视觉效果。 最后，可以选择通过对照相机的位置或视野进行动画处理来对投影本身进行动画处理。 有关 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 计时和动画系统的背景信息，请参阅[动画概述](animation-overview.md)、[演示图板概述](storyboards-overview.md)和 [Freezable 对象概述](../advanced/freezable-objects-overview.md)主题。  
  
 若要对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的对象进行动画处理，可以创建时间线、定义动画（实际上是随着时间的推移而更改某个属性值）并指定要向其应用动画的属性。 由于 3D 场景中的所有对象都是 的<xref:System.Windows.Controls.Viewport3D>子对象，因此要应用于该场景的任何动画的目标属性都是 Viewport3D 属性的属性。  
  
 假设你希望实现模型看上去是在原地摇摆的效果。 您可以选择对模型应用 ，<xref:System.Windows.Media.Media3D.RotateTransform3D>并为其旋转轴从一个矢量到另一个矢量设置动画。 下面的代码示例演示如何将 Vector3DAnimation 应用于该转换的 Rotation3D 的 Axis 属性，并假设 RotateTransform3D 是应用于具有 TransformGroup 的模型的几个转换之一。  
  
 [!code-csharp[3doverview#3DOverview3DN1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn1)]
 [!code-vb[3doverview#3DOverview3DN1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn1)]  
  
 [!code-csharp[3doverview#3DOverview3DN3](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn3)]
 [!code-vb[3doverview#3DOverview3DN3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn3)]  
  
 [!code-csharp[3doverview#3DOverview3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn4)]
 [!code-vb[3doverview#3DOverview3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn4)]  
  
 [!code-csharp[3doverview#3DOverview3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/3DOverview/CSharp/Window1.xaml.cs#3doverview3dn5)]
 [!code-vb[3doverview#3DOverview3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DOverview/visualbasic/window1.xaml.vb#3doverview3dn5)]  
  
<a name="animations1"></a>
## <a name="add-3d-content-to-the-window"></a>将 3D 内容添加到窗口  
 要渲染场景，将模型和灯光添加到<xref:System.Windows.Media.Media3D.Model3DGroup>中，然后将<xref:System.Windows.Media.Media3D.Model3DGroup>设置为<xref:System.Windows.Media.Media3D.ModelVisual3D.Content%2A> <xref:System.Windows.Media.Media3D.ModelVisual3D>。 将<xref:System.Windows.Media.Media3D.ModelVisual3D>添加到<xref:System.Windows.Controls.Viewport3D.Children%2A>集合 中<xref:System.Windows.Controls.Viewport3D>。 通过设置其<xref:System.Windows.Controls.Viewport3D.Camera%2A>属性<xref:System.Windows.Controls.Viewport3D>将摄像机添加到 。  
  
 最后，将<xref:System.Windows.Controls.Viewport3D>添加到窗口中。 当<xref:System.Windows.Controls.Viewport3D>包含在 布局元素（如 Canvas）的内容时，通过设置其<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>属性（继承自<xref:System.Windows.FrameworkElement>） 来指定 Viewport3D 的大小。  
  
 [!code-xaml[hostingwpfusercontrolinwf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Viewport3D>
- <xref:System.Windows.Media.Media3D.PerspectiveCamera>
- <xref:System.Windows.Media.Media3D.DirectionalLight>
- <xref:System.Windows.Media.Media3D.Material>
- [3D 转换概述](3-d-transformations-overview.md)
- [最大程度地提高 WPF 3D 性能](maximize-wpf-3d-performance.md)
- [如何使用主题](3-d-graphics-how-to-topics.md)
- [WPF 中的形状和基本绘图概述](shapes-and-basic-drawing-in-wpf-overview.md)
- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
