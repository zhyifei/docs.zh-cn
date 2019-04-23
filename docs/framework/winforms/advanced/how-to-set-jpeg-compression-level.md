---
title: 如何：设置 JPEG 压缩级别
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], changing encoder parameters
- JPEG images [Windows Forms], setting quality level
ms.assetid: 4b9a74e3-9504-43c1-9f28-ace651d0772e
ms.openlocfilehash: de9dce1b3c15070fda268c430ce5da641efef6f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130671"
---
# <a name="how-to-set-jpeg-compression-level"></a><span data-ttu-id="30c38-102">如何：设置 JPEG 压缩级别</span><span class="sxs-lookup"><span data-stu-id="30c38-102">How to: Set JPEG Compression Level</span></span>
<span data-ttu-id="30c38-103">在将图像保存到磁盘中时，可能需要修改图像的参数，以最大限度地减小文件的大小或提高其质量。</span><span class="sxs-lookup"><span data-stu-id="30c38-103">You may want to modify the parameters of an image when you save the image to disk to minimize the file size or improve its quality.</span></span> <span data-ttu-id="30c38-104">可以通过修改 JPEG 图像的压缩级别来调整其质量。</span><span class="sxs-lookup"><span data-stu-id="30c38-104">You can adjust the quality of a JPEG image by modifying its compression level.</span></span> <span data-ttu-id="30c38-105">若要指定压缩级别保存 JPEG 图像时，必须创建<xref:System.Drawing.Imaging.EncoderParameters>对象，并将其传递给<xref:System.Drawing.Image.Save%2A>方法的<xref:System.Drawing.Image>类。</span><span class="sxs-lookup"><span data-stu-id="30c38-105">To specify the compression level when you save a JPEG image, you must create an <xref:System.Drawing.Imaging.EncoderParameters> object and pass it to the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="30c38-106">初始化<xref:System.Drawing.Imaging.EncoderParameters>对象，使它具有一个数组，其中包含一个<xref:System.Drawing.Imaging.EncoderParameter>。</span><span class="sxs-lookup"><span data-stu-id="30c38-106">Initialize the <xref:System.Drawing.Imaging.EncoderParameters> object so that it has an array that consists of one <xref:System.Drawing.Imaging.EncoderParameter>.</span></span> <span data-ttu-id="30c38-107">当您创建<xref:System.Drawing.Imaging.EncoderParameter>，指定<xref:System.Drawing.Imaging.Encoder.Quality>编码器和所需的压缩级别。</span><span class="sxs-lookup"><span data-stu-id="30c38-107">When you create the <xref:System.Drawing.Imaging.EncoderParameter>, specify the <xref:System.Drawing.Imaging.Encoder.Quality> encoder, and the desired compression level.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30c38-108">示例</span><span class="sxs-lookup"><span data-stu-id="30c38-108">Example</span></span>  
 <span data-ttu-id="30c38-109">下面的示例代码创建<xref:System.Drawing.Imaging.EncoderParameter>对象，并将保存三个 JPEG 图像。</span><span class="sxs-lookup"><span data-stu-id="30c38-109">The following example code creates an <xref:System.Drawing.Imaging.EncoderParameter> object and saves three JPEG images.</span></span> <span data-ttu-id="30c38-110">通过修改与不同质量级别保存每个 JPEG 图像`long`值传递给<xref:System.Drawing.Imaging.EncoderParameter>构造函数。</span><span class="sxs-lookup"><span data-stu-id="30c38-110">Each JPEG image is saved with a different quality level, by modifying the `long` value passed to the <xref:System.Drawing.Imaging.EncoderParameter> constructor.</span></span> <span data-ttu-id="30c38-111">质量级别 0 对应于最大压缩，而质量级别 100 对应于最小压缩。</span><span class="sxs-lookup"><span data-stu-id="30c38-111">A quality level of 0 corresponds to the greatest compression, and a quality level of 100 corresponds to the least compression.</span></span>  
  
