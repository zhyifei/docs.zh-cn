---
title: 如何：定义拆分窗口中的大小调整和定位行为
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 015e93fb551b8d48b8a57662b8def61c3cb46c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531630"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="1ef81-102">如何：定义拆分窗口中的大小调整和定位行为</span><span class="sxs-lookup"><span data-stu-id="1ef81-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="1ef81-103">面板的<xref:System.Windows.Forms.SplitContainer>控制有助于使自身对其大小调整和由用户操作。</span><span class="sxs-lookup"><span data-stu-id="1ef81-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="1ef81-104">但是，将有的时候你将想要以编程方式控制拆分器-它位于，其中可以移动的程度。</span><span class="sxs-lookup"><span data-stu-id="1ef81-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="1ef81-105"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>属性和其他属性上的<xref:System.Windows.Forms.SplitContainer>控件使你的用户界面以满足你需求的行为的精确控制。</span><span class="sxs-lookup"><span data-stu-id="1ef81-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="1ef81-106">下表中列出了这些属性。</span><span class="sxs-lookup"><span data-stu-id="1ef81-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="1ef81-107">名称</span><span class="sxs-lookup"><span data-stu-id="1ef81-107">Name</span></span>|<span data-ttu-id="1ef81-108">描述</span><span class="sxs-lookup"><span data-stu-id="1ef81-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1ef81-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="1ef81-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="1ef81-110">确定是否通过键盘或鼠标可移动拆分器。</span><span class="sxs-lookup"><span data-stu-id="1ef81-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="1ef81-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="1ef81-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="1ef81-112">确定以到可移动拆分条从左侧或右上边缘像素为单位的距离。</span><span class="sxs-lookup"><span data-stu-id="1ef81-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="1ef81-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 属性</span><span class="sxs-lookup"><span data-stu-id="1ef81-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="1ef81-114">确定的最小距离，以像素为单位，用户可以移动拆分器。</span><span class="sxs-lookup"><span data-stu-id="1ef81-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="1ef81-115">下面的示例修改<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>属性来创建"对齐拆分"的效果; 当用户拖动拆分器，递增的 10 个像素，而不是默认值 1 单位。</span><span class="sxs-lookup"><span data-stu-id="1ef81-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="1ef81-116">若要定义 SplitContainer，调整大小行为</span><span class="sxs-lookup"><span data-stu-id="1ef81-116">To define SplitContainer resize behavior</span></span>  
  
1.  <span data-ttu-id="1ef81-117">在过程中，设置<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>属性设置为所需的大小，以便实现拆分器的对齐行为。</span><span class="sxs-lookup"><span data-stu-id="1ef81-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="1ef81-118">在以下代码示例中，在窗体的<xref:System.Windows.Forms.Form.Load>事件、 中的拆分<xref:System.Windows.Forms.SplitContainer>控件设置跳转时拖放的 10 个像素。</span><span class="sxs-lookup"><span data-stu-id="1ef81-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     <span data-ttu-id="1ef81-119">(Visual C#)将以下代码放在窗体的构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1ef81-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="1ef81-120">略有向左或向右移动拆分器会有明显的效果;但是，当鼠标指针的两个方向的 10 个像素，拆分器将与新的位置对齐。</span><span class="sxs-lookup"><span data-stu-id="1ef81-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef81-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ef81-121">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
