---
title: 如何：水平拆分窗口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: 7ef3fe1210ae42c52a4fd7f23633d6566bc102a5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956060"
---
# <a name="how-to-split-a-window-horizontally"></a><span data-ttu-id="0ffb2-102">如何：水平拆分窗口</span><span class="sxs-lookup"><span data-stu-id="0ffb2-102">How to: Split a Window Horizontally</span></span>
<span data-ttu-id="0ffb2-103">下面的代码示例将使<xref:System.Windows.Forms.SplitContainer>控件成为水平分隔的拆分器。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-103">The following code example makes the splitter that divides the <xref:System.Windows.Forms.SplitContainer> control horizontal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ffb2-104"><xref:System.Windows.Forms.SplitContainer>控件<xref:System.Windows.Forms.SplitContainer.Orientation%2A>的属性决定拆分器的方向, 而不是控件本身的方向。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-104">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span>  
  
### <a name="to-split-a-window-horizontally"></a><span data-ttu-id="0ffb2-105">水平拆分窗口</span><span class="sxs-lookup"><span data-stu-id="0ffb2-105">To split a window horizontally</span></span>  
  
1. <span data-ttu-id="0ffb2-106">在过程中, 将<xref:System.Windows.Forms.SplitContainer.Orientation%2A> <xref:System.Windows.Forms.SplitContainer>控件的属性设置为<xref:System.Windows.Forms.Orientation.Horizontal>。</span><span class="sxs-lookup"><span data-stu-id="0ffb2-106">Within a procedure, set the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control to <xref:System.Windows.Forms.Orientation.Horizontal>.</span></span>  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0ffb2-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ffb2-107">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="0ffb2-108">SplitContainer 控件</span><span class="sxs-lookup"><span data-stu-id="0ffb2-108">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
