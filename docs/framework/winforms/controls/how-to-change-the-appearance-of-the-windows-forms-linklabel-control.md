---
title: "如何：更改 Windows 窗体 LinkLabel 控件的外观"
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
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42aaef183178e7170d3046b4c5daefc8647f7cc1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="eea21-102">如何：更改 Windows 窗体 LinkLabel 控件的外观</span><span class="sxs-lookup"><span data-stu-id="eea21-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="eea21-103">你可以更改显示的文本<xref:System.Windows.Forms.LinkLabel>控件以满足多种用途。</span><span class="sxs-lookup"><span data-stu-id="eea21-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="eea21-104">例如，它是常见的做法，以指示用户后，可以设置要显示在特定颜色带下划线的文本单击文本。</span><span class="sxs-lookup"><span data-stu-id="eea21-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="eea21-105">在用户单击文本后的颜色更改为不同的颜色。</span><span class="sxs-lookup"><span data-stu-id="eea21-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="eea21-106">若要控制此行为，可以设置五个不同的属性： <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>， <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>， <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>， <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>，和<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="eea21-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="eea21-107">若要更改 LinkLabel 控件的外观</span><span class="sxs-lookup"><span data-stu-id="eea21-107">To change the appearance of a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="eea21-108">设置<xref:System.Windows.Forms.LinkLabel.LinkColor%2A>和<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>属性设置为所需的颜色。</span><span class="sxs-lookup"><span data-stu-id="eea21-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="eea21-109">这可以是以编程方式或在设计时在**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="eea21-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
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
  
2.  <span data-ttu-id="eea21-110">设置<xref:System.Windows.Forms.LinkLabel.Text%2A>为适当标题的属性。</span><span class="sxs-lookup"><span data-stu-id="eea21-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="eea21-111">这可以是以编程方式或在设计时在**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="eea21-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  <span data-ttu-id="eea21-112">设置<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>属性来确定哪个部分的标题将指示的链接的形式。</span><span class="sxs-lookup"><span data-stu-id="eea21-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="eea21-113"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A>值表示为带有<xref:System.Windows.Forms.LinkArea>包含两个数字、 起始字符位置和字符数。</span><span class="sxs-lookup"><span data-stu-id="eea21-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="eea21-114">这可以是以编程方式或在设计时在**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="eea21-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  <span data-ttu-id="eea21-115">设置<xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>属性<xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>， <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>，或<xref:System.Windows.Forms.LinkBehavior.NeverUnderline>。</span><span class="sxs-lookup"><span data-stu-id="eea21-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="eea21-116">如果设置为<xref:System.Windows.Forms.LinkBehavior.HoverUnderline>，由标题的一部分<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>当指针停留在其上只会带有下划线。</span><span class="sxs-lookup"><span data-stu-id="eea21-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5.  <span data-ttu-id="eea21-117">在<xref:System.Windows.Forms.LinkLabel.LinkClicked>事件处理程序中，设置<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="eea21-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="eea21-118">访问链接，很常见的做法通常按颜色更改以某种方式，其外观。</span><span class="sxs-lookup"><span data-stu-id="eea21-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="eea21-119">文本将更改为指定的颜色<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="eea21-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eea21-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eea21-120">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>  
 [<span data-ttu-id="eea21-121">LinkLabel 控件概述</span><span class="sxs-lookup"><span data-stu-id="eea21-121">LinkLabel Control Overview</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [<span data-ttu-id="eea21-122">如何：使用 Windows 窗体 LinkLabel 控件链接到对象或网页</span><span class="sxs-lookup"><span data-stu-id="eea21-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [<span data-ttu-id="eea21-123">LinkLabel 控件</span><span class="sxs-lookup"><span data-stu-id="eea21-123">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
