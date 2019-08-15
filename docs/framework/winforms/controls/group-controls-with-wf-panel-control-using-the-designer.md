---
title: 如何：通过使用设计器使用 Windows 窗体 Panel 控件对控件进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: cadfa715b140c63b216ec0ca2e6d6a6589ae3458
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040385"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="3f0f5-102">如何：通过使用设计器使用 Windows 窗体 Panel 控件对控件进行分组</span><span class="sxs-lookup"><span data-stu-id="3f0f5-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="3f0f5-103">Windows 窗体<xref:System.Windows.Forms.Panel>控件用于对其他控件进行分组。</span><span class="sxs-lookup"><span data-stu-id="3f0f5-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="3f0f5-104">分组控件有三个原因。</span><span class="sxs-lookup"><span data-stu-id="3f0f5-104">There are three reasons to group controls.</span></span> <span data-ttu-id="3f0f5-105">一个是清晰用户界面的相关窗体元素的直观分组;另一种是按编程分组, 例如单选按钮;最后一种是在设计时将控件作为一个单元移动。</span><span class="sxs-lookup"><span data-stu-id="3f0f5-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>

## <a name="to-create-a-group-of-controls"></a><span data-ttu-id="3f0f5-106">创建一组控件</span><span class="sxs-lookup"><span data-stu-id="3f0f5-106">To create a group of controls</span></span>

1. <span data-ttu-id="3f0f5-107">将控件从 "工具箱" 的 "Windows 窗体" 选项卡拖到窗体上。 <xref:System.Windows.Forms.Panel></span><span class="sxs-lookup"><span data-stu-id="3f0f5-107">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>

2. <span data-ttu-id="3f0f5-108">将其他控件添加到面板, 在面板中绘制每个控件。</span><span class="sxs-lookup"><span data-stu-id="3f0f5-108">Add other controls to the panel, drawing each inside the panel.</span></span>

     <span data-ttu-id="3f0f5-109">如果要将现有控件置于面板中, 则可以选择所有控件, 将它们剪切到剪贴板, 选择<xref:System.Windows.Forms.Panel>控件, 然后将其粘贴到面板中。</span><span class="sxs-lookup"><span data-stu-id="3f0f5-109">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="3f0f5-110">还可以将其拖动到面板中。</span><span class="sxs-lookup"><span data-stu-id="3f0f5-110">You can also drag them into the panel.</span></span>

3. <span data-ttu-id="3f0f5-111">可有可无如果要向面板中添加边框, 请设置其<xref:System.Windows.Forms.BorderStyle>属性。</span><span class="sxs-lookup"><span data-stu-id="3f0f5-111">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="3f0f5-112">有三种选择: <xref:System.Windows.Forms.BorderStyle.Fixed3D>、 <xref:System.Windows.Forms.BorderStyle.FixedSingle>和<xref:System.Windows.Forms.BorderStyle.None>。</span><span class="sxs-lookup"><span data-stu-id="3f0f5-112">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f0f5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f0f5-113">See also</span></span>

- [<span data-ttu-id="3f0f5-114">Panel 控件</span><span class="sxs-lookup"><span data-stu-id="3f0f5-114">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="3f0f5-115">Panel 控件概述</span><span class="sxs-lookup"><span data-stu-id="3f0f5-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="3f0f5-116">如何：设置面板的背景</span><span class="sxs-lookup"><span data-stu-id="3f0f5-116">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)
