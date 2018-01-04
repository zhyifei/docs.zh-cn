---
title: "如何：从 Control 类继承"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7cbca79cd3541df1db7ace3a7d5f67bf3f2b2ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="95d03-102">如何：从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="95d03-102">How to: Inherit from the Control Class</span></span>
<span data-ttu-id="95d03-103">如果你想要创建使用 Windows 窗体上的完全自定义控件，应从继承<xref:System.Windows.Forms.Control>类。</span><span class="sxs-lookup"><span data-stu-id="95d03-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="95d03-104">时从继承<xref:System.Windows.Forms.Control>类要求你执行详细的规划和实现，它还提供的选项的最大范围。</span><span class="sxs-lookup"><span data-stu-id="95d03-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="95d03-105">从继承时<xref:System.Windows.Forms.Control>，继承使控件能够运行的最基本功能。</span><span class="sxs-lookup"><span data-stu-id="95d03-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="95d03-106">中的固有功能<xref:System.Windows.Forms.Control>类处理通过键盘和鼠标的用户输入，定义的边界和控件大小，提供 windows 句柄，并提供消息处理和安全性。</span><span class="sxs-lookup"><span data-stu-id="95d03-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="95d03-107">它没有纳入任何绘图功能（这里指的是控件的图形界面的实际呈现），也没有纳入任何特定的用户交互功能。</span><span class="sxs-lookup"><span data-stu-id="95d03-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="95d03-108">必须通过自定义代码提供所有的这些功能。</span><span class="sxs-lookup"><span data-stu-id="95d03-108">You must provide all of these aspects through custom code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95d03-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="95d03-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="95d03-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="95d03-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="95d03-111">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="95d03-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-custom-control"></a><span data-ttu-id="95d03-112">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="95d03-112">To create a custom control</span></span>  
  
1.  <span data-ttu-id="95d03-113">创建一个新的 **Windows 应用程序**或 **Windows 控件库**项目。</span><span class="sxs-lookup"><span data-stu-id="95d03-113">Create a new **Windows Application** or **Windows Control Library** project.</span></span>  
  
2.  <span data-ttu-id="95d03-114">从“项目”菜单中，选择“添加类”。</span><span class="sxs-lookup"><span data-stu-id="95d03-114">From the **Project** menu, choose **Add Class**.</span></span>  
  
3.  <span data-ttu-id="95d03-115">在“添加新项”对话框中，单击“自定义控件”。</span><span class="sxs-lookup"><span data-stu-id="95d03-115">In the **Add New Item** dialog box, click **Custom Control**.</span></span>  
  
     <span data-ttu-id="95d03-116">一个新的自定义控件将被添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="95d03-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="95d03-117">按 F7 打开自定义控件的“代码编辑器”。</span><span class="sxs-lookup"><span data-stu-id="95d03-117">Press F7 to open the **Code Editor** for your custom control.</span></span>  
  
5.  <span data-ttu-id="95d03-118">找到<xref:System.Windows.Forms.Control.OnPaint%2A>方法，将为空除外调用<xref:System.Windows.Forms.Control.OnPaint%2A>基本类的方法。</span><span class="sxs-lookup"><span data-stu-id="95d03-118">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>  
  
6.  <span data-ttu-id="95d03-119">修改代码以纳入控件所需的任何自定义绘图。</span><span class="sxs-lookup"><span data-stu-id="95d03-119">Modify the code to incorporate any custom painting you want for your control.</span></span>  
  
     <span data-ttu-id="95d03-120">有关编写代码来呈现控件的图形的信息，请参阅[自定义控件的绘制和呈现](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)。</span><span class="sxs-lookup"><span data-stu-id="95d03-120">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span></span>  
  
7.  <span data-ttu-id="95d03-121">实现控件将纳入的任何自定义方法、属性或事件。</span><span class="sxs-lookup"><span data-stu-id="95d03-121">Implement any custom methods, properties, or events that your control will incorporate.</span></span>  
  
8.  <span data-ttu-id="95d03-122">保存并测试控件。</span><span class="sxs-lookup"><span data-stu-id="95d03-122">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d03-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="95d03-123">See Also</span></span>  
 [<span data-ttu-id="95d03-124">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="95d03-124">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="95d03-125">如何：从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="95d03-125">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [<span data-ttu-id="95d03-126">如何：从现有 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="95d03-126">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [<span data-ttu-id="95d03-127">如何：创作 Windows 窗体的控件</span><span class="sxs-lookup"><span data-stu-id="95d03-127">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="95d03-128">Visual Basic 中继承的事件处理程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="95d03-128">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="95d03-129">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="95d03-129">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
