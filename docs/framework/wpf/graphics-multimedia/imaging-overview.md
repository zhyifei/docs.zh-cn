---
title: 图像处理概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- metadata [WPF], images
- displaying images [WPF]
- Imaging API [WPF]
- image metadata [WPF]
- converting images [WPF]
- encoding image formats [WPF]
- format decoding for images [WPF]
- painting with images [WPF]
- stretching images [WPF]
- images [WPF], about imaging
- format encoding for images [WPF]
- cropping images [WPF]
- decoding image formats [WPF]
- rotating images [WPF]
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
ms.openlocfilehash: 3365c35e3e7b7fe5c0be48a65d7a14da0882c90e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186692"
---
# <a name="imaging-overview"></a>图像处理概述
本主题介绍了 Microsoft Windows 演示文稿基础映像组件。 WPF 成像使开发人员能够显示、转换和格式化图像。  

## <a name="wpf-imaging-component"></a>WPF 图像处理组件  
 WPF 映像在 Microsoft Windows 中提供了映像功能的重大增强。 映像功能（如显示位图或使用公共控件上的图像）以前依赖于 Microsoft Windows 图形设备接口 （GDI） 或 Microsoft Windows GDI+ 库。 这些 API 提供基线映像功能，但缺少支持编解码器扩展性和高保真图像支持等功能。 WPF 成像旨在克服 GDI 和 GDI+ 的缺点，并提供一组新的 API 来在应用程序中显示和使用图像。  
  
 有两种方法可以访问 WPF 映像 API、托管组件和非托管组件。 非托管组件提供以下功能。  
  
- 适用于新的或专用图像格式的扩展性模型。  
  
- 改进了本机图像格式的性能和安全性，包括位图 （BMP）、联合摄影专家组 （JPEG）、便携式网络图形 （PNG）、标记的图像文件格式 （TIFF）、微软 Windows 媒体照片、图形交换格式 （GIF）、和图标 （.ico）。  
  
- 高位深图像数据最多保留 8 位/通道（32 位/像素）。  
  
- 非破坏性图像缩放、剪切和旋转。  
  
- 简化的颜色管理。  
  
- 对文件内的专用元数据的支持。  
  
- 托管组件利用非托管基础结构提供图像与其他 WPF 功能（如 、动画和图形）[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]的无缝集成。 托管组件还受益于 Windows 演示基础 （WPF） 成像编解码器扩展模型，该模型允许在 WPF 应用程序中自动识别新的映像格式。  
  
 大多数托管的 WPF 映像 API 都驻<xref:System.Windows.Media.Imaging?displayProperty=nameWithType>留在命名空间中，但有几个重要类型，<xref:System.Windows.Media.ImageBrush>如<xref:System.Windows.Media.ImageDrawing>并驻留在<xref:System.Windows.Media?displayProperty=nameWithType>命名空间中<xref:System.Windows.Controls.Image>并驻留在<xref:System.Windows.Controls?displayProperty=nameWithType>命名空间中。  
  
 本主题提供有关托管组件的其他信息。 有关非托管 API 的详细信息，请参阅[非托管 WPF 映像组件](/windows/desktop/wic/-wic-lh)文档。  
  
