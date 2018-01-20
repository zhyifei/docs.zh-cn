---
title: "如何：为控件提供工具箱位图"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 446e0f830e916e7f4118a7374c66f238a60fda02
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>如何：为控件提供工具箱位图
如果你想要为您的控件的特殊图标将出现在**工具箱**，你可以通过使用指定的特定映像<xref:System.Drawing.ToolboxBitmapAttribute>。 此类是一个特性，是一种可以附加到其他类上的特殊类。 有关特性的详细信息，对于 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]，请参阅[不在生成中：Visual Basic 中的特性概述](http://msdn.microsoft.com/library/0d0cff64-892d-4f57-83bd-bef388553d4f)，对于 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]，请参阅[特性](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)。  
  
 使用<xref:System.Drawing.ToolboxBitmapAttribute>，你可以指定一个字符串，指示 16 x 16 像素位图的路径和文件名称。 添加到“工具箱”后，此位图显示在对应的控件旁边。 你还可以指定<xref:System.Type>，在这种情况下加载与该类型相关联的位图。 如果同时指定了<xref:System.Type>和一个字符串，该控件搜索图像资源中包含由指定的类型的程序集的字符串参数指定的名称与<xref:System.Type>参数。  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>指定控件的工具箱位图  
  
1.  添加<xref:System.Drawing.ToolboxBitmapAttribute>到之前控件的类声明`Class`关键字[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]，和更高版本的类声明[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]。  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2.  重新生成项目。  
  
    > [!NOTE]
    >  对于自动生成的控件和组件，位图不会出现在工具箱中。 若要查看位图，请使用“选择工具箱项”对话框重载控件。 有关详细信息，请参阅[演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.ToolboxBitmapAttribute>  
 [演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [设计时开发 Windows 窗体控件](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [属性 (Visual Basic)](~/docs/visual-basic/language-reference/attributes.md)  
 [特性](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
