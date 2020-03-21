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
ms.openlocfilehash: e2b56175e625281a920c390e5feb4238e3cb7f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182524"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="db54b-102">如何：读取图像元数据</span><span class="sxs-lookup"><span data-stu-id="db54b-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="db54b-103">某些图像文件包含元数据，您可以读取元数据以确定图像的功能。</span><span class="sxs-lookup"><span data-stu-id="db54b-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="db54b-104">例如，数字照片可能包含元数据，您可以读取元数据来确定用于捕获图像的相机的制作和型号。</span><span class="sxs-lookup"><span data-stu-id="db54b-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="db54b-105">使用 GDI+，您可以读取现有元数据，还可以将新的元数据写入图像文件。</span><span class="sxs-lookup"><span data-stu-id="db54b-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="db54b-106">GDI+ 将单个元数据段存储在<xref:System.Drawing.Imaging.PropertyItem>对象中。</span><span class="sxs-lookup"><span data-stu-id="db54b-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="db54b-107">可以读取<xref:System.Drawing.Image.PropertyItems%2A><xref:System.Drawing.Image>对象的属性以从文件检索所有元数据。</span><span class="sxs-lookup"><span data-stu-id="db54b-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="db54b-108">属性<xref:System.Drawing.Image.PropertyItems%2A>返回对象数组<xref:System.Drawing.Imaging.PropertyItem>。</span><span class="sxs-lookup"><span data-stu-id="db54b-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="db54b-109">对象<xref:System.Drawing.Imaging.PropertyItem>`Id`具有以下四个属性： 、 `Value``Len`和`Type`。</span><span class="sxs-lookup"><span data-stu-id="db54b-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="db54b-110">ID</span><span class="sxs-lookup"><span data-stu-id="db54b-110">Id</span></span>

<span data-ttu-id="db54b-111">标识元数据项的标记。</span><span class="sxs-lookup"><span data-stu-id="db54b-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="db54b-112">下表中显示了可以分配给<xref:System.Drawing.Imaging.PropertyItem.Id%2A>的一些值：</span><span class="sxs-lookup"><span data-stu-id="db54b-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="db54b-113">十六进制值</span><span class="sxs-lookup"><span data-stu-id="db54b-113">Hexadecimal value</span></span>|<span data-ttu-id="db54b-114">说明</span><span class="sxs-lookup"><span data-stu-id="db54b-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="db54b-115">0 x0320</span><span class="sxs-lookup"><span data-stu-id="db54b-115">0x0320</span></span><br /><br /> <span data-ttu-id="db54b-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="db54b-116">0x010F</span></span><br /><br /> <span data-ttu-id="db54b-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="db54b-117">0x0110</span></span><br /><br /> <span data-ttu-id="db54b-118">0 x9003</span><span class="sxs-lookup"><span data-stu-id="db54b-118">0x9003</span></span><br /><br /> <span data-ttu-id="db54b-119">0 x829A</span><span class="sxs-lookup"><span data-stu-id="db54b-119">0x829A</span></span><br /><br /> <span data-ttu-id="db54b-120">0 x5090</span><span class="sxs-lookup"><span data-stu-id="db54b-120">0x5090</span></span><br /><br /> <span data-ttu-id="db54b-121">0 x5091</span><span class="sxs-lookup"><span data-stu-id="db54b-121">0x5091</span></span>|<span data-ttu-id="db54b-122">图像标题</span><span class="sxs-lookup"><span data-stu-id="db54b-122">Image title</span></span><br /><br /> <span data-ttu-id="db54b-123">设备制造商</span><span class="sxs-lookup"><span data-stu-id="db54b-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="db54b-124">设备型号</span><span class="sxs-lookup"><span data-stu-id="db54b-124">Equipment model</span></span><br /><br /> <span data-ttu-id="db54b-125">ExifDT 原始</span><span class="sxs-lookup"><span data-stu-id="db54b-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="db54b-126">Exif 曝光时间</span><span class="sxs-lookup"><span data-stu-id="db54b-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="db54b-127">亮度表</span><span class="sxs-lookup"><span data-stu-id="db54b-127">Luminance table</span></span><br /><br /> <span data-ttu-id="db54b-128">色度表</span><span class="sxs-lookup"><span data-stu-id="db54b-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="db54b-129">值</span><span class="sxs-lookup"><span data-stu-id="db54b-129">Value</span></span>

<span data-ttu-id="db54b-130">一个 值数组。</span><span class="sxs-lookup"><span data-stu-id="db54b-130">An array of values.</span></span> <span data-ttu-id="db54b-131">值的格式由<xref:System.Drawing.Imaging.PropertyItem.Type%2A>属性确定。</span><span class="sxs-lookup"><span data-stu-id="db54b-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="db54b-132">Len</span><span class="sxs-lookup"><span data-stu-id="db54b-132">Len</span></span>

<span data-ttu-id="db54b-133"><xref:System.Drawing.Imaging.PropertyItem.Value%2A>属性指向的值数组的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="db54b-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="db54b-134">类型</span><span class="sxs-lookup"><span data-stu-id="db54b-134">Type</span></span>

