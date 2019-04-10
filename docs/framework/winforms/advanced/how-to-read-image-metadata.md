---
title: 如何：读取图像元数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 0a53e9b9d23c03715bf3088a4ae8577a39527995
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173610"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="6c953-102">如何：读取图像元数据</span><span class="sxs-lookup"><span data-stu-id="6c953-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="6c953-103">某些图像文件包含元数据可以读取来确定映像的功能。</span><span class="sxs-lookup"><span data-stu-id="6c953-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="6c953-104">例如，数字照片中可能包含您可以读取以确定品牌和型号的照相机用于捕获映像的元数据。</span><span class="sxs-lookup"><span data-stu-id="6c953-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="6c953-105">使用[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，可以读取现有的元数据，并还可以将新的元数据写入图像文件。</span><span class="sxs-lookup"><span data-stu-id="6c953-105">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="6c953-106">存储元数据中的个别<xref:System.Drawing.Imaging.PropertyItem>对象。</span><span class="sxs-lookup"><span data-stu-id="6c953-106">stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="6c953-107">可以读取<xref:System.Drawing.Image.PropertyItems%2A>属性的<xref:System.Drawing.Image>要从文件检索的元数据对象。</span><span class="sxs-lookup"><span data-stu-id="6c953-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="6c953-108"><xref:System.Drawing.Image.PropertyItems%2A>属性返回的数组<xref:System.Drawing.Imaging.PropertyItem>对象。</span><span class="sxs-lookup"><span data-stu-id="6c953-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="6c953-109">一个<xref:System.Drawing.Imaging.PropertyItem>对象具有以下四个属性： `Id`， `Value`， `Len`，和`Type`。</span><span class="sxs-lookup"><span data-stu-id="6c953-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="6c953-110">Id</span><span class="sxs-lookup"><span data-stu-id="6c953-110">Id</span></span>  
 <span data-ttu-id="6c953-111">一个标识元数据项的标记。</span><span class="sxs-lookup"><span data-stu-id="6c953-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="6c953-112">可以分配给某些值<xref:System.Drawing.Imaging.PropertyItem.Id%2A>下表中所示。</span><span class="sxs-lookup"><span data-stu-id="6c953-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="6c953-113">十六进制值</span><span class="sxs-lookup"><span data-stu-id="6c953-113">Hexadecimal value</span></span>|<span data-ttu-id="6c953-114">描述</span><span class="sxs-lookup"><span data-stu-id="6c953-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="6c953-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="6c953-115">0x0320</span></span><br /><br /> <span data-ttu-id="6c953-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="6c953-116">0x010F</span></span><br /><br /> <span data-ttu-id="6c953-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="6c953-117">0x0110</span></span><br /><br /> <span data-ttu-id="6c953-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="6c953-118">0x9003</span></span><br /><br /> <span data-ttu-id="6c953-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="6c953-119">0x829A</span></span><br /><br /> <span data-ttu-id="6c953-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="6c953-120">0x5090</span></span><br /><br /> <span data-ttu-id="6c953-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="6c953-121">0x5091</span></span>|<span data-ttu-id="6c953-122">图像标题</span><span class="sxs-lookup"><span data-stu-id="6c953-122">Image title</span></span><br /><br /> <span data-ttu-id="6c953-123">设备制造商</span><span class="sxs-lookup"><span data-stu-id="6c953-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="6c953-124">设备模型</span><span class="sxs-lookup"><span data-stu-id="6c953-124">Equipment model</span></span><br /><br /> <span data-ttu-id="6c953-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="6c953-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="6c953-126">Exif 暴露时间</span><span class="sxs-lookup"><span data-stu-id="6c953-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="6c953-127">亮度表</span><span class="sxs-lookup"><span data-stu-id="6c953-127">Luminance table</span></span><br /><br /> <span data-ttu-id="6c953-128">色度表</span><span class="sxs-lookup"><span data-stu-id="6c953-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="6c953-129">“值”</span><span class="sxs-lookup"><span data-stu-id="6c953-129">Value</span></span>  
 <span data-ttu-id="6c953-130">值的数组。</span><span class="sxs-lookup"><span data-stu-id="6c953-130">An array of values.</span></span> <span data-ttu-id="6c953-131">值的格式由<xref:System.Drawing.Imaging.PropertyItem.Type%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6c953-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="6c953-132">Len</span><span class="sxs-lookup"><span data-stu-id="6c953-132">Len</span></span>  
 <span data-ttu-id="6c953-133">指向的值数组的长度 （以字节为单位）<xref:System.Drawing.Imaging.PropertyItem.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6c953-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="6c953-134">类型</span><span class="sxs-lookup"><span data-stu-id="6c953-134">Type</span></span>  
 <span data-ttu-id="6c953-135">指向数组中的值的数据类型`Value`属性。</span><span class="sxs-lookup"><span data-stu-id="6c953-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="6c953-136">通过指示的格式`Type`下表中显示属性值</span><span class="sxs-lookup"><span data-stu-id="6c953-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="6c953-137">数字值</span><span class="sxs-lookup"><span data-stu-id="6c953-137">Numeric value</span></span>|<span data-ttu-id="6c953-138">描述</span><span class="sxs-lookup"><span data-stu-id="6c953-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="6c953-139">1</span><span class="sxs-lookup"><span data-stu-id="6c953-139">1</span></span>|<span data-ttu-id="6c953-140">包含当前请求的 URL 的</span><span class="sxs-lookup"><span data-stu-id="6c953-140">A</span></span> `Byte`|  
|<span data-ttu-id="6c953-141">2</span><span class="sxs-lookup"><span data-stu-id="6c953-141">2</span></span>|<span data-ttu-id="6c953-142">一个数组`Byte`对象编码为 ASCII</span><span class="sxs-lookup"><span data-stu-id="6c953-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="6c953-143">3</span><span class="sxs-lookup"><span data-stu-id="6c953-143">3</span></span>|<span data-ttu-id="6c953-144">16 位整数</span><span class="sxs-lookup"><span data-stu-id="6c953-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="6c953-145">4</span><span class="sxs-lookup"><span data-stu-id="6c953-145">4</span></span>|<span data-ttu-id="6c953-146">一个 32 位整数</span><span class="sxs-lookup"><span data-stu-id="6c953-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="6c953-147">5</span><span class="sxs-lookup"><span data-stu-id="6c953-147">5</span></span>|<span data-ttu-id="6c953-148">两个数组`Byte`代表有理数的对象</span><span class="sxs-lookup"><span data-stu-id="6c953-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="6c953-149">6</span><span class="sxs-lookup"><span data-stu-id="6c953-149">6</span></span>|<span data-ttu-id="6c953-150">未使用</span><span class="sxs-lookup"><span data-stu-id="6c953-150">Not used</span></span>|  
|<span data-ttu-id="6c953-151">7</span><span class="sxs-lookup"><span data-stu-id="6c953-151">7</span></span>|<span data-ttu-id="6c953-152">未定义</span><span class="sxs-lookup"><span data-stu-id="6c953-152">Undefined</span></span>|  
|<span data-ttu-id="6c953-153">8</span><span class="sxs-lookup"><span data-stu-id="6c953-153">8</span></span>|<span data-ttu-id="6c953-154">未使用</span><span class="sxs-lookup"><span data-stu-id="6c953-154">Not used</span></span>|  
|<span data-ttu-id="6c953-155">9</span><span class="sxs-lookup"><span data-stu-id="6c953-155">9</span></span>|`SLong`|  
|<span data-ttu-id="6c953-156">10</span><span class="sxs-lookup"><span data-stu-id="6c953-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="6c953-157">示例</span><span class="sxs-lookup"><span data-stu-id="6c953-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6c953-158">描述</span><span class="sxs-lookup"><span data-stu-id="6c953-158">Description</span></span>  
 <span data-ttu-id="6c953-159">下面的代码示例读取并显示文件中的元数据的七个部分`FakePhoto.jpg`。</span><span class="sxs-lookup"><span data-stu-id="6c953-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="6c953-160">在列表中的第二个 （索引 1） 属性项<xref:System.Drawing.Imaging.PropertyItem.Id%2A>0x010F （设备制造商） 和<xref:System.Drawing.Imaging.PropertyItem.Type%2A>2 （ASCII 编码的字节数组）。</span><span class="sxs-lookup"><span data-stu-id="6c953-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="6c953-161">此代码示例显示该属性项的值。</span><span class="sxs-lookup"><span data-stu-id="6c953-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="6c953-162">此代码生成类似于以下输出：</span><span class="sxs-lookup"><span data-stu-id="6c953-162">The code produces output similar to the following:</span></span>  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### <a name="code"></a><span data-ttu-id="6c953-163">代码</span><span class="sxs-lookup"><span data-stu-id="6c953-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6c953-164">编译代码</span><span class="sxs-lookup"><span data-stu-id="6c953-164">Compiling the Code</span></span>  
 <span data-ttu-id="6c953-165">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6c953-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="6c953-166">处理窗体的<xref:System.Windows.Forms.Control.Paint>事件并将此代码粘贴到 paint 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6c953-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="6c953-167">必须替换`FakePhoto.jpg`用的映像名称和路径上您的系统和导入有效`System.Drawing.Imaging`命名空间。</span><span class="sxs-lookup"><span data-stu-id="6c953-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c953-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c953-168">See also</span></span>

- [<span data-ttu-id="6c953-169">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="6c953-169">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="6c953-170">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="6c953-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
