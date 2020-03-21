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
# <a name="how-to-read-image-metadata"></a>如何：读取图像元数据

某些图像文件包含元数据，您可以读取元数据以确定图像的功能。 例如，数字照片可能包含元数据，您可以读取元数据来确定用于捕获图像的相机的制作和型号。 使用 GDI+，您可以读取现有元数据，还可以将新的元数据写入图像文件。

GDI+ 将单个元数据段存储在<xref:System.Drawing.Imaging.PropertyItem>对象中。 可以读取<xref:System.Drawing.Image.PropertyItems%2A><xref:System.Drawing.Image>对象的属性以从文件检索所有元数据。 属性<xref:System.Drawing.Image.PropertyItems%2A>返回对象数组<xref:System.Drawing.Imaging.PropertyItem>。

对象<xref:System.Drawing.Imaging.PropertyItem>`Id`具有以下四个属性： 、 `Value``Len`和`Type`。

## <a name="id"></a>ID

标识元数据项的标记。 下表中显示了可以分配给<xref:System.Drawing.Imaging.PropertyItem.Id%2A>的一些值：

|十六进制值|说明|
|-----------------------|-----------------|
|0 x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0 x9003<br /><br /> 0 x829A<br /><br /> 0 x5090<br /><br /> 0 x5091|图像标题<br /><br /> 设备制造商<br /><br /> 设备型号<br /><br /> ExifDT 原始<br /><br /> Exif 曝光时间<br /><br /> 亮度表<br /><br /> 色度表|

## <a name="value"></a>值

一个 值数组。 值的格式由<xref:System.Drawing.Imaging.PropertyItem.Type%2A>属性确定。

## <a name="len"></a>Len

<xref:System.Drawing.Imaging.PropertyItem.Value%2A>属性指向的值数组的长度（以字节为单位）。

## <a name="type"></a>类型

属性指向的数组中值的`Value`数据类型。 属性值指示的`Type`格式显示在下表中：

|数值|说明|
|-------------------|-----------------|
|1|一个 `Byte` 类型的值|
|2|编码为`Byte`ASCII 的对象数组|
|3|16 位整数|
|4|32 位整数|
|5|表示合理数字的`Byte`两个对象的数组|
|6|未使用|
|7|Undefined|
|8|未使用|
|9|`SLong`|
|10|`SRational`|

## <a name="example"></a>示例
  
以下代码示例读取并显示文件中`FakePhoto.jpg`的七个元数据片段。 列表中的第二个（索引 1）属性项具有<xref:System.Drawing.Imaging.PropertyItem.Id%2A>0x010F（设备制造商）和<xref:System.Drawing.Imaging.PropertyItem.Type%2A>2（ASCII 编码字节数组）。 代码示例显示该属性项的值。

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

该代码生成类似于以下内容的输出：

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

## <a name="compiling-the-code"></a>编译代码

前面的示例设计用于 Windows 窗体，它需要<xref:System.Windows.Forms.PaintEventArgs>`e`，这是事件处理程序的<xref:System.Windows.Forms.Control.Paint>参数。 处理窗体<xref:System.Windows.Forms.Control.Paint>的事件并将此代码粘贴到绘制事件处理程序中。 您必须替换为`FakePhoto.jpg`系统上有效的图像名称和路径，`System.Drawing.Imaging`并导入命名空间。

## <a name="see-also"></a>另请参阅

- [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
