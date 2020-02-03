---
title: 如何：为 ToolStrip 控件创建和设置自定义呈现器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: ad5ced42754fba6a714452220dd824c4f54fb5e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743419"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="7d8bc-102">如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="7d8bc-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="7d8bc-103"><xref:System.Windows.Forms.ToolStrip> 控件可以轻松地支持主题和样式。</span><span class="sxs-lookup"><span data-stu-id="7d8bc-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="7d8bc-104">可以通过将 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性或 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器来实现完全自定义的外观和行为（外观和感觉）。</span><span class="sxs-lookup"><span data-stu-id="7d8bc-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="7d8bc-105">可以将呈现器分配给每个 <xref:System.Windows.Forms.ToolStrip>、<xref:System.Windows.Forms.MenuStrip>、<xref:System.Windows.Forms.ContextMenuStrip>或 <xref:System.Windows.Forms.StatusStrip> 控件，也可以通过将 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> 属性设置为 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> 来使用 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>属性来影响所有对象。</span><span class="sxs-lookup"><span data-stu-id="7d8bc-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d8bc-106">仅当 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 的值不 `null`时，<xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 才返回 <xref:System.Windows.Forms.ToolStripRenderMode.Custom>。</span><span class="sxs-lookup"><span data-stu-id="7d8bc-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="7d8bc-107">创建自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="7d8bc-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="7d8bc-108">扩展 <xref:System.Windows.Forms.ToolStripRenderer> 类。</span><span class="sxs-lookup"><span data-stu-id="7d8bc-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="7d8bc-109">通过重写适当*的*来实现所需的自定义呈现</span><span class="sxs-lookup"><span data-stu-id="7d8bc-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="7d8bc-110">成员</span><span class="sxs-lookup"><span data-stu-id="7d8bc-110">members</span></span>  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="7d8bc-111">将自定义呈现器设置为当前呈现器</span><span class="sxs-lookup"><span data-stu-id="7d8bc-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="7d8bc-112">若要为一个 <xref:System.Windows.Forms.ToolStrip>设置自定义呈现器，请将 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器。</span><span class="sxs-lookup"><span data-stu-id="7d8bc-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="7d8bc-113">或者，为应用程序中包含的所有 <xref:System.Windows.Forms.ToolStrip> 类设置自定义呈现器：将 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器并将 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 属性设置为 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>。</span><span class="sxs-lookup"><span data-stu-id="7d8bc-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7d8bc-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d8bc-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="7d8bc-115">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="7d8bc-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="7d8bc-116">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="7d8bc-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="7d8bc-117">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="7d8bc-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
