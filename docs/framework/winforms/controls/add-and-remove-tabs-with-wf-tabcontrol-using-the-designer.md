---
title: 如何：通过使用设计器使用 Windows 窗体 TabControl 添加和移除选项卡
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 23fe9fa2b8405a6ebe66e8f0cee1d81d45f2395b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640361"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="87d22-102">如何：通过使用设计器使用 Windows 窗体 TabControl 添加和移除选项卡</span><span class="sxs-lookup"><span data-stu-id="87d22-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="87d22-103">在将<xref:System.Windows.Forms.TabControl>控制窗体中，它包含两个选项卡默认情况下。</span><span class="sxs-lookup"><span data-stu-id="87d22-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="87d22-104">可以添加或删除使用设计器的选项卡。</span><span class="sxs-lookup"><span data-stu-id="87d22-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="87d22-105">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.TabControl>控件。</span><span class="sxs-lookup"><span data-stu-id="87d22-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="87d22-106">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="87d22-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87d22-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="87d22-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="87d22-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="87d22-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="87d22-109">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="87d22-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="87d22-110">若要添加或删除使用设计器的选项卡</span><span class="sxs-lookup"><span data-stu-id="87d22-110">To add or remove a tab using the designer</span></span>  
  
- <span data-ttu-id="87d22-111">在控件的智能标记上，单击**添加选项卡**或**删除选项卡**</span><span class="sxs-lookup"><span data-stu-id="87d22-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="87d22-112">或</span><span class="sxs-lookup"><span data-stu-id="87d22-112">-or-</span></span>  
  
     <span data-ttu-id="87d22-113">在中**属性**窗口中，单击**省略号**按钮 (![VisualStudioEllipsesButton 屏幕快照](../media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.TabControl.TabPages%2A>以打开**TabPage 集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="87d22-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="87d22-114">单击**外**或**删除**按钮。</span><span class="sxs-lookup"><span data-stu-id="87d22-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d22-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="87d22-115">See also</span></span>

- [<span data-ttu-id="87d22-116">TabControl 控件</span><span class="sxs-lookup"><span data-stu-id="87d22-116">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="87d22-117">TabControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="87d22-117">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="87d22-118">如何：向选项卡页添加控件</span><span class="sxs-lookup"><span data-stu-id="87d22-118">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="87d22-119">如何：禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="87d22-119">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="87d22-120">如何：更改 Windows 窗体 TabControl 的外观</span><span class="sxs-lookup"><span data-stu-id="87d22-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
