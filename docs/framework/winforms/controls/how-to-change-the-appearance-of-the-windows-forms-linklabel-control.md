---
title: 更改链接标签控件的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142125"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>如何：更改 Windows 窗体 LinkLabel 控件的外观
您可以更改<xref:System.Windows.Forms.LinkLabel>控件显示的文本，以适应各种用途。 例如，通常的做法是，通过将文本设置为以带有下划线的特定颜色显示，可以向用户指示可以单击文本。 用户单击文本后，颜色将更改为其他颜色。 要控制此行为，可以设置五个不同的<xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>属性：、 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>、<xref:System.Windows.Forms.LinkLabel.LinkColor%2A><xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>和<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>属性。  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>更改链接标签控件的外观  
  
1. 将<xref:System.Windows.Forms.LinkLabel.LinkColor%2A>和<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>属性设置为所需的颜色。  
  
     这可以以编程方式或在 **"属性"** 窗口中的设计时间完成。  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. 将<xref:System.Windows.Forms.LinkLabel.Text%2A>属性设置为适当的标题。  
  
     这可以以编程方式或在 **"属性"** 窗口中的设计时间完成。  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. 设置属性<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>以确定标题的哪个部分将指示为链接。  
  
     该<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>值用<xref:System.Windows.Forms.LinkArea>包含两个数字、起始字符位置和字符数表示。 这可以以编程方式或在 **"属性"** 窗口中的设计时间完成。  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. 将<xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>属性设置为<xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>或<xref:System.Windows.Forms.LinkBehavior.HoverUnderline>。 <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>  
  
     如果设置为<xref:System.Windows.Forms.LinkBehavior.HoverUnderline>，则确定<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>的标题部分仅在指针位于其上时进行下划线。  
  
5. 在事件<xref:System.Windows.Forms.LinkLabel.LinkClicked>处理程序中，将<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>属性设置为`true`。  
  
     访问链接后，通常的做法是以某种方式（通常按颜色）更改其外观。 文本将更改为<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>属性指定的颜色。  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [LinkLabel 控件概述](linklabel-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 LinkLabel 控件链接到对象或网页](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [LinkLabel 控件](linklabel-control-windows-forms.md)