<a name="_imageformats"></a>
## <a name="wpf-image-formats"></a>WPF 图像格式  

 编解码器用于对特定媒体格式进行解码或编码。 WPF 成像包括用于 BMP、JPEG、PNG、TIFF、Windows 媒体照片、GIF 和 ICON 图像格式的编解码器。 利用上述每个编解码器，应用程序可以对其各自的图像格式进行解码（ICON 除外）和编码。  
  
 <xref:System.Windows.Media.Imaging.BitmapSource>是图像解码和编码中的重要类。 它是 WPF 成像管道的基本构建基块，表示一组具有特定大小和分辨率的像素。 可以是<xref:System.Windows.Media.Imaging.BitmapSource>多个帧图像的单个帧，也可以是 对 执行转换的结果<xref:System.Windows.Media.Imaging.BitmapSource>。 它是 WPF 映像中使用的许多主类的父类，例如<xref:System.Windows.Media.Imaging.BitmapFrame>。  
  
 A<xref:System.Windows.Media.Imaging.BitmapFrame>用于存储图像格式的实际位图数据。 许多图像格式仅支持单个<xref:System.Windows.Media.Imaging.BitmapFrame>，尽管 GIF 和 TIFF 等格式支持每个图像的多个帧。 帧由解码器用作输入数据，并传递到编码器以创建图像文件。  
  
 下面的示例演示如何<xref:System.Windows.Media.Imaging.BitmapFrame>从 创建<xref:System.Windows.Media.Imaging.BitmapSource>，然后添加到 TIFF 映像。  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>图像格式解码  
 图像解码是指将某种图像格式转换为可以由系统使用的图像数据。 然后，此图像数据可以用于显示、处理或编码为其他格式。 根据图像格式选择解码器。 自动选择编解码器，除非指定了特定解码器。 [在 WPF 中显示图像](#_displayingimages)一节中的示例演示了自动解码。 使用非托管 WPF 映像接口开发的自定义格式解码器，并在系统中注册，可自动参与解码器选择。 这允许自定义格式自动显示在 WPF 应用程序中。  
  
 下面的示例演示了使用位图解码器解码 BMP 格式图像。  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>图像格式编码  
 图像编码是指将图像数据转换为特定的图像格式。 然后，已编码的图像数据可以用于创建新的图像文件。 WPF 成像为上述每种图像格式提供编码器。  
  
 以下示例演示使用编码器保存一个新创建的位图图像。  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>
## <a name="displaying-images-in-wpf"></a>在 WPF 中显示图像  
 有几种方法可以在 Windows 演示文稿基础 （WPF） 应用程序中显示图像。 图像可以使用<xref:System.Windows.Controls.Image>控件显示，使用 在视觉对象上绘制<xref:System.Windows.Media.ImageBrush>，或使用 进行绘制。 <xref:System.Windows.Media.ImageDrawing>  
  
### <a name="using-the-image-control"></a>使用 Image 控件  
 <xref:System.Windows.Controls.Image>是框架元素和在应用程序中显示图像的主要方式。 在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<xref:System.Windows.Controls.Image>中，可通过两种方式使用;属性语法或属性语法。 以下示例演示如何使用特性语法或属性标记语法来呈现宽度为 200 像素的图像。 有关特性语法和属性语法的详细信息，请参阅[依赖属性概述](../advanced/dependency-properties-overview.md)。  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 许多示例使用<xref:System.Windows.Media.Imaging.BitmapImage>对象来引用图像文件。 <xref:System.Windows.Media.Imaging.BitmapImage>是专为加载<xref:System.Windows.Media.Imaging.BitmapSource>而[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]优化<xref:System.Windows.Controls.Image.Source%2A>的专用函数，是作为<xref:System.Windows.Controls.Image>控件显示图像的简便方法。  
  
 以下示例演示如何使用代码呈现宽度为 200 像素的图像。  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage>实现接口<xref:System.ComponentModel.ISupportInitialize>以优化多个属性的初始化。 只能在对象初始化过程中进行属性更改。 调用<xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A>以发出初始化已经开始的信号，并<xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A>发出初始化已完成的信号。 初始化后，将忽略所做的属性更改。  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>旋转、转换和剪切图像  
 WPF 使用户能够<xref:System.Windows.Media.Imaging.BitmapImage>通过使用 属性或使用 其他<xref:System.Windows.Media.Imaging.BitmapSource>对象（如<xref:System.Windows.Media.Imaging.CroppedBitmap>或<xref:System.Windows.Media.Imaging.FormatConvertedBitmap>） 转换图像。 上述图像转换可以缩放或旋转图像、更改图像的像素格式或剪切图像。  
  
 使用<xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A>的属性执行图像旋转<xref:System.Windows.Media.Imaging.BitmapImage>。 只能以 90 度为增量进行旋转。 在以下示例中，图像旋转了 90 度。  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 使用 将图像转换为其他像素格式（如灰度）后，将使用<xref:System.Windows.Media.Imaging.FormatConvertedBitmap>。 在以下示例中，图像将转换为<xref:System.Windows.Media.PixelFormats.Gray4%2A>。  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 要裁剪图像，<xref:System.Windows.UIElement.Clip%2A>可以使用 或<xref:System.Windows.Controls.Image><xref:System.Windows.Media.Imaging.CroppedBitmap>可以使用 属性。 通常，如果您只想显示图像的一部分，<xref:System.Windows.UIElement.Clip%2A>则应使用。 如果需要对裁剪的图像进行编码和保存，则应使用 。 <xref:System.Windows.Media.Imaging.CroppedBitmap> 在下面的示例中，使用 Clip 属性使用<xref:System.Windows.Media.EllipseGeometry>裁剪图像。  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>拉伸图像  
 属性<xref:System.Windows.Controls.Image.Stretch%2A>控制图像拉伸以填充其容器的方式。 属性<xref:System.Windows.Controls.Image.Stretch%2A>接受以下值，由<xref:System.Windows.Media.Stretch>枚举定义：  
  
- <xref:System.Windows.Media.Stretch.None>： 图像不会拉伸以填充输出区域。 如果图像比输出区域大，将图像绘制到输出区域，剪裁掉无法容纳的内容。  
  
- <xref:System.Windows.Media.Stretch.Fill>： 缩放图像以适合输出区域。 由于图像的高度和宽度独立进行缩放，因此图像的原始纵横比可能不会保留。 也就是说，为了完全填充输出容器，图像可能会扭曲。  
  
- <xref:System.Windows.Media.Stretch.Uniform>： 缩放图像，使其完全适合输出区域。 图像的纵横比会保留。  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>： 缩放图像，使其完全填充输出区域，同时保持图像的原始纵横比。  
  
 下面的示例将每个可用的<xref:System.Windows.Media.Stretch>枚举应用于 。 <xref:System.Windows.Controls.Image>  
  
 下图显示了示例中的输出，并演示了应用于图像时的不同<xref:System.Windows.Controls.Image.Stretch%2A>设置的影响。  
  
 ![不同的 TileBrush 拉伸设置](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
不同的拉伸设置  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>使用图像进行绘制  
 图像也可以通过使用 进行绘制显示在应用程序中<xref:System.Windows.Media.Brush>。 借助画笔，可以利用任意内容（从简单的纯色到复杂的图案和图像集）绘制 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 对象。 要使用图像进行绘制，请使用<xref:System.Windows.Media.ImageBrush>。 是<xref:System.Windows.Media.ImageBrush>将其内容定义为<xref:System.Windows.Media.TileBrush>位图图像的类型。 显示<xref:System.Windows.Media.ImageBrush>由其<xref:System.Windows.Media.ImageBrush.ImageSource%2A>属性指定的单个图像。 可以控制图像的拉伸、对齐和平铺方式，从而防止失真并生成图案和其他效果。 下图显示了可以使用 可以实现的一<xref:System.Windows.Media.ImageBrush>些效果。  
  
 ![ImageBrush 输出示例](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
图像画笔可以填充形状、控件、文本等  
  
 下面的示例演示如何使用 图像绘制按钮的背景<xref:System.Windows.Media.ImageBrush>。  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 有关<xref:System.Windows.Media.ImageBrush>图像和绘制图像的其他信息，请参阅[使用图像、绘图和视觉对象进行绘画](painting-with-images-drawings-and-visuals.md)。  
  
<a name="_metadata"></a>
## <a name="image-metadata"></a>图像元数据  
 某些图像文件包含用于描述文件的内容或特征的元数据。 例如，大多数数数字相机创建的图像中包含用于捕获该图像的照相机品牌和型号的元数据。 每个图像格式处理元数据的方式不同，但 WPF 映像提供了存储和检索每个受支持图像格式的元数据的统一方法。  
  
 元数据的访问通过<xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A><xref:System.Windows.Media.Imaging.BitmapSource>对象的属性提供。 <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>返回包含<xref:System.Windows.Media.Imaging.BitmapMetadata>图像包含的所有元数据的对象。 此数据可以位于一个元数据架构中或位于不同架构的组合中。 WPF 成像支持以下图像元数据架构：可交换图像文件 （Exif）、tEXt （PNG 文本数据）、图像文件目录 （IFD）、国际新闻电信理事会 （IPTC） 和可扩展元数据平台 （XMP）。  
  
 为了简化<xref:System.Windows.Media.Imaging.BitmapMetadata>读取元数据的过程，提供了几个可以轻松访问的命名属性，如<xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>和<xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>。 <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A> 许多命名属性还可以用于编写元数据。 元数据查询读取器提供对读取元数据的其他支持。 该方法<xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A>用于通过提供字符串查询（如 *"/app1/exif/"）* 来检索元数据查询读取器。 在下面的示例中，<xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A>用于获取存储在 *"/文本/描述"* 位置的文本。  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 若要编写元数据，请使用元数据查询编写器。 <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>获取查询编写器并设置所需的值。 在下面的示例中，<xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>用于写入存储在 *"/文本/描述"* 位置的文本。  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>
## <a name="codec-extensibility"></a>编解码器扩展性  
 WPF成像的核心特征是新图像编解码器的可扩展性模型。 这些非托管接口使编解码器开发人员能够将编解码器与 WPF 集成，以便 WPF 应用程序可以自动使用新的映像格式。  
  
 有关扩展性 API 的示例，请参阅[Win32 示例编解码器](https://go.microsoft.com/fwlink/?LinkID=160052)。 此示例演示如何为自定义图像格式创建解码器和编码器。  
  
> [!NOTE]
> 编解码器必须进行数字签名，系统才能够识别它。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [2D 图形和图像处理](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Win32 示例编解码器](https://go.microsoft.com/fwlink/?LinkID=160052)
