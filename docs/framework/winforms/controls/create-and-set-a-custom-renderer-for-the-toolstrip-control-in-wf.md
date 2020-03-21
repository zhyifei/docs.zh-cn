---
title: 如何：为工具条控件创建和设置自定义渲染器
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
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182407"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="595b2-102">如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="595b2-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="595b2-103"><xref:System.Windows.Forms.ToolStrip>控件为主题和样式提供了简单的支持。</span><span class="sxs-lookup"><span data-stu-id="595b2-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="595b2-104">通过将属性或属性设置为自定义呈现器，<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType><xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>可以完全自定义外观和行为（外观）。</span><span class="sxs-lookup"><span data-stu-id="595b2-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="595b2-105"><xref:System.Windows.Forms.ToolStrip>可以将渲染器分配给每个单独的 、、<xref:System.Windows.Forms.ContextMenuStrip><xref:System.Windows.Forms.StatusStrip><xref:System.Windows.Forms.ToolStripManager.Renderer%2A><xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType><xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType><xref:System.Windows.Forms.MenuStrip>或控件，也可以使用 属性通过将 属性设置为 来影响所有对象。</span><span class="sxs-lookup"><span data-stu-id="595b2-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="595b2-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>仅当<xref:System.Windows.Forms.ToolStripRenderMode.Custom>的值<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>不是`null`时才返回。</span><span class="sxs-lookup"><span data-stu-id="595b2-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="595b2-107">创建自定义渲染器</span><span class="sxs-lookup"><span data-stu-id="595b2-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="595b2-108">扩展类<xref:System.Windows.Forms.ToolStripRenderer>。</span><span class="sxs-lookup"><span data-stu-id="595b2-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="595b2-109">通过重写适当的*On...*</span><span class="sxs-lookup"><span data-stu-id="595b2-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="595b2-110">members</span><span class="sxs-lookup"><span data-stu-id="595b2-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="595b2-111">将自定义渲染器设置为当前渲染器</span><span class="sxs-lookup"><span data-stu-id="595b2-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="595b2-112">要为其中<xref:System.Windows.Forms.ToolStrip>设置自定义呈现器，将<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>属性设置为自定义呈现器。</span><span class="sxs-lookup"><span data-stu-id="595b2-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="595b2-113">或者为应用程序中包含的<xref:System.Windows.Forms.ToolStrip>所有类设置自定义呈现器：将<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>属性设置为自定义呈现器，<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>并将该属性设置为<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>。</span><span class="sxs-lookup"><span data-stu-id="595b2-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="595b2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="595b2-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="595b2-115">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="595b2-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="595b2-116">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="595b2-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="595b2-117">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="595b2-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
