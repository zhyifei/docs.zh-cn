---
title: 如何：设置 Windows 窗体面板的背景
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: 289a91481c832a36b4b77d56ba6b18921ef02d5b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227999"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a><span data-ttu-id="55e2e-102">如何：设置 Windows 窗体面板的背景</span><span class="sxs-lookup"><span data-stu-id="55e2e-102">How to: Set the Background of a Windows Forms Panel</span></span>
<span data-ttu-id="55e2e-103">Windows 窗体<xref:System.Windows.Forms.Panel>控件可以显示背景色和背景图像。</span><span class="sxs-lookup"><span data-stu-id="55e2e-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="55e2e-104"><xref:System.Windows.Forms.Control.BackColor%2A>属性设置为包含的控件，如标签和单选按钮的背景色。</span><span class="sxs-lookup"><span data-stu-id="55e2e-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for the contained controls, such as labels and radio buttons.</span></span> <span data-ttu-id="55e2e-105">如果<xref:System.Windows.Forms.Control.BackgroundImage%2A>未设置属性，<xref:System.Windows.Forms.Control.BackColor%2A>选择将填充整个面板。</span><span class="sxs-lookup"><span data-stu-id="55e2e-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill the entire panel.</span></span> <span data-ttu-id="55e2e-106">如果<xref:System.Windows.Forms.Control.BackgroundImage%2A>属性设置，则图像将显示在包含控件的后面。</span><span class="sxs-lookup"><span data-stu-id="55e2e-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the contained controls.</span></span>  
  
### <a name="to-set-the-background-programmatically"></a><span data-ttu-id="55e2e-107">若要以编程方式设置的背景</span><span class="sxs-lookup"><span data-stu-id="55e2e-107">To set the background programmatically</span></span>  
  
1.  <span data-ttu-id="55e2e-108">设置的面板<xref:System.Windows.Forms.Control.BackColor%2A>属性的值类型<xref:System.Drawing.Color?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="55e2e-108">Set the panel's <xref:System.Windows.Forms.Control.BackColor%2A> property to a value of type <xref:System.Drawing.Color?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2.  <span data-ttu-id="55e2e-109">设置的面板<xref:System.Windows.Forms.Control.BackgroundImage%2A>属性使用<xref:System.Drawing.Image.FromFile%2A>方法的<xref:System.Drawing.Image?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="55e2e-109">Set the panel's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image?displayProperty=nameWithType> class.</span></span>  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="55e2e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="55e2e-110">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="55e2e-111">Panel 控件</span><span class="sxs-lookup"><span data-stu-id="55e2e-111">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="55e2e-112">Panel 控件概述</span><span class="sxs-lookup"><span data-stu-id="55e2e-112">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
