---
title: "演练：创建可访问的基于 Windows 的应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8f0a35b569b38e0d7ca79129f720034420ecd23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a><span data-ttu-id="65861-102">演练：创建可访问的基于 Windows 的应用程序</span><span class="sxs-lookup"><span data-stu-id="65861-102">Walkthrough: Creating an Accessible Windows-based Application</span></span>
<span data-ttu-id="65861-103">创建具有辅助功能的应用程序具有重要的商业意义。</span><span class="sxs-lookup"><span data-stu-id="65861-103">Creating an accessible application has important business implications.</span></span> <span data-ttu-id="65861-104">很多政府都有针对软件购买的辅助功能法规。</span><span class="sxs-lookup"><span data-stu-id="65861-104">Many governments have accessibility regulations for software purchase.</span></span> <span data-ttu-id="65861-105">Certified for Windows 徽标包括辅助功能需求。</span><span class="sxs-lookup"><span data-stu-id="65861-105">The Certified for Windows logo includes accessibility requirements.</span></span> <span data-ttu-id="65861-106">据估计，仅美国就有 3 千万居民（其中很多为潜在客户）受到软件辅助功能的影响。</span><span class="sxs-lookup"><span data-stu-id="65861-106">An estimated 30 million residents of the U.S. alone, many of them potential customers, are affected by the accessibility of software.</span></span>  
  
 <span data-ttu-id="65861-107">此演练将针对 Certified for Windows 徽标的 5 项辅助功能需求。</span><span class="sxs-lookup"><span data-stu-id="65861-107">This walkthrough will address the five accessibility requirements for the Certified for Windows logo.</span></span> <span data-ttu-id="65861-108">根据这些要求，具有辅助功能的应用程序将：</span><span class="sxs-lookup"><span data-stu-id="65861-108">According to these requirements, an accessible application will:</span></span>  
  
-   <span data-ttu-id="65861-109">支持控件面板大小、颜色、字体和输入设置。</span><span class="sxs-lookup"><span data-stu-id="65861-109">Support Control Panel size, color, font, and input settings.</span></span> <span data-ttu-id="65861-110">当用户更改控件面板设置时，菜单栏、标题栏、边框和状态栏都将调整大小。</span><span class="sxs-lookup"><span data-stu-id="65861-110">The menu bar, title bar, borders, and status bar will all resize themselves when the user changes the control panel settings.</span></span> <span data-ttu-id="65861-111">此应用程序中不需要对控件或代码进行任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="65861-111">No additional changes to the controls or code are required in this application.</span></span>  
  
-   <span data-ttu-id="65861-112">支持高对比度模式。</span><span class="sxs-lookup"><span data-stu-id="65861-112">Support High Contrast mode.</span></span>  
  
-   <span data-ttu-id="65861-113">提供对所有功能的已记录的键盘访问。</span><span class="sxs-lookup"><span data-stu-id="65861-113">Provide documented keyboard access to all features.</span></span>  
  
-   <span data-ttu-id="65861-114">以可视方式和以编程方式公开键盘焦点的位置。</span><span class="sxs-lookup"><span data-stu-id="65861-114">Expose location of the keyboard focus visually and programmatically.</span></span>  
  
