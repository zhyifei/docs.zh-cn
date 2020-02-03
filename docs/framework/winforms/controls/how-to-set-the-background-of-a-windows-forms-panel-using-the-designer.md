---
title: 使用设计器设置面板的背景
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731918"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="4798a-102">如何：使用设计器设置 Windows 窗体面板的背景</span><span class="sxs-lookup"><span data-stu-id="4798a-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="4798a-103">Windows 窗体 <xref:System.Windows.Forms.Panel> 控件可以同时显示背景色和背景图像。</span><span class="sxs-lookup"><span data-stu-id="4798a-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="4798a-104"><xref:System.Windows.Forms.Control.BackColor%2A> 属性为面板中包含的控件（如标签和单选按钮）设置背景色。</span><span class="sxs-lookup"><span data-stu-id="4798a-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="4798a-105">如果未设置 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性，则 <xref:System.Windows.Forms.Control.BackColor%2A> 选择将填充所有面板。</span><span class="sxs-lookup"><span data-stu-id="4798a-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="4798a-106">如果设置了 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性，则该图像将显示在面板中包含的控件后。</span><span class="sxs-lookup"><span data-stu-id="4798a-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="4798a-107">下面的过程需要一个**Windows 应用程序**项目，该项目具有包含 <xref:System.Windows.Forms.Panel> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="4798a-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="4798a-108">有关如何在 Visual Studio 中设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="4798a-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="4798a-109">在 Windows 窗体设计器中设置背景</span><span class="sxs-lookup"><span data-stu-id="4798a-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="4798a-110">在 Visual Studio 中打开项目，然后选择 "<xref:System.Windows.Forms.Panel>" 控件。</span><span class="sxs-lookup"><span data-stu-id="4798a-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="4798a-111">在 "**属性**" 窗口中，单击 "<xref:System.Windows.Forms.Control.BackColor%2A>" 属性旁边的箭头按钮以显示具有三个选项卡的窗口。</span><span class="sxs-lookup"><span data-stu-id="4798a-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="4798a-112">选择 "**自定义**" 选项卡以显示颜色调色板。</span><span class="sxs-lookup"><span data-stu-id="4798a-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="4798a-113">选择 " **Web** " 或 "**系统**" 选项卡以显示颜色的预定义名称列表，然后选择一种颜色。</span><span class="sxs-lookup"><span data-stu-id="4798a-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="4798a-114">在 "**属性**" 窗口中，单击 "<xref:System.Windows.Forms.Control.BackgroundImage%2A>" 属性旁边的箭头按钮。</span><span class="sxs-lookup"><span data-stu-id="4798a-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="4798a-115">在 "**打开**" 对话框中，选择要显示的文件。</span><span class="sxs-lookup"><span data-stu-id="4798a-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="4798a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4798a-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="4798a-117">Panel 控件</span><span class="sxs-lookup"><span data-stu-id="4798a-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="4798a-118">Panel 控件概述</span><span class="sxs-lookup"><span data-stu-id="4798a-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="4798a-119">如何：使用设计器用 Windows 窗体 Panel 控件对控件进行分组</span><span class="sxs-lookup"><span data-stu-id="4798a-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
