---
title: "如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器"
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
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f63ff0a7336ae80ce5652cf3e4c6c7dd409882a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="e196c-102">如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="e196c-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="e196c-103"><xref:System.Windows.Forms.ToolStrip>控件向主题和样式轻松支持。</span><span class="sxs-lookup"><span data-stu-id="e196c-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="e196c-104">你可以通过设置实现完全自定义外观和行为 （外观和感觉）<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>属性或<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>到自定义呈现器的属性。</span><span class="sxs-lookup"><span data-stu-id="e196c-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="e196c-105">你可以将呈现器分配给每个单独<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.MenuStrip>， <xref:System.Windows.Forms.ContextMenuStrip>，或<xref:System.Windows.Forms.StatusStrip>控件，也可以使用<xref:System.Windows.Forms.ToolStripManager.Renderer%2A>属性以影响所有对象通过设置<xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType>属性<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e196c-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e196c-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A>返回<xref:System.Windows.Forms.ToolStripRenderMode.Custom>才的值<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>不`null`。</span><span class="sxs-lookup"><span data-stu-id="e196c-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="e196c-107">若要创建自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="e196c-107">To create a custom renderer</span></span>  
  
1.  <span data-ttu-id="e196c-108">扩展<xref:System.Windows.Forms.ToolStripRenderer>类。</span><span class="sxs-lookup"><span data-stu-id="e196c-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2.  <span data-ttu-id="e196c-109">实现所需的自定义呈现通过重写相应*上...*</span><span class="sxs-lookup"><span data-stu-id="e196c-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="e196c-110">成员</span><span class="sxs-lookup"><span data-stu-id="e196c-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="e196c-111">若要设置为当前呈现器的自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="e196c-111">To set the custom renderer to be the current renderer</span></span>  
  
1.  <span data-ttu-id="e196c-112">若要设置一个自定义呈现器<xref:System.Windows.Forms.ToolStrip>，将其设置<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>到自定义呈现器的属性。</span><span class="sxs-lookup"><span data-stu-id="e196c-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  <span data-ttu-id="e196c-113">也可以将设置所有的自定义呈现器<xref:System.Windows.Forms.ToolStrip>你的应用程序中包含的类： 设置<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>到自定义呈现器和集属性<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>属性<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>。</span><span class="sxs-lookup"><span data-stu-id="e196c-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e196c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e196c-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>  
 [<span data-ttu-id="e196c-115">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="e196c-115">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="e196c-116">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="e196c-116">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="e196c-117">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="e196c-117">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