-   <span data-ttu-id="65861-115">避免仅靠声音传达重要信息。</span><span class="sxs-lookup"><span data-stu-id="65861-115">Avoid conveying important information by sound alone.</span></span>  
  
 <span data-ttu-id="65861-116">有关详细信息，请参阅[用于设计支持辅助功能的应用程序的资源](/visualstudio/ide/reference/resources-for-designing-accessible-applications)。</span><span class="sxs-lookup"><span data-stu-id="65861-116">For more information, see [Resources for Designing Accessible Applications](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span></span>  
  
 <span data-ttu-id="65861-117">有关支持不同键盘布局的信息，请参阅[开发全球通用应用程序的最佳做法](../../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="65861-117">For information on supporting varying keyboard layouts, see [Best Practices for Developing World-Ready Applications](../../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="65861-118">创建项目</span><span class="sxs-lookup"><span data-stu-id="65861-118">Creating the Project</span></span>  
 <span data-ttu-id="65861-119">此演练为一个可接受比萨订单的应用程序创建用户界面。</span><span class="sxs-lookup"><span data-stu-id="65861-119">This walkthrough creates the user interface for an application that takes pizza orders.</span></span> <span data-ttu-id="65861-120">它包含以下内容：一个用于输入客户名称的 <xref:System.Windows.Forms.TextBox>一个用于选择比萨大小的 <xref:System.Windows.Forms.RadioButton> 组，一个用于选择浇头的 <xref:System.Windows.Forms.CheckedListBox>分别标记为“订购”和“取消”的两个 Button 控件，以及一个具有“退出”命令的“菜单”。</span><span class="sxs-lookup"><span data-stu-id="65861-120">It consists of a <xref:System.Windows.Forms.TextBox> for the customer's name, a <xref:System.Windows.Forms.RadioButton> group to select the pizza size, a <xref:System.Windows.Forms.CheckedListBox> for selecting the toppings, two Button controls labeled Order and Cancel, and a Menu with an Exit command.</span></span>  
  
 <span data-ttu-id="65861-121">用户输入客户名称、比萨大小和想要的浇头。</span><span class="sxs-lookup"><span data-stu-id="65861-121">The user enters the customer's name, the size of the pizza, and the toppings desired.</span></span> <span data-ttu-id="65861-122">当用户单击“订购”按钮时，将在消息框中显示订单一览表及其价格，然后将控件清除并为下个订单做好准备。</span><span class="sxs-lookup"><span data-stu-id="65861-122">When the user clicks the Order button, a summary of the order and its cost are displayed in a message box and the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="65861-123">当用户单击“取消”按钮时，将控件清除并为下个订单做好准备。</span><span class="sxs-lookup"><span data-stu-id="65861-123">When the user clicks the Cancel button, the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="65861-124">当用户单击“退出”菜单项时，程序关闭。</span><span class="sxs-lookup"><span data-stu-id="65861-124">When the user clicks the Exit menu item, the program closes.</span></span>  
  
 <span data-ttu-id="65861-125">本演练的重点不是零售订单系统的代码，而是用户界面的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="65861-125">The emphasis of this walkthrough is not the code for a retail order system, but the accessibility of the user interface.</span></span> <span data-ttu-id="65861-126">本演练说明几个常用控件（包括按钮、单选按钮、文本框和标签）的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="65861-126">The walkthrough demonstrates the accessibility features of several frequently used controls, including buttons, radio buttons, text boxes, and labels.</span></span>  
  
#### <a name="to-begin-making-the-application"></a><span data-ttu-id="65861-127">开始生成应用程序</span><span class="sxs-lookup"><span data-stu-id="65861-127">To begin making the application</span></span>  
  
-   <span data-ttu-id="65861-128">在 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 中创建新的 Windows 应用程序。</span><span class="sxs-lookup"><span data-stu-id="65861-128">Create a new Windows Application in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="65861-129">将项目命名为 **PizzaOrder**。</span><span class="sxs-lookup"><span data-stu-id="65861-129">Name the project **PizzaOrder**.</span></span> <span data-ttu-id="65861-130">（有关详细信息，请参阅[创建新解决方案和项目](/visualstudio/ide/creating-solutions-and-projects)。）</span><span class="sxs-lookup"><span data-stu-id="65861-130">(For details see [Creating New Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).)</span></span>  
  
## <a name="adding-the-controls-to-the-form"></a><span data-ttu-id="65861-131">将控件添加到窗体</span><span class="sxs-lookup"><span data-stu-id="65861-131">Adding the Controls to the Form</span></span>  
 <span data-ttu-id="65861-132">将控件添加到窗体时，请牢记以下指南以生成具有辅助功能的应用程序：</span><span class="sxs-lookup"><span data-stu-id="65861-132">When adding the controls to a form, keep in mind the following guidelines to make an accessible application:</span></span>  
  
-   <span data-ttu-id="65861-133">设置 <xref:System.Windows.Forms.Control.AccessibleDescription%2A> 和 <xref:System.Windows.Forms.Control.AccessibleName%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="65861-133">Set the <xref:System.Windows.Forms.Control.AccessibleDescription%2A> and <xref:System.Windows.Forms.Control.AccessibleName%2A> properties.</span></span> <span data-ttu-id="65861-134">在此示例中，<xref:System.Windows.Forms.Control.AccessibleRole%2A> 的默认设置已经足够。</span><span class="sxs-lookup"><span data-stu-id="65861-134">In this example, the Default setting for the <xref:System.Windows.Forms.Control.AccessibleRole%2A> is sufficient.</span></span> <span data-ttu-id="65861-135">有关辅助功能属性的详细信息，请参阅[为 Windows 窗体上的控件提供辅助功能信息](../../../../docs/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form.md)。</span><span class="sxs-lookup"><span data-stu-id="65861-135">For more information on the accessibility properties, see [Providing Accessibility Information for Controls on a Windows Form](../../../../docs/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span></span>  
  
-   <span data-ttu-id="65861-136">将字体大小设置为 10 号或更大。</span><span class="sxs-lookup"><span data-stu-id="65861-136">Set the font size to 10 points or larger.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65861-137">如果在启动时将窗体的字体大小设置为 10，则随后添加到窗体的所有控件的字体大小均为 10。</span><span class="sxs-lookup"><span data-stu-id="65861-137">If you set the font size of the form to 10 when you start, then all controls subsequently added to the form will have a font size of 10.</span></span>  
  
-   <span data-ttu-id="65861-138">确保任何描述 TextBox 控件的 Label 控件均按 Tab 顺序紧排在相应的 TextBox 控件之前。</span><span class="sxs-lookup"><span data-stu-id="65861-138">Make sure any Label control that describes a TextBox control immediately precedes the TextBox control in the tab order.</span></span>  
  
-   <span data-ttu-id="65861-139">使用“&”字符将访问键添加到用户可能想要导航到的任何控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="65861-139">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of any control the user may want to navigate to.</span></span>  
  
-   <span data-ttu-id="65861-140">使用“&”字符将访问键添加到标签的 <xref:System.Windows.Forms.Control.Text%2A> 属性，此标签位于用户可能想要导航到的控件之前。</span><span class="sxs-lookup"><span data-stu-id="65861-140">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of the label that precedes a control that the user may want to navigate to.</span></span> <span data-ttu-id="65861-141">将标签的 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 属性设置为 `true`，以便在用户按下访问键时将焦点设置到按 Tab 键顺序的下一控件。</span><span class="sxs-lookup"><span data-stu-id="65861-141">Set the labels' <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`, so that the focus is set to the next control in the tab order when the user presses the access key.</span></span>  
  
-   <span data-ttu-id="65861-142">将访问键添加到所有菜单项。</span><span class="sxs-lookup"><span data-stu-id="65861-142">Add access keys to all menu items.</span></span>  
  
#### <a name="to-make-your-windows-application-accessible"></a><span data-ttu-id="65861-143">使 Windows 应用程序具有辅助功能</span><span class="sxs-lookup"><span data-stu-id="65861-143">To make your Windows Application accessible</span></span>  
  
-   <span data-ttu-id="65861-144">将控件添加到窗体并如下所述设置属性。</span><span class="sxs-lookup"><span data-stu-id="65861-144">Add the controls to the form and set the properties as described below.</span></span> <span data-ttu-id="65861-145">有关如何在窗体上排列控件的模型，请查看表结尾处的图片。</span><span class="sxs-lookup"><span data-stu-id="65861-145">See the picture at the end of the table for a model of how to arrange the controls on the form.</span></span>  
  
    |<span data-ttu-id="65861-146">对象</span><span class="sxs-lookup"><span data-stu-id="65861-146">Object</span></span>|<span data-ttu-id="65861-147">属性</span><span class="sxs-lookup"><span data-stu-id="65861-147">Property</span></span>|<span data-ttu-id="65861-148">值</span><span class="sxs-lookup"><span data-stu-id="65861-148">Value</span></span>|  
    |------------|--------------|-----------|  
    |<span data-ttu-id="65861-149">Form1</span><span class="sxs-lookup"><span data-stu-id="65861-149">Form1</span></span>|<span data-ttu-id="65861-150">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-150">AccessibleDescription</span></span>|<span data-ttu-id="65861-151">订购窗体</span><span class="sxs-lookup"><span data-stu-id="65861-151">Order form</span></span>|  
    ||<span data-ttu-id="65861-152">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-152">AccessibleName</span></span>|<span data-ttu-id="65861-153">订购窗体</span><span class="sxs-lookup"><span data-stu-id="65861-153">Order form</span></span>|  
    ||<span data-ttu-id="65861-154">字号</span><span class="sxs-lookup"><span data-stu-id="65861-154">Font Size</span></span>|<span data-ttu-id="65861-155">10</span><span class="sxs-lookup"><span data-stu-id="65861-155">10</span></span>|  
    ||<span data-ttu-id="65861-156">Text</span><span class="sxs-lookup"><span data-stu-id="65861-156">Text</span></span>|<span data-ttu-id="65861-157">比萨饼订购窗体</span><span class="sxs-lookup"><span data-stu-id="65861-157">Pizza Order Form</span></span>|  
    |<span data-ttu-id="65861-158">PictureBox</span><span class="sxs-lookup"><span data-stu-id="65861-158">PictureBox</span></span>|<span data-ttu-id="65861-159">名称</span><span class="sxs-lookup"><span data-stu-id="65861-159">Name</span></span>|<span data-ttu-id="65861-160">徽标</span><span class="sxs-lookup"><span data-stu-id="65861-160">logo</span></span>|  
    ||<span data-ttu-id="65861-161">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-161">AccessibleDescription</span></span>|<span data-ttu-id="65861-162">一片比萨饼</span><span class="sxs-lookup"><span data-stu-id="65861-162">A slice of pizza</span></span>|  
    ||<span data-ttu-id="65861-163">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-163">AccessibleName</span></span>|<span data-ttu-id="65861-164">公司徽标</span><span class="sxs-lookup"><span data-stu-id="65861-164">Company logo</span></span>|  
    ||<span data-ttu-id="65861-165">Image</span><span class="sxs-lookup"><span data-stu-id="65861-165">Image</span></span>|<span data-ttu-id="65861-166">任何图标或位图</span><span class="sxs-lookup"><span data-stu-id="65861-166">Any icon or bitmap</span></span>|  
    |<span data-ttu-id="65861-167">Label</span><span class="sxs-lookup"><span data-stu-id="65861-167">Label</span></span>|<span data-ttu-id="65861-168">名称</span><span class="sxs-lookup"><span data-stu-id="65861-168">Name</span></span>|<span data-ttu-id="65861-169">companyLabel</span><span class="sxs-lookup"><span data-stu-id="65861-169">companyLabel</span></span>|  
    ||<span data-ttu-id="65861-170">Text</span><span class="sxs-lookup"><span data-stu-id="65861-170">Text</span></span>|<span data-ttu-id="65861-171">美味比萨</span><span class="sxs-lookup"><span data-stu-id="65861-171">Good Pizza</span></span>|  
    ||<span data-ttu-id="65861-172">TabIndex</span><span class="sxs-lookup"><span data-stu-id="65861-172">TabIndex</span></span>|<span data-ttu-id="65861-173">1</span><span class="sxs-lookup"><span data-stu-id="65861-173">1</span></span>|  
    ||<span data-ttu-id="65861-174">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-174">AccessibleDescription</span></span>|<span data-ttu-id="65861-175">公司名称</span><span class="sxs-lookup"><span data-stu-id="65861-175">Company name</span></span>|  
    ||<span data-ttu-id="65861-176">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-176">AccessibleName</span></span>|<span data-ttu-id="65861-177">公司名称</span><span class="sxs-lookup"><span data-stu-id="65861-177">Company name</span></span>|  
    ||<span data-ttu-id="65861-178">背景色</span><span class="sxs-lookup"><span data-stu-id="65861-178">Backcolor</span></span>|<span data-ttu-id="65861-179">蓝色</span><span class="sxs-lookup"><span data-stu-id="65861-179">Blue</span></span>|  
    ||<span data-ttu-id="65861-180">前景色</span><span class="sxs-lookup"><span data-stu-id="65861-180">Forecolor</span></span>|<span data-ttu-id="65861-181">黄色</span><span class="sxs-lookup"><span data-stu-id="65861-181">Yellow</span></span>|  
    ||<span data-ttu-id="65861-182">字体大小</span><span class="sxs-lookup"><span data-stu-id="65861-182">Font size</span></span>|<span data-ttu-id="65861-183">18</span><span class="sxs-lookup"><span data-stu-id="65861-183">18</span></span>|  
    |<span data-ttu-id="65861-184">Label</span><span class="sxs-lookup"><span data-stu-id="65861-184">Label</span></span>|<span data-ttu-id="65861-185">名称</span><span class="sxs-lookup"><span data-stu-id="65861-185">Name</span></span>|<span data-ttu-id="65861-186">customerLabel</span><span class="sxs-lookup"><span data-stu-id="65861-186">customerLabel</span></span>|  
    ||<span data-ttu-id="65861-187">Text</span><span class="sxs-lookup"><span data-stu-id="65861-187">Text</span></span>|<span data-ttu-id="65861-188">名称(&N)</span><span class="sxs-lookup"><span data-stu-id="65861-188">&Name</span></span>|  
    ||<span data-ttu-id="65861-189">TabIndex</span><span class="sxs-lookup"><span data-stu-id="65861-189">TabIndex</span></span>|<span data-ttu-id="65861-190">2</span><span class="sxs-lookup"><span data-stu-id="65861-190">2</span></span>|  
    ||<span data-ttu-id="65861-191">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-191">AccessibleDescription</span></span>|<span data-ttu-id="65861-192">客户名称标签</span><span class="sxs-lookup"><span data-stu-id="65861-192">Customer name label</span></span>|  
    ||<span data-ttu-id="65861-193">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-193">AccessibleName</span></span>|<span data-ttu-id="65861-194">客户名称标签</span><span class="sxs-lookup"><span data-stu-id="65861-194">Customer name label</span></span>|  
    ||<span data-ttu-id="65861-195">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="65861-195">UseMnemonic</span></span>|<span data-ttu-id="65861-196">True</span><span class="sxs-lookup"><span data-stu-id="65861-196">True</span></span>|  
    |<span data-ttu-id="65861-197">文本框</span><span class="sxs-lookup"><span data-stu-id="65861-197">TextBox</span></span>|<span data-ttu-id="65861-198">名称</span><span class="sxs-lookup"><span data-stu-id="65861-198">Name</span></span>|<span data-ttu-id="65861-199">CustomerName</span><span class="sxs-lookup"><span data-stu-id="65861-199">customerName</span></span>|  
    ||<span data-ttu-id="65861-200">Text</span><span class="sxs-lookup"><span data-stu-id="65861-200">Text</span></span>|<span data-ttu-id="65861-201">(无)</span><span class="sxs-lookup"><span data-stu-id="65861-201">(none)</span></span>|  
    ||<span data-ttu-id="65861-202">TabIndex</span><span class="sxs-lookup"><span data-stu-id="65861-202">TabIndex</span></span>|<span data-ttu-id="65861-203">3</span><span class="sxs-lookup"><span data-stu-id="65861-203">3</span></span>|  
    ||<span data-ttu-id="65861-204">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-204">AccessibleDescription</span></span>|<span data-ttu-id="65861-205">CustomerName</span><span class="sxs-lookup"><span data-stu-id="65861-205">Customer name</span></span>|  
    ||<span data-ttu-id="65861-206">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-206">AccessibleName</span></span>|<span data-ttu-id="65861-207">CustomerName</span><span class="sxs-lookup"><span data-stu-id="65861-207">Customer name</span></span>|  
    |<span data-ttu-id="65861-208">GroupBox</span><span class="sxs-lookup"><span data-stu-id="65861-208">GroupBox</span></span>|<span data-ttu-id="65861-209">名称</span><span class="sxs-lookup"><span data-stu-id="65861-209">Name</span></span>|<span data-ttu-id="65861-210">sizeOptions</span><span class="sxs-lookup"><span data-stu-id="65861-210">sizeOptions</span></span>|  
    ||<span data-ttu-id="65861-211">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-211">AccessibleDescription</span></span>|<span data-ttu-id="65861-212">比萨大小选项</span><span class="sxs-lookup"><span data-stu-id="65861-212">Pizza size options</span></span>|  
    ||<span data-ttu-id="65861-213">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-213">AccessibleName</span></span>|<span data-ttu-id="65861-214">比萨大小选项</span><span class="sxs-lookup"><span data-stu-id="65861-214">Pizza size options</span></span>|  
    ||<span data-ttu-id="65861-215">Text</span><span class="sxs-lookup"><span data-stu-id="65861-215">Text</span></span>|<span data-ttu-id="65861-216">比萨大小</span><span class="sxs-lookup"><span data-stu-id="65861-216">Pizza size</span></span>|  
    ||<span data-ttu-id="65861-217">TabIndex</span><span class="sxs-lookup"><span data-stu-id="65861-217">TabIndex</span></span>|<span data-ttu-id="65861-218">4</span><span class="sxs-lookup"><span data-stu-id="65861-218">4</span></span>|  
    |<span data-ttu-id="65861-219">RadioButton</span><span class="sxs-lookup"><span data-stu-id="65861-219">RadioButton</span></span>|<span data-ttu-id="65861-220">名称</span><span class="sxs-lookup"><span data-stu-id="65861-220">Name</span></span>|<span data-ttu-id="65861-221">smallPizza</span><span class="sxs-lookup"><span data-stu-id="65861-221">smallPizza</span></span>|  
    ||<span data-ttu-id="65861-222">Text</span><span class="sxs-lookup"><span data-stu-id="65861-222">Text</span></span>|<span data-ttu-id="65861-223">小号 $6.00 (&S)</span><span class="sxs-lookup"><span data-stu-id="65861-223">&Small $6.00</span></span>|  
    ||<span data-ttu-id="65861-224">已选中</span><span class="sxs-lookup"><span data-stu-id="65861-224">Checked</span></span>|<span data-ttu-id="65861-225">True</span><span class="sxs-lookup"><span data-stu-id="65861-225">True</span></span>|  
    ||<span data-ttu-id="65861-226">TabIndex</span><span class="sxs-lookup"><span data-stu-id="65861-226">TabIndex</span></span>|<span data-ttu-id="65861-227">0</span><span class="sxs-lookup"><span data-stu-id="65861-227">0</span></span>|  
    ||<span data-ttu-id="65861-228">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-228">AccessibleDescription</span></span>|<span data-ttu-id="65861-229">小号比萨</span><span class="sxs-lookup"><span data-stu-id="65861-229">Small pizza</span></span>|  
    ||<span data-ttu-id="65861-230">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-230">AccessibleName</span></span>|<span data-ttu-id="65861-231">小号比萨</span><span class="sxs-lookup"><span data-stu-id="65861-231">Small pizza</span></span>|  
    |<span data-ttu-id="65861-232">RadioButton</span><span class="sxs-lookup"><span data-stu-id="65861-232">RadioButton</span></span>|<span data-ttu-id="65861-233">名称</span><span class="sxs-lookup"><span data-stu-id="65861-233">Name</span></span>|<span data-ttu-id="65861-234">largePizza</span><span class="sxs-lookup"><span data-stu-id="65861-234">largePizza</span></span>|  
    ||<span data-ttu-id="65861-235">Text</span><span class="sxs-lookup"><span data-stu-id="65861-235">Text</span></span>|<span data-ttu-id="65861-236">大号 $10.00 (&L)</span><span class="sxs-lookup"><span data-stu-id="65861-236">&Large $10.00</span></span>|  
    ||<span data-ttu-id="65861-237">TabIndex</span><span class="sxs-lookup"><span data-stu-id="65861-237">TabIndex</span></span>|<span data-ttu-id="65861-238">1</span><span class="sxs-lookup"><span data-stu-id="65861-238">1</span></span>|  
    ||<span data-ttu-id="65861-239">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-239">AccessibleDescription</span></span>|<span data-ttu-id="65861-240">大号披萨</span><span class="sxs-lookup"><span data-stu-id="65861-240">Large pizza</span></span>|  
    ||<span data-ttu-id="65861-241">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-241">AccessibleName</span></span>|<span data-ttu-id="65861-242">大号披萨</span><span class="sxs-lookup"><span data-stu-id="65861-242">Large pizza</span></span>|  
    |<span data-ttu-id="65861-243">Label</span><span class="sxs-lookup"><span data-stu-id="65861-243">Label</span></span>|<span data-ttu-id="65861-244">名称</span><span class="sxs-lookup"><span data-stu-id="65861-244">Name</span></span>|<span data-ttu-id="65861-245">toppingsLabel</span><span class="sxs-lookup"><span data-stu-id="65861-245">toppingsLabel</span></span>|  
    ||<span data-ttu-id="65861-246">Text</span><span class="sxs-lookup"><span data-stu-id="65861-246">Text</span></span>|<span data-ttu-id="65861-247">浇头(每个$0.75)(&T)</span><span class="sxs-lookup"><span data-stu-id="65861-247">&Toppings ($0.75 each)</span></span>|  
    ||<span data-ttu-id="65861-248">TabIndex</span><span class="sxs-lookup"><span data-stu-id="65861-248">TabIndex</span></span>|<span data-ttu-id="65861-249">5</span><span class="sxs-lookup"><span data-stu-id="65861-249">5</span></span>|  
    ||<span data-ttu-id="65861-250">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-250">AccessibleDescription</span></span>|<span data-ttu-id="65861-251">浇头标签</span><span class="sxs-lookup"><span data-stu-id="65861-251">Toppings label</span></span>|  
    ||<span data-ttu-id="65861-252">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-252">AccessibleName</span></span>|<span data-ttu-id="65861-253">浇头标签</span><span class="sxs-lookup"><span data-stu-id="65861-253">Toppings label</span></span>|  
    ||<span data-ttu-id="65861-254">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="65861-254">UseMnemonic</span></span>|<span data-ttu-id="65861-255">True</span><span class="sxs-lookup"><span data-stu-id="65861-255">True</span></span>|  
    |<span data-ttu-id="65861-256">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="65861-256">CheckedListBox</span></span>|<span data-ttu-id="65861-257">名称</span><span class="sxs-lookup"><span data-stu-id="65861-257">Name</span></span>|<span data-ttu-id="65861-258">浇头</span><span class="sxs-lookup"><span data-stu-id="65861-258">toppings</span></span>|  
    ||<span data-ttu-id="65861-259">TabIndex</span><span class="sxs-lookup"><span data-stu-id="65861-259">TabIndex</span></span>|<span data-ttu-id="65861-260">6</span><span class="sxs-lookup"><span data-stu-id="65861-260">6</span></span>|  
    ||<span data-ttu-id="65861-261">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-261">AccessibleDescription</span></span>|<span data-ttu-id="65861-262">可用浇头</span><span class="sxs-lookup"><span data-stu-id="65861-262">Available toppings</span></span>|  
    ||<span data-ttu-id="65861-263">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-263">AccessibleName</span></span>|<span data-ttu-id="65861-264">可用浇头</span><span class="sxs-lookup"><span data-stu-id="65861-264">Available toppings</span></span>|  
    ||<span data-ttu-id="65861-265">项</span><span class="sxs-lookup"><span data-stu-id="65861-265">Items</span></span>|<span data-ttu-id="65861-266">意大利辣肠、香肠、蘑菇</span><span class="sxs-lookup"><span data-stu-id="65861-266">Pepperoni, Sausage, Mushrooms</span></span>|  
    |<span data-ttu-id="65861-267">Button</span><span class="sxs-lookup"><span data-stu-id="65861-267">Button</span></span>|<span data-ttu-id="65861-268">名称</span><span class="sxs-lookup"><span data-stu-id="65861-268">Name</span></span>|<span data-ttu-id="65861-269">顺序</span><span class="sxs-lookup"><span data-stu-id="65861-269">order</span></span>|  
    ||<span data-ttu-id="65861-270">Text</span><span class="sxs-lookup"><span data-stu-id="65861-270">Text</span></span>|<span data-ttu-id="65861-271">顺序(&O)</span><span class="sxs-lookup"><span data-stu-id="65861-271">&Order</span></span>|  
    ||<span data-ttu-id="65861-272">TabIndex</span><span class="sxs-lookup"><span data-stu-id="65861-272">TabIndex</span></span>|<span data-ttu-id="65861-273">7</span><span class="sxs-lookup"><span data-stu-id="65861-273">7</span></span>|  
    ||<span data-ttu-id="65861-274">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-274">AccessibleDescription</span></span>|<span data-ttu-id="65861-275">订单合计</span><span class="sxs-lookup"><span data-stu-id="65861-275">Total the order</span></span>|  
    ||<span data-ttu-id="65861-276">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-276">AccessibleName</span></span>|<span data-ttu-id="65861-277">总订单</span><span class="sxs-lookup"><span data-stu-id="65861-277">Total order</span></span>|  
    |<span data-ttu-id="65861-278">Button</span><span class="sxs-lookup"><span data-stu-id="65861-278">Button</span></span>|<span data-ttu-id="65861-279">名称</span><span class="sxs-lookup"><span data-stu-id="65861-279">Name</span></span>|<span data-ttu-id="65861-280">cancel</span><span class="sxs-lookup"><span data-stu-id="65861-280">cancel</span></span>|  
    ||<span data-ttu-id="65861-281">Text</span><span class="sxs-lookup"><span data-stu-id="65861-281">Text</span></span>|<span data-ttu-id="65861-282">取消(&C)</span><span class="sxs-lookup"><span data-stu-id="65861-282">&Cancel</span></span>|  
    ||<span data-ttu-id="65861-283">TabIndex</span><span class="sxs-lookup"><span data-stu-id="65861-283">TabIndex</span></span>|<span data-ttu-id="65861-284">8</span><span class="sxs-lookup"><span data-stu-id="65861-284">8</span></span>|  
    ||<span data-ttu-id="65861-285">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="65861-285">AccessibleDescription</span></span>|<span data-ttu-id="65861-286">取消订单</span><span class="sxs-lookup"><span data-stu-id="65861-286">Cancel the order</span></span>|  
    ||<span data-ttu-id="65861-287">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="65861-287">AccessibleName</span></span>|<span data-ttu-id="65861-288">取消订单</span><span class="sxs-lookup"><span data-stu-id="65861-288">Cancel order</span></span>|  
    |<span data-ttu-id="65861-289">MainMenu</span><span class="sxs-lookup"><span data-stu-id="65861-289">MainMenu</span></span>|<span data-ttu-id="65861-290">名称</span><span class="sxs-lookup"><span data-stu-id="65861-290">Name</span></span>|<span data-ttu-id="65861-291">theMainMenu</span><span class="sxs-lookup"><span data-stu-id="65861-291">theMainMenu</span></span>|  
    |<span data-ttu-id="65861-292">MenuItem</span><span class="sxs-lookup"><span data-stu-id="65861-292">MenuItem</span></span>|<span data-ttu-id="65861-293">名称</span><span class="sxs-lookup"><span data-stu-id="65861-293">Name</span></span>|<span data-ttu-id="65861-294">fileCommands</span><span class="sxs-lookup"><span data-stu-id="65861-294">fileCommands</span></span>|  
    ||<span data-ttu-id="65861-295">Text</span><span class="sxs-lookup"><span data-stu-id="65861-295">Text</span></span>|<span data-ttu-id="65861-296">文件(&F)</span><span class="sxs-lookup"><span data-stu-id="65861-296">&File</span></span>|  
    |<span data-ttu-id="65861-297">MenuItem</span><span class="sxs-lookup"><span data-stu-id="65861-297">MenuItem</span></span>|<span data-ttu-id="65861-298">名称</span><span class="sxs-lookup"><span data-stu-id="65861-298">Name</span></span>|<span data-ttu-id="65861-299">exitApp</span><span class="sxs-lookup"><span data-stu-id="65861-299">exitApp</span></span>|  
    ||<span data-ttu-id="65861-300">Text</span><span class="sxs-lookup"><span data-stu-id="65861-300">Text</span></span>|<span data-ttu-id="65861-301">退出(&X)</span><span class="sxs-lookup"><span data-stu-id="65861-301">E&xit</span></span>|  
  
     <span data-ttu-id="65861-302">![比萨饼订购窗体](../../../../docs/framework/winforms/advanced/media/vbpizzaorderform.gif "vbPizzaOrderForm")</span><span class="sxs-lookup"><span data-stu-id="65861-302">![Pizza Order Form](../../../../docs/framework/winforms/advanced/media/vbpizzaorderform.gif "vbPizzaOrderForm")</span></span>  
<span data-ttu-id="65861-303">窗体外观将类似于：</span><span class="sxs-lookup"><span data-stu-id="65861-303">Your form will look something like the following:</span></span>  
  
## <a name="supporting-high-contrast-mode"></a><span data-ttu-id="65861-304">支持高对比度模式</span><span class="sxs-lookup"><span data-stu-id="65861-304">Supporting High Contrast Mode</span></span>  
 <span data-ttu-id="65861-305">高对比度模式是一种 Windows 系统设置，它通过使用有益于视力受损用户的对比颜色和字体大小提高可读性。</span><span class="sxs-lookup"><span data-stu-id="65861-305">High Contrast mode is a Windows system setting that improves readability by using contrasting colors and font sizes that are beneficial for visually impaired users.</span></span> <span data-ttu-id="65861-306"><xref:System.Windows.Forms.SystemInformation.HighContrast%2A>提供属性以确定是否设置高对比度模式。</span><span class="sxs-lookup"><span data-stu-id="65861-306">The <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> property is provided to determine whether the High Contrast mode is set.</span></span>  
  
 <span data-ttu-id="65861-307">如果 SystemInformation.HighContrast 为`true`，则应用程序应：</span><span class="sxs-lookup"><span data-stu-id="65861-307">If SystemInformation.HighContrast is `true`, the application should:</span></span>  
  
-   <span data-ttu-id="65861-308">显示使用系统配色方案的所有用户界面元素</span><span class="sxs-lookup"><span data-stu-id="65861-308">Display all user interface elements using the system color scheme</span></span>  
  
-   <span data-ttu-id="65861-309">通过可视提示或声音传递任何通过颜色传递的信息。</span><span class="sxs-lookup"><span data-stu-id="65861-309">Convey by visual cues or sound any information that is conveyed through color.</span></span> <span data-ttu-id="65861-310">例如，如果特定列表项使用红色字体突出显示，则还可为字体加粗，以便用户得到突出显示项的非颜色提示。</span><span class="sxs-lookup"><span data-stu-id="65861-310">For example, if particular list items are highlighted by using a red font, you could also add bold to the font, so that the user has a non-color cue that the items are highlighted.</span></span>  
  
-   <span data-ttu-id="65861-311">忽略文本之后的任何图像或图案</span><span class="sxs-lookup"><span data-stu-id="65861-311">Omit any images or patterns behind text</span></span>  
  
 <span data-ttu-id="65861-312">应用程序应在启动时检查 <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> 的设置，并响应系统事件 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>。</span><span class="sxs-lookup"><span data-stu-id="65861-312">The application should check the setting of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> when the application starts and respond to the system event <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span></span> <span data-ttu-id="65861-313">每当 <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> 的值更改时，都会引发 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="65861-313">The <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event is raised whenever the value of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> changes.</span></span>  
  
 <span data-ttu-id="65861-314">在本应用程序中，未使用系统颜色设置的唯一元素是 `lblCompanyName`。</span><span class="sxs-lookup"><span data-stu-id="65861-314">In our application, the only element that is not using the system settings for color is `lblCompanyName`.</span></span> <span data-ttu-id="65861-315"><xref:System.Drawing.SystemColors>类用于将标签的颜色设置更改为用户选择的系统颜色。</span><span class="sxs-lookup"><span data-stu-id="65861-315">The <xref:System.Drawing.SystemColors> class is used to change the color settings of the label to the user-selected system colors.</span></span>  
  
#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a><span data-ttu-id="65861-316">有效地启用高对比度模式</span><span class="sxs-lookup"><span data-stu-id="65861-316">To enable High Contrast mode in an effective way</span></span>  
  
1.  <span data-ttu-id="65861-317">创建一种方法将标签颜色设置为系统颜色。</span><span class="sxs-lookup"><span data-stu-id="65861-317">Create a method to set the colors of the label to the system colors.</span></span>  
  
    ```  
    ' Visual Basic  
    Private Sub SetColorScheme()  
       If SystemInformation.HighContrast Then  
          companyLabel.BackColor = SystemColors.Window  
          companyLabel.ForeColor = SystemColors.WindowText  
       Else  
          companyLabel.BackColor = Color.Blue  
          companyLabel.ForeColor = Color.Yellow  
       End If  
    End Sub  
  
    // C#  
    private void SetColorScheme()  
    {  
       if (SystemInformation.HighContrast)  
       {  
          companyLabel.BackColor = SystemColors.Window;  
          companyLabel.ForeColor = SystemColors.WindowText;  
       }  
       else  
       {  
          companyLabel.BackColor = Color.Blue;  
          companyLabel.ForeColor = Color.Yellow;  
       }  
    }  
    ```  
  
2.  <span data-ttu-id="65861-318">在窗体构造函数（Visual Basic 中为 `Public Sub New()`，Visual C# 中为 `public class Form1`）调用 `SetColorScheme` 过程。</span><span class="sxs-lookup"><span data-stu-id="65861-318">Call the `SetColorScheme` procedure in the form constructor (`Public Sub New()` in Visual Basic and `public class Form1` in Visual C#).</span></span> <span data-ttu-id="65861-319">若要访问 Visual Basic 中的构造函数，需要展开标记了“Windows 窗体设计器生成的代码”的区域。</span><span class="sxs-lookup"><span data-stu-id="65861-319">To access the constructor in Visual Basic, you will need to expand the region labeled **Windows Form Designer generated code**.</span></span>  
  
    ```  
    ' Visual Basic   
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
    }  
    ```  
  
3.  <span data-ttu-id="65861-320">使用适当签名创建事件过程，以响应 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="65861-320">Create an event procedure, with the appropriate signature, to respond to the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Sub UserPreferenceChanged(ByVal sender As Object, _  
    ByVal e As Microsoft.Win32.UserPreferenceChangedEventArgs)  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public void UserPreferenceChanged(object sender,   
    Microsoft.Win32.UserPreferenceChangedEventArgs e)  
    {  
       SetColorScheme();  
    }  
    ```  
  
4.  <span data-ttu-id="65861-321">在调用 `InitializeComponents` 后将代码添加到窗体构造函数，以便将事件过程挂钩到系统事件。</span><span class="sxs-lookup"><span data-stu-id="65861-321">Add code to the form constructor, after the call to `InitializeComponents`, to hook up the event procedure to the system event.</span></span> <span data-ttu-id="65861-322">此方法调用 `SetColorScheme` 过程。</span><span class="sxs-lookup"><span data-stu-id="65861-322">This method calls the `SetColorScheme` procedure.</span></span>  
  
    ```  
    ' Visual Basic  
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
       AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          += new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
    }  
    ```  
  
5.  <span data-ttu-id="65861-323">在调用基类的 <xref:System.Windows.Forms.Control.Dispose%2A> 方法之前将代码添加到窗体 <xref:System.Windows.Forms.Control.Dispose%2A> 方法，以便在应用程序关闭时释放事件。</span><span class="sxs-lookup"><span data-stu-id="65861-323">Add code to the form <xref:System.Windows.Forms.Control.Dispose%2A> method, before the call to the <xref:System.Windows.Forms.Control.Dispose%2A> method of the base class, to release the event when the application closes.</span></span> <span data-ttu-id="65861-324">若要访问 Visual Basic 中的 <xref:System.Windows.Forms.Control.Dispose%2A> 方法，需要展开标记为“Windows 窗体设计器生成的代码”区域。</span><span class="sxs-lookup"><span data-stu-id="65861-324">To access the <xref:System.Windows.Forms.Control.Dispose%2A> method in Visual Basic, you will need to expand the region labeled Windows Form Designer generated code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65861-325">系统事件代码运行独立于主应用程序的线程。</span><span class="sxs-lookup"><span data-stu-id="65861-325">The system event code runs a thread separate from the main application.</span></span> <span data-ttu-id="65861-326">如果不释放事件，挂钩到事件的代码在程序关闭后仍将运行。</span><span class="sxs-lookup"><span data-stu-id="65861-326">If you do not release the event, the code that you hook up to the event will run even after the program is closed.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)  
       If disposing Then  
          If Not (components Is Nothing) Then  
             components.Dispose()  
          End If  
       End If  
       RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
       MyBase.Dispose(disposing)  
    End Sub  
  
    // C#  
    protected override void Dispose( bool disposing )  
    {  
       if( disposing )  
       {  
          if (components != null)   
          {  
             components.Dispose();  
          }  
       }  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          -= new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
       base.Dispose( disposing );  
    }  
    ```  
  
6.  <span data-ttu-id="65861-327">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="65861-327">Press F5 to run the application.</span></span>  
  
## <a name="conveying-important-information-by-means-other-than-sound"></a><span data-ttu-id="65861-328">通过非声音方式传达重要信息</span><span class="sxs-lookup"><span data-stu-id="65861-328">Conveying Important Information by Means Other Than Sound</span></span>  
 <span data-ttu-id="65861-329">在此应用程序中，没有信息是仅靠声音传达的。</span><span class="sxs-lookup"><span data-stu-id="65861-329">In this application, no information is conveyed by sound alone.</span></span> <span data-ttu-id="65861-330">如果在应用程序中使用声音，则还应通过其他一些方式提供信息。</span><span class="sxs-lookup"><span data-stu-id="65861-330">If you use sound in your application, then you should supply the information by some other means as well.</span></span>  
  
#### <a name="to-supply-information-by-some-other-means-than-sound"></a><span data-ttu-id="65861-331">以声音以外的其他方式提供信息</span><span class="sxs-lookup"><span data-stu-id="65861-331">To supply information by some other means than sound</span></span>  
  
1.  <span data-ttu-id="65861-332">使用 Windows API 函数 FlashWindow 使标题栏闪烁。</span><span class="sxs-lookup"><span data-stu-id="65861-332">Make the title bar flash by using the Windows API function FlashWindow.</span></span> <span data-ttu-id="65861-333">有关如何调用 Windows API 函数的示例，请参阅[演练：调用 Windows API](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)。</span><span class="sxs-lookup"><span data-stu-id="65861-333">For an example of how to call Windows API functions, see [Walkthrough: Calling Windows APIs](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65861-334">用户可能已启用 Windows SoundSentry 服务，它也会在系统声音通过计算机内置扬声器播放时使窗口闪烁。</span><span class="sxs-lookup"><span data-stu-id="65861-334">The user may have the Windows SoundSentry service enabled, which will also cause the window to flash when the system sounds are played through the computer's built-in speaker.</span></span>  
  
2.  <span data-ttu-id="65861-335">在非模式窗口中显示重要信息，以便用户可以响应它。</span><span class="sxs-lookup"><span data-stu-id="65861-335">Display the important information in a non-modal window so that the user may respond to it.</span></span>  
  
3.  <span data-ttu-id="65861-336">显示一个获取键盘焦点消息框。</span><span class="sxs-lookup"><span data-stu-id="65861-336">Display a message box that acquires the keyboard focus.</span></span> <span data-ttu-id="65861-337">在用户可能键入时避免使用此方法。</span><span class="sxs-lookup"><span data-stu-id="65861-337">Avoid this method when the user may be typing.</span></span>  
  
4.  <span data-ttu-id="65861-338">在任务栏的状态通知区域中显示一个状态指示器。</span><span class="sxs-lookup"><span data-stu-id="65861-338">Display a status indicator in the status notification area of the taskbar.</span></span> <span data-ttu-id="65861-339">有关详细信息，请参阅[使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)。</span><span class="sxs-lookup"><span data-stu-id="65861-339">For details, see [Adding Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="65861-340">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="65861-340">Testing the Application</span></span>  
 <span data-ttu-id="65861-341">在部署应用程序之前，应测试已实现的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="65861-341">Before deploying the application, you should test the accessibility features that you have implemented.</span></span>  
  
#### <a name="to-test-accessibility-features"></a><span data-ttu-id="65861-342">测试辅助功能</span><span class="sxs-lookup"><span data-stu-id="65861-342">To test accessibility features</span></span>  
  
1.  <span data-ttu-id="65861-343">若要测试键盘访问，请拔下鼠标，并仅使用键盘导航每个功能的用户界面。</span><span class="sxs-lookup"><span data-stu-id="65861-343">To test keyboard access, unplug the mouse and navigate the user interface for each feature using only the keyboard.</span></span> <span data-ttu-id="65861-344">确保只使用键盘即可执行所有任务。</span><span class="sxs-lookup"><span data-stu-id="65861-344">Ensure that all tasks may be performed using the keyboard only.</span></span>  
  
2.  <span data-ttu-id="65861-345">若要测试高对比度的支持，请在控制面板中选择“辅助功能选项”图标。</span><span class="sxs-lookup"><span data-stu-id="65861-345">To test support of High Contrast, choose the Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="65861-346">单击“显示”选项卡并选择“使用高对比度”复选框。</span><span class="sxs-lookup"><span data-stu-id="65861-346">Click the Display tab and select the Use High Contrast check box.</span></span> <span data-ttu-id="65861-347">导航到所有用户界面元素以确保会反映颜色和字体更改。</span><span class="sxs-lookup"><span data-stu-id="65861-347">Navigate through all user interface elements to ensure that the color and font changes are reflected.</span></span> <span data-ttu-id="65861-348">此外，确保忽略文本后面绘制的图像或图案。</span><span class="sxs-lookup"><span data-stu-id="65861-348">Also, ensure that images or patterns drawn behind text are omitted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65861-349">Windows NT 4 的控制面板中没有“辅助功能选项”图标。</span><span class="sxs-lookup"><span data-stu-id="65861-349">Windows NT 4 does not have an Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="65861-350">因此，更改 SystemInformation.HighContrast 设置的此过程不适用于 Windows NT 4。</span><span class="sxs-lookup"><span data-stu-id="65861-350">Thus, this procedure for changing the SystemInformation.HighContrast setting does not work in Windows NT 4.</span></span>  
  
3.  <span data-ttu-id="65861-351">其他工具也用于测试应用程序的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="65861-351">Other tools are readily available for testing the accessibility of an application.</span></span>  
  
4.  <span data-ttu-id="65861-352">若要测试公开键盘焦点，请运行放大镜。</span><span class="sxs-lookup"><span data-stu-id="65861-352">To test exposing the keyboard focus, run Magnifier.</span></span> <span data-ttu-id="65861-353">（若要打开它，请单击“开始”菜单，依次指向“程序”、“附件”和“辅助功能”，然后单击“放大镜”）。</span><span class="sxs-lookup"><span data-stu-id="65861-353">(To open it, click the **Start** menu, point to **Programs**, point to **Accessories**, point to **Accessibility**, and then click **Magnifier**).</span></span> <span data-ttu-id="65861-354">使用键盘 Tab 键和鼠标导航用户界面。</span><span class="sxs-lookup"><span data-stu-id="65861-354">Navigate the user interface using both keyboard tabbing and the mouse.</span></span> <span data-ttu-id="65861-355">确保在“放大镜”中正确跟踪所有导航。</span><span class="sxs-lookup"><span data-stu-id="65861-355">Ensure that all navigation is tracked properly in **Magnifier**.</span></span>  
  
5.  <span data-ttu-id="65861-356">若要测试公开屏幕元素，请运行检查并使用鼠标和 Tab 键选中每个元素。</span><span class="sxs-lookup"><span data-stu-id="65861-356">To test exposing screen elements, run Inspect, and use both the mouse and the TAB key to reach each element.</span></span> <span data-ttu-id="65861-357">确保“检查”窗口中名称、状态、角色、位置和值字段中显示的信息对于 UI 中每个对象的用户都有意义。</span><span class="sxs-lookup"><span data-stu-id="65861-357">Ensure that the information presented in the Name, State, Role, Location, and Value fields of the Inspect window is meaningful to the user for each object in the UI.</span></span>
