---
title: 如何：将现有的控件重新分配给不同的父控件
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 84e662e0bd2689115abe128c6442e4462eed3e18
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987036"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="0a43f-102">如何：将现有控件重新分配给不同的父控件</span><span class="sxs-lookup"><span data-stu-id="0a43f-102">How to: Reassign existing controls to a different parent</span></span>

<span data-ttu-id="0a43f-103">可以将你窗体中的控件分配到新容器控件。</span><span class="sxs-lookup"><span data-stu-id="0a43f-103">You can assign controls that exist on your form to a new container control.</span></span>

1. <span data-ttu-id="0a43f-104">在 Visual Studio 中, 将<xref:System.Windows.Forms.Button> **"工具箱**" 中的三个控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="0a43f-104">In Visual Studio, drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span> <span data-ttu-id="0a43f-105">将其相邻放置，但不用对齐它们。</span><span class="sxs-lookup"><span data-stu-id="0a43f-105">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="0a43f-106">在“工具箱”中，单击 <xref:System.Windows.Forms.FlowLayoutPanel> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="0a43f-106">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span> <span data-ttu-id="0a43f-107">(请勿将该图标拖动到窗体上。)</span><span class="sxs-lookup"><span data-stu-id="0a43f-107">(Do not drag the icon onto the form.)</span></span>

3. <span data-ttu-id="0a43f-108">将鼠标指针移至靠近这 3 个 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="0a43f-108">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

   <span data-ttu-id="0a43f-109">指针更改为十字线时就会附上 <xref:System.Windows.Forms.FlowLayoutPanel> 控件图标。</span><span class="sxs-lookup"><span data-stu-id="0a43f-109">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="0a43f-110">单击并按住鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="0a43f-110">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="0a43f-111">拖动鼠标指针以绘制 <xref:System.Windows.Forms.FlowLayoutPanel> 控件的轮廓。</span><span class="sxs-lookup"><span data-stu-id="0a43f-111">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="0a43f-112">在这三个 <xref:System.Windows.Forms.Button> 控件周围绘制轮廓。</span><span class="sxs-lookup"><span data-stu-id="0a43f-112">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="0a43f-113">释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="0a43f-113">Release the mouse button.</span></span>

   <span data-ttu-id="0a43f-114">这三种 <xref:System.Windows.Forms.Button> 控件现在插入到 <xref:System.Windows.Forms.FlowLayoutPanel> 控件中。</span><span class="sxs-lookup"><span data-stu-id="0a43f-114">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a43f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a43f-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="0a43f-116">演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="0a43f-116">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="0a43f-117">演练：使用对齐线排列 Windows 窗体上的控件</span><span class="sxs-lookup"><span data-stu-id="0a43f-117">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
