---
title: 如何：通过 Windows 窗体 LinkLabel 控件显示 Web 页面 (Visual Basic)
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
ms.openlocfilehash: 1be9ff06e749d14b46946e899c6ffb6c3a950d65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170022"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="f0867-102">如何：通过 Windows 窗体 LinkLabel 控件显示 Web 页面 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0867-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="f0867-103">此示例在默认浏览器中显示网页，当用户单击 Windows 窗体<xref:System.Windows.Forms.LinkLabel>控件。</span><span class="sxs-lookup"><span data-stu-id="f0867-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0867-104">示例</span><span class="sxs-lookup"><span data-stu-id="f0867-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="f0867-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="f0867-105">Compiling the Code</span></span>  
 <span data-ttu-id="f0867-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f0867-106">This example requires:</span></span>  
  
-   <span data-ttu-id="f0867-107">名为 Windows 窗体`Form1`。</span><span class="sxs-lookup"><span data-stu-id="f0867-107">A Windows Form named `Form1`.</span></span>  
  
-   <span data-ttu-id="f0867-108">名为 `LinkLabel1` 的 <xref:System.Windows.Forms.LinkLabel> 控件。</span><span class="sxs-lookup"><span data-stu-id="f0867-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
-   <span data-ttu-id="f0867-109">活动的 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="f0867-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f0867-110">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="f0867-110">.NET Framework Security</span></span>  
 <span data-ttu-id="f0867-111">对调用<xref:System.Diagnostics.Process.Start%2A>方法需要完全信任。</span><span class="sxs-lookup"><span data-stu-id="f0867-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="f0867-112">有关详细信息，请参阅 <xref:System.Security.SecurityException>。</span><span class="sxs-lookup"><span data-stu-id="f0867-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0867-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0867-113">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="f0867-114">LinkLabel 控件</span><span class="sxs-lookup"><span data-stu-id="f0867-114">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
