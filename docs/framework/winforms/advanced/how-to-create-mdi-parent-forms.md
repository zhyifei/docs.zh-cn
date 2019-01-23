---
title: 如何：创建 MDI 父窗体
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: 1cc3d813b77ddf8220242f4a1dfc7fe39f9cb520
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512562"
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="cabbb-102">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="cabbb-102">How to: Create MDI Parent Forms</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="cabbb-103">该话题使用 <xref:System.Windows.Forms.MainMenu> 控制（已由 <xref:System.Windows.Forms.MenuStrip> 控制取代）。</span><span class="sxs-lookup"><span data-stu-id="cabbb-103">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="cabbb-104">如果你选择的话，就会保留 <xref:System.Windows.Forms.MainMenu> 控制以便实现后向兼容性和未来使用。</span><span class="sxs-lookup"><span data-stu-id="cabbb-104">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span>  <span data-ttu-id="cabbb-105">有关创建 MDI 父窗体的使用<xref:System.Windows.Forms.MenuStrip>，请参阅[如何：使用 MenuStrip 创建 MDI 窗口列表](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="cabbb-105">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>  
  
 <span data-ttu-id="cabbb-106">多文档界面 (MDI) 应用程序的基础为 MDI 父窗体。</span><span class="sxs-lookup"><span data-stu-id="cabbb-106">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="cabbb-107">这是包含 MDI 子窗口（用户与 MDI 应用程序交流所在的子窗口）的窗口。</span><span class="sxs-lookup"><span data-stu-id="cabbb-107">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="cabbb-108">在“Windows 窗体设计器”中采用编程方式可轻松创建一个 MDI 父窗体。</span><span class="sxs-lookup"><span data-stu-id="cabbb-108">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="cabbb-109">要在设计时创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="cabbb-109">To create an MDI parent form at design time</span></span>  
  
1.  <span data-ttu-id="cabbb-110">创建一个 Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="cabbb-110">Create a Windows Application project.</span></span>  
  
2.  <span data-ttu-id="cabbb-111">在中**属性**窗口中，将<xref:System.Windows.Forms.Form.IsMdiContainer%2A>属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="cabbb-111">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>  
  
     <span data-ttu-id="cabbb-112">这将该表单指定为适合子窗口的 MDI 容器。</span><span class="sxs-lookup"><span data-stu-id="cabbb-112">This designates the form as an MDI container for child windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cabbb-113">在“属性”窗口中设置属性时，如果你喜欢的话，也可以将 `WindowState` 属性设置为“最大化”，因为父窗体最大化时最容易操作 MDI 子窗口。</span><span class="sxs-lookup"><span data-stu-id="cabbb-113">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="cabbb-114">此外，注意 MDI 父窗体的边缘将获得系统颜色（在 Windows“系统控制面板”中进行设置），而非你使用 <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> 属性设置的背景颜色。</span><span class="sxs-lookup"><span data-stu-id="cabbb-114">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>  
  
3.  <span data-ttu-id="cabbb-115">从“工具箱”中，将“MenuStrip”控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="cabbb-115">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="cabbb-116">创建一个顶级菜单项，将“Text”属性设置为“&File”，其中包含名为“&New”和“&Close”的子菜单项。</span><span class="sxs-lookup"><span data-stu-id="cabbb-116">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="cabbb-117">另创建一个名为“&Window”的顶级菜单项。</span><span class="sxs-lookup"><span data-stu-id="cabbb-117">Also create a top-level menu item called **&Window**.</span></span>  
  
     <span data-ttu-id="cabbb-118">第一个菜单将在运行时创建并隐藏菜单项，第二个菜单将跟踪打开的 MDI 子窗口。</span><span class="sxs-lookup"><span data-stu-id="cabbb-118">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="cabbb-119">这时，你已经创建了一个 MDI 父窗口。</span><span class="sxs-lookup"><span data-stu-id="cabbb-119">At this point, you have created an MDI parent window.</span></span>  
  
4.  <span data-ttu-id="cabbb-120">按 **F5** 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cabbb-120">Press **F5** to run the application.</span></span> <span data-ttu-id="cabbb-121">有关创建 MDI 子窗口的 MDI 父窗体内运行的信息，请参阅[如何：创建 MDI 子窗体](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="cabbb-121">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cabbb-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="cabbb-122">See also</span></span>
- [<span data-ttu-id="cabbb-123">多文档界面 (MDI) 应用程序</span><span class="sxs-lookup"><span data-stu-id="cabbb-123">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="cabbb-124">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="cabbb-124">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="cabbb-125">如何：确定活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="cabbb-125">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="cabbb-126">如何：将数据发送到活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="cabbb-126">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="cabbb-127">如何：排列 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="cabbb-127">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
