---
title: 通过 LinkLabel 控件显示网页（Visual Basic）
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 75373d55b7bc5ef11e39d5b9546996cb1c4f6f7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745927"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>如何：通过 Windows 窗体 LinkLabel 控件显示网页 (Visual Basic)
当用户单击 <xref:System.Windows.Forms.LinkLabel> 控件的 Windows 窗体时，此示例将在默认浏览器中显示网页。  
  
## <a name="example"></a>示例  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `Form1`的 Windows 窗体。  
  
- 名为 <xref:System.Windows.Forms.LinkLabel> 的 `LinkLabel1` 控件。  
  
- 活动 Internet 连接。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 调用 <xref:System.Diagnostics.Process.Start%2A> 方法需要完全信任。 有关详细信息，请参阅 <xref:System.Security.SecurityException>。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.LinkLabel>
- [LinkLabel 控件](linklabel-control-windows-forms.md)
