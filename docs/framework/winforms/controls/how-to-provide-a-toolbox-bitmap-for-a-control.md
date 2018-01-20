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
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="215a8-102">如何：为控件提供工具箱位图</span><span class="sxs-lookup"><span data-stu-id="215a8-102">How to: Provide a Toolbox Bitmap for a Control</span></span>
<span data-ttu-id="215a8-103">如果你想要为您的控件的特殊图标将出现在**工具箱**，你可以通过使用指定的特定映像<xref:System.Drawing.ToolboxBitmapAttribute>。</span><span class="sxs-lookup"><span data-stu-id="215a8-103">If you want to have a special icon for your control appear in the **Toolbox**, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="215a8-104">此类是一个特性，是一种可以附加到其他类上的特殊类。</span><span class="sxs-lookup"><span data-stu-id="215a8-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="215a8-105">有关特性的详细信息，对于 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]，请参阅[不在生成中：Visual Basic 中的特性概述](http://msdn.microsoft.com/library/0d0cff64-892d-4f57-83bd-bef388553d4f)，对于 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]，请参阅[特性](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)。</span><span class="sxs-lookup"><span data-stu-id="215a8-105">For more information about attributes, see [NOT IN BUILD: Attributes Overview in Visual Basic](http://msdn.microsoft.com/library/0d0cff64-892d-4f57-83bd-bef388553d4f) for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] and [Attributes](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205) for [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span></span>  
  
 <span data-ttu-id="215a8-106">使用<xref:System.Drawing.ToolboxBitmapAttribute>，你可以指定一个字符串，指示 16 x 16 像素位图的路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="215a8-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="215a8-107">添加到“工具箱”后，此位图显示在对应的控件旁边。</span><span class="sxs-lookup"><span data-stu-id="215a8-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="215a8-108">你还可以指定<xref:System.Type>，在这种情况下加载与该类型相关联的位图。</span><span class="sxs-lookup"><span data-stu-id="215a8-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="215a8-109">如果同时指定了<xref:System.Type>和一个字符串，该控件搜索图像资源中包含由指定的类型的程序集的字符串参数指定的名称与<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="215a8-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="215a8-110">指定控件的工具箱位图</span><span class="sxs-lookup"><span data-stu-id="215a8-110">To specify a Toolbox bitmap for your control</span></span>  
  
1.  <span data-ttu-id="215a8-111">添加<xref:System.Drawing.ToolboxBitmapAttribute>到之前控件的类声明`Class`关键字[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]，和更高版本的类声明[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="215a8-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], and above the class declaration for [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span></span>  
  
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
  
2.  <span data-ttu-id="215a8-112">重新生成项目。</span><span class="sxs-lookup"><span data-stu-id="215a8-112">Rebuild the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="215a8-113">对于自动生成的控件和组件，位图不会出现在工具箱中。</span><span class="sxs-lookup"><span data-stu-id="215a8-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="215a8-114">若要查看位图，请使用“选择工具箱项”对话框重载控件。</span><span class="sxs-lookup"><span data-stu-id="215a8-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="215a8-115">有关详细信息，请参阅[演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)。</span><span class="sxs-lookup"><span data-stu-id="215a8-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="215a8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="215a8-116">See Also</span></span>  
 <xref:System.Drawing.ToolboxBitmapAttribute>  
 [<span data-ttu-id="215a8-117">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="215a8-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [<span data-ttu-id="215a8-118">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="215a8-118">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="215a8-119">属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="215a8-119">Attributes (Visual Basic)</span></span>](~/docs/visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="215a8-120">特性</span><span class="sxs-lookup"><span data-stu-id="215a8-120">Attributes</span></span>](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
