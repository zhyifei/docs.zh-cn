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
ms.openlocfilehash: da9a9d40529a1902c58f67d6a8696d8906eb34c9
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040058"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="3d54a-102">如何：通过使用设计器使用 Windows 窗体 TabControl 添加和移除选项卡</span><span class="sxs-lookup"><span data-stu-id="3d54a-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="3d54a-103">将<xref:System.Windows.Forms.TabControl>控件放在窗体上时, 默认情况下它包含两个选项卡。</span><span class="sxs-lookup"><span data-stu-id="3d54a-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="3d54a-104">您可以使用设计器添加或删除选项卡。</span><span class="sxs-lookup"><span data-stu-id="3d54a-104">You can add or remove tabs using the designer.</span></span>

 <span data-ttu-id="3d54a-105">下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.TabControl>包含控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="3d54a-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="3d54a-106">有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="3d54a-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="3d54a-107">使用设计器添加或删除选项卡</span><span class="sxs-lookup"><span data-stu-id="3d54a-107">To add or remove a tab using the designer</span></span>

- <span data-ttu-id="3d54a-108">在控件的智能标记上, 单击 "**添加选项卡**" 或 "**删除选项卡**"</span><span class="sxs-lookup"><span data-stu-id="3d54a-108">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>

     <span data-ttu-id="3d54a-109">或</span><span class="sxs-lookup"><span data-stu-id="3d54a-109">-or-</span></span>

     <span data-ttu-id="3d54a-110">在 "**属性**" 窗口中<xref:System.Windows.Forms.TabControl.TabPages%2A> , 单击属性旁边![的**省略号**按钮 (省略号按钮 (... 属性窗口](./media/visual-studio-ellipsis-button.png)), 以打开**TabPage 集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="3d54a-110">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="3d54a-111">单击 "**添加**或**删除**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="3d54a-111">Click the **Add** or **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d54a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d54a-112">See also</span></span>

- [<span data-ttu-id="3d54a-113">TabControl 控件</span><span class="sxs-lookup"><span data-stu-id="3d54a-113">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="3d54a-114">TabControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="3d54a-114">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="3d54a-115">如何：向选项卡页添加控件</span><span class="sxs-lookup"><span data-stu-id="3d54a-115">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="3d54a-116">如何：禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="3d54a-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="3d54a-117">如何：更改 Windows 窗体 TabControl 的外观</span><span class="sxs-lookup"><span data-stu-id="3d54a-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
