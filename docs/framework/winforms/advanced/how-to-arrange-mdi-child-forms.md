---
title: "如何：排列 MDI 子窗体"
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
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5273327c283f873352f62462cc4be59e4b34351f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-arrange-mdi-child-forms"></a><span data-ttu-id="3a33d-102">如何：排列 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="3a33d-102">How to: Arrange MDI Child Forms</span></span>
<span data-ttu-id="3a33d-103">通常，应用程序会有用于操作（例如“平铺”、“级联”和“排列”）的菜单命令，这些命令会控制打开的 MDI 子窗体布局。</span><span class="sxs-lookup"><span data-stu-id="3a33d-103">Often, applications will have menu commands for actions such as Tile, Cascade, and Arrange, which control the layout of the open MDI child forms.</span></span> <span data-ttu-id="3a33d-104">你可以使用 <xref:System.Windows.Forms.Form.LayoutMdi%2A> 方法和一个 <xref:System.Windows.Forms.MdiLayout> 枚举值来重排 MDI 父窗体中的子窗体。</span><span class="sxs-lookup"><span data-stu-id="3a33d-104">You can use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method with one of the <xref:System.Windows.Forms.MdiLayout> enumeration values to rearrange the child forms in an MDI parent form.</span></span>  
  
 <span data-ttu-id="3a33d-105"><xref:System.Windows.Forms.MdiLayout> 枚举值将子窗体显示为水平或垂直平铺的级联或沿 MDI 窗体下部排列的子窗体图表。</span><span class="sxs-lookup"><span data-stu-id="3a33d-105">The <xref:System.Windows.Forms.MdiLayout> enumeration values display child forms as cascading, as horizontally or vertically tiled, or as child form icons arranged along the lower portion of the MDI form.</span></span> <span data-ttu-id="3a33d-106">这些值具有相同的效果与 Windows 命令**层叠窗口**，**并排显示 windows**，**显示 windows 堆积**，和**显示桌面**分别。</span><span class="sxs-lookup"><span data-stu-id="3a33d-106">These values have the same effect as the Windows commands **Cascade windows**, **Show windows side by side**, **Show windows stacked**, and **Show the desktop**, respectively.</span></span>  
  
 <span data-ttu-id="3a33d-107">通常，这些方法用作菜单项 <xref:System.Windows.Forms.Control.Click> 事件调用的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3a33d-107">Often, these methods are used as the event handlers called by a menu item's <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="3a33d-108">通过此方法，包含文本“级联窗口”的菜单项可实现对 MDI 子窗口的预期效果。</span><span class="sxs-lookup"><span data-stu-id="3a33d-108">In this way, a menu item with the text "Cascade Windows" can have the desired effect on the MDI child windows.</span></span>  
  
### <a name="to-arrange-child-forms"></a><span data-ttu-id="3a33d-109">要排列子窗体</span><span class="sxs-lookup"><span data-stu-id="3a33d-109">To arrange child forms</span></span>  
  
1.  <span data-ttu-id="3a33d-110">在一个方法中，使用 <xref:System.Windows.Forms.Form.LayoutMdi%2A> 方法来设置 MDI 父窗体的 <xref:System.Windows.Forms.MdiLayout> 枚举。</span><span class="sxs-lookup"><span data-stu-id="3a33d-110">In a method, use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method to set the <xref:System.Windows.Forms.MdiLayout> enumeration for the MDI parent form.</span></span> <span data-ttu-id="3a33d-111">下面的示例使用 MDI 父窗体的子窗口（<xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType>）的 `Form1` 枚举值。</span><span class="sxs-lookup"><span data-stu-id="3a33d-111">The following example uses the <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> enumeration value for the child windows of the MDI parent form (`Form1`).</span></span> <span data-ttu-id="3a33d-112">事件处理程序期间，枚举用于代码中<xref:System.Windows.Forms.Control.Click>事件**级联窗口**菜单项。</span><span class="sxs-lookup"><span data-stu-id="3a33d-112">The enumeration is used in code during the event handler for the <xref:System.Windows.Forms.Control.Click> event of the **Cascade Windows** menu item.</span></span>  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="3a33d-113">你也可以通过更改使用的 <xref:System.Windows.Forms.MdiLayout> 枚举值来堆积窗口并以图标形式排列窗口。</span><span class="sxs-lookup"><span data-stu-id="3a33d-113">You can also tile windows and arranging windows as icons by changing the <xref:System.Windows.Forms.MdiLayout> enumeration value used.</span></span>  
  
2.  <span data-ttu-id="3a33d-114">如果你正在使用 Visual C#，将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3a33d-114">If you’re using Visual C#, place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3a33d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a33d-115">See Also</span></span>  
 [<span data-ttu-id="3a33d-116">多文档界面 (MDI) 应用程序</span><span class="sxs-lookup"><span data-stu-id="3a33d-116">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="3a33d-117">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="3a33d-117">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="3a33d-118">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="3a33d-118">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="3a33d-119">如何：确定活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="3a33d-119">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [<span data-ttu-id="3a33d-120">如何：将数据发送到活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="3a33d-120">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
