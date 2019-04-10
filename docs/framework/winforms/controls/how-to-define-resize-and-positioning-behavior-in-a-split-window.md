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
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328668"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="d47d9-102">如何：定义拆分窗口中的大小调整和定位行为</span><span class="sxs-lookup"><span data-stu-id="d47d9-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="d47d9-103">面板的<xref:System.Windows.Forms.SplitContainer>控件有助于使自身也要调整其大小和由用户操作。</span><span class="sxs-lookup"><span data-stu-id="d47d9-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="d47d9-104">但是，将有的时间时要以编程方式控制拆分器 — 其中其定位和可以移动的程度。</span><span class="sxs-lookup"><span data-stu-id="d47d9-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="d47d9-105"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>属性和其他属性上的<xref:System.Windows.Forms.SplitContainer>控件使您的用户界面以满足你需求的行为的精确控制。</span><span class="sxs-lookup"><span data-stu-id="d47d9-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="d47d9-106">下表列出了这些属性。</span><span class="sxs-lookup"><span data-stu-id="d47d9-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="d47d9-107">名称</span><span class="sxs-lookup"><span data-stu-id="d47d9-107">Name</span></span>|<span data-ttu-id="d47d9-108">描述</span><span class="sxs-lookup"><span data-stu-id="d47d9-108">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> <span data-ttu-id="d47d9-109">属性</span><span class="sxs-lookup"><span data-stu-id="d47d9-109">property</span></span>|<span data-ttu-id="d47d9-110">确定是否拆分器是可移动通过键盘或鼠标。</span><span class="sxs-lookup"><span data-stu-id="d47d9-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> <span data-ttu-id="d47d9-111">属性</span><span class="sxs-lookup"><span data-stu-id="d47d9-111">property</span></span>|<span data-ttu-id="d47d9-112">确定在从左边缘或上边缘到可移动拆分条的像素的距离。</span><span class="sxs-lookup"><span data-stu-id="d47d9-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> <span data-ttu-id="d47d9-113">属性</span><span class="sxs-lookup"><span data-stu-id="d47d9-113">property</span></span>|<span data-ttu-id="d47d9-114">确定的最小距离，以像素为单位，用户可以移动拆分器。</span><span class="sxs-lookup"><span data-stu-id="d47d9-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="d47d9-115">下面的示例修改<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>属性来创建"对齐拆分器"的效果; 当用户拖动拆分器，它都增加 10 个像素，而不是默认值 1 为单位。</span><span class="sxs-lookup"><span data-stu-id="d47d9-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="d47d9-116">若要定义 SplitContainer 调整大小行为</span><span class="sxs-lookup"><span data-stu-id="d47d9-116">To define SplitContainer resize behavior</span></span>  
  
1. <span data-ttu-id="d47d9-117">在过程中，设置<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>属性设置为所需的大小，以便实现拆分器的对齐行为。</span><span class="sxs-lookup"><span data-stu-id="d47d9-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="d47d9-118">在以下代码示例中，在窗体内<xref:System.Windows.Forms.Form.Load>事件，在拆分器<xref:System.Windows.Forms.SplitContainer>控件被设置为 10 个像素拖动时跳转。</span><span class="sxs-lookup"><span data-stu-id="d47d9-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
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
  
     <span data-ttu-id="d47d9-119">(Visual C#)将以下代码放在窗体的构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d47d9-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="d47d9-120">稍微向左或向右移动拆分器将具有无明显的效果;但是，当鼠标指针在任一方向的 10 个像素，拆分器将对齐到新位置。</span><span class="sxs-lookup"><span data-stu-id="d47d9-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47d9-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="d47d9-121">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