```csharp  
private void VaryQualityLevel()  
    {  
        // Get a bitmap. The using statement ensures objects  
        // are automatically disposed from memory after use.  
        using (Bitmap bmp1 = new Bitmap(@"C:\TestPhoto.jpg"))  
        {  
            ImageCodecInfo jpgEncoder = GetEncoder(ImageFormat.Jpeg);  
  
            // Create an Encoder object based on the GUID  
            // for the Quality parameter category.  
            System.Drawing.Imaging.Encoder myEncoder =  
                System.Drawing.Imaging.Encoder.Quality;  
  
            // Create an EncoderParameters object.  
            // An EncoderParameters object has an array of EncoderParameter  
            // objects. In this case, there is only one  
            // EncoderParameter object in the array.  
            EncoderParameters myEncoderParameters = new EncoderParameters(1);  
  
            EncoderParameter myEncoderParameter = new EncoderParameter(myEncoder, 50L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"c:\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters);  
  
            myEncoderParameter = new EncoderParameter(myEncoder, 100L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters);  
  
            // Save the bitmap as a JPG file with zero quality level compression.  
            myEncoderParameter = new EncoderParameter(myEncoder, 0L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters);  
        }  
    }  
```  
  
```vb  
Private Sub VaryQualityLevel()  
    ' Get a bitmap. The Using statement ensures objects  
    ' are automatically disposed from memory after use.  
    Using bmp1 As New Bitmap("C:\test\TestPhoto.jpg")  
        Dim jpgEncoder As ImageCodecInfo = GetEncoder(ImageFormat.Jpeg)  
  
        ' Create an Encoder object based on the GUID  
        ' for the Quality parameter category.  
        Dim myEncoder As System.Drawing.Imaging.Encoder = System.Drawing.Imaging.Encoder.Quality  
  
        ' Create an EncoderParameters object.  
        ' An EncoderParameters object has an array of EncoderParameter  
        ' objects. In this case, there is only one  
        ' EncoderParameter object in the array.  
        Dim myEncoderParameters As New EncoderParameters(1)  
  
        Dim myEncoderParameter As New EncoderParameter(myEncoder, 50L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("c:\test\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters)  
  
        myEncoderParameter = New EncoderParameter(myEncoder, 100L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters)  
  
        ' Save the bitmap as a JPG file with zero quality level compression.  
        myEncoderParameter = New EncoderParameter(myEncoder, 0L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters)  
    End Using  
End Sub  
```  
  
```csharp  
private ImageCodecInfo GetEncoder(ImageFormat format)  
{  
    ImageCodecInfo[] codecs = ImageCodecInfo.GetImageDecoders();  
    foreach (ImageCodecInfo codec in codecs)  
    {  
        if (codec.FormatID == format.Guid)  
        {  
            return codec;  
        }  
    }  
    return null;  
}  
```  
  
```vb  
Private Function GetEncoder(ByVal format As ImageFormat) As ImageCodecInfo  
  
    Dim codecs As ImageCodecInfo() = ImageCodecInfo.GetImageDecoders()  
    Dim codec As ImageCodecInfo  
    For Each codec In codecs  
        If codec.FormatID = format.Guid Then  
            Return codec  
        End If  
    Next codec  
    Return Nothing  
  
End Function  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="30c38-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="30c38-112">Compiling the Code</span></span>  
 <span data-ttu-id="30c38-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="30c38-113">This example requires:</span></span>  
  
-   <span data-ttu-id="30c38-114">Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="30c38-114">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="30c38-115">一个<xref:System.Windows.Forms.PaintEventArgs>，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="30c38-115">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
-   <span data-ttu-id="30c38-116">一个位于 **c:\\** 位置的名为 `TestPhoto.jpg` 的图像文件。</span><span class="sxs-lookup"><span data-stu-id="30c38-116">An image file that is named `TestPhoto.jpg` and located at **c:\\**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c38-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="30c38-117">See also</span></span>

- [<span data-ttu-id="30c38-118">如何：确定编码器支持的参数</span><span class="sxs-lookup"><span data-stu-id="30c38-118">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)
- [<span data-ttu-id="30c38-119">位图类型</span><span class="sxs-lookup"><span data-stu-id="30c38-119">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="30c38-120">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="30c38-120">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
