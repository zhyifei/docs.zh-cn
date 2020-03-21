---
title: 设置 Panel 控件的背景
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
ms.openlocfilehash: 36e552475334c25b9d5a6fafb82155c6ebcba266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182097"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>如何：设置 Windows 窗体面板的背景
Windows 窗体<xref:System.Windows.Forms.Panel>控件可以同时显示背景颜色和背景图像。 属性<xref:System.Windows.Forms.Control.BackColor%2A>设置包含控件（如标签和单选按钮）的背景颜色。 如果未设置<xref:System.Windows.Forms.Control.BackgroundImage%2A>该属性，<xref:System.Windows.Forms.Control.BackColor%2A>则所选内容将填充整个面板。 如果设置了<xref:System.Windows.Forms.Control.BackgroundImage%2A>该属性，则图像将显示在包含的控件后面。  
  
### <a name="to-set-the-background-programmatically"></a>以编程方式设置背景  
  
1. 将面板的属性<xref:System.Windows.Forms.Control.BackColor%2A>设置为 类型<xref:System.Drawing.Color?displayProperty=nameWithType>的值 。  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. 使用<xref:System.Windows.Forms.Control.BackgroundImage%2A><xref:System.Drawing.Image?displayProperty=nameWithType>类<xref:System.Drawing.Image.FromFile%2A>的方法设置面板的属性。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Panel 控件](panel-control-windows-forms.md)
- [Panel 控件概述](panel-control-overview-windows-forms.md)
