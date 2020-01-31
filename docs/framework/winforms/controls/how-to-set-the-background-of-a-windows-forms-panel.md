---
title: 패널 배경 설정
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
ms.openlocfilehash: ba2619354403793aea7ca15d43649da9637079a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744744"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>방법: Windows Forms 패널의 배경 설정
Windows 窗体 <xref:System.Windows.Forms.Panel> 控件可以同时显示背景色和背景图像。 <xref:System.Windows.Forms.Control.BackColor%2A> 属性设置所包含控件（如标签和单选按钮）的背景色。 如果未设置 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性，则 <xref:System.Windows.Forms.Control.BackColor%2A> 选择将填充整个面板。 如果设置了 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性，则该图像将显示在包含的控件后。  
  
### <a name="to-set-the-background-programmatically"></a>以编程方式设置背景  
  
1. 将面板的 <xref:System.Windows.Forms.Control.BackColor%2A> 属性设置为 <xref:System.Drawing.Color?displayProperty=nameWithType>类型的值。  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. 使用 <xref:System.Drawing.Image?displayProperty=nameWithType> 类的 <xref:System.Drawing.Image.FromFile%2A> 方法设置面板的 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性。  
  
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
- [Panel 컨트롤](panel-control-windows-forms.md)
- [Panel 컨트롤 개요](panel-control-overview-windows-forms.md)