<span data-ttu-id="db54b-135">属性指向的数组中值的`Value`数据类型。</span><span class="sxs-lookup"><span data-stu-id="db54b-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="db54b-136">属性值指示的`Type`格式显示在下表中：</span><span class="sxs-lookup"><span data-stu-id="db54b-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="db54b-137">数值</span><span class="sxs-lookup"><span data-stu-id="db54b-137">Numeric value</span></span>|<span data-ttu-id="db54b-138">说明</span><span class="sxs-lookup"><span data-stu-id="db54b-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="db54b-139">1</span><span class="sxs-lookup"><span data-stu-id="db54b-139">1</span></span>|<span data-ttu-id="db54b-140">一个 `Byte` 类型的值</span><span class="sxs-lookup"><span data-stu-id="db54b-140">A `Byte`</span></span>|
|<span data-ttu-id="db54b-141">2</span><span class="sxs-lookup"><span data-stu-id="db54b-141">2</span></span>|<span data-ttu-id="db54b-142">编码为`Byte`ASCII 的对象数组</span><span class="sxs-lookup"><span data-stu-id="db54b-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="db54b-143">3</span><span class="sxs-lookup"><span data-stu-id="db54b-143">3</span></span>|<span data-ttu-id="db54b-144">16 位整数</span><span class="sxs-lookup"><span data-stu-id="db54b-144">A 16-bit integer</span></span>|
|<span data-ttu-id="db54b-145">4</span><span class="sxs-lookup"><span data-stu-id="db54b-145">4</span></span>|<span data-ttu-id="db54b-146">32 位整数</span><span class="sxs-lookup"><span data-stu-id="db54b-146">A 32-bit integer</span></span>|
|<span data-ttu-id="db54b-147">5</span><span class="sxs-lookup"><span data-stu-id="db54b-147">5</span></span>|<span data-ttu-id="db54b-148">表示合理数字的`Byte`两个对象的数组</span><span class="sxs-lookup"><span data-stu-id="db54b-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="db54b-149">6</span><span class="sxs-lookup"><span data-stu-id="db54b-149">6</span></span>|<span data-ttu-id="db54b-150">未使用</span><span class="sxs-lookup"><span data-stu-id="db54b-150">Not used</span></span>|
|<span data-ttu-id="db54b-151">7</span><span class="sxs-lookup"><span data-stu-id="db54b-151">7</span></span>|<span data-ttu-id="db54b-152">Undefined</span><span class="sxs-lookup"><span data-stu-id="db54b-152">Undefined</span></span>|
|<span data-ttu-id="db54b-153">8</span><span class="sxs-lookup"><span data-stu-id="db54b-153">8</span></span>|<span data-ttu-id="db54b-154">未使用</span><span class="sxs-lookup"><span data-stu-id="db54b-154">Not used</span></span>|
|<span data-ttu-id="db54b-155">9</span><span class="sxs-lookup"><span data-stu-id="db54b-155">9</span></span>|`SLong`|
|<span data-ttu-id="db54b-156">10</span><span class="sxs-lookup"><span data-stu-id="db54b-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="db54b-157">示例</span><span class="sxs-lookup"><span data-stu-id="db54b-157">Example</span></span>
  
<span data-ttu-id="db54b-158">以下代码示例读取并显示文件中`FakePhoto.jpg`的七个元数据片段。</span><span class="sxs-lookup"><span data-stu-id="db54b-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="db54b-159">列表中的第二个（索引 1）属性项具有<xref:System.Drawing.Imaging.PropertyItem.Id%2A>0x010F（设备制造商）和<xref:System.Drawing.Imaging.PropertyItem.Type%2A>2（ASCII 编码字节数组）。</span><span class="sxs-lookup"><span data-stu-id="db54b-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="db54b-160">代码示例显示该属性项的值。</span><span class="sxs-lookup"><span data-stu-id="db54b-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="db54b-161">该代码生成类似于以下内容的输出：</span><span class="sxs-lookup"><span data-stu-id="db54b-161">The code produces output similar to the following:</span></span>

```output
 Property Item 0
  
 id: 0x320
  
 type: 2

 length: 16 bytes
  
 Property Item 1
  
 id: 0x10f
  
 type: 2
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```

## <a name="compiling-the-code"></a><span data-ttu-id="db54b-162">编译代码</span><span class="sxs-lookup"><span data-stu-id="db54b-162">Compiling the Code</span></span>

<span data-ttu-id="db54b-163">前面的示例设计用于 Windows 窗体，它需要<xref:System.Windows.Forms.PaintEventArgs>`e`，这是事件处理程序的<xref:System.Windows.Forms.Control.Paint>参数。</span><span class="sxs-lookup"><span data-stu-id="db54b-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="db54b-164">处理窗体<xref:System.Windows.Forms.Control.Paint>的事件并将此代码粘贴到绘制事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="db54b-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="db54b-165">您必须替换为`FakePhoto.jpg`系统上有效的图像名称和路径，`System.Drawing.Imaging`并导入命名空间。</span><span class="sxs-lookup"><span data-stu-id="db54b-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="db54b-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db54b-166">See also</span></span>

- [<span data-ttu-id="db54b-167">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="db54b-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="db54b-168">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="db54b-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
