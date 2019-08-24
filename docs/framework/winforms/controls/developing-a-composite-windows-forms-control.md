---
title: 开发复合 Windows 窗体控件
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 9ccbf3de3f5c65b99a06c29ffce4c96896d11fae
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015958"
---
# <a name="develop-a-composite-windows-forms-control"></a><span data-ttu-id="393b0-102">开发复合 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="393b0-102">Develop a composite Windows Forms control</span></span>

<span data-ttu-id="393b0-103">可以通过组合其它 Windows 窗体控件来开发复合 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="393b0-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="393b0-104">派生自<xref:System.Web.UI.UserControl>的复合控件称为用户控件。</span><span class="sxs-lookup"><span data-stu-id="393b0-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="393b0-105">基类 <xref:System.Windows.Forms.UserControl> 为子控件提供了键盘路由，从而确保子控件可以接收焦点。</span><span class="sxs-lookup"><span data-stu-id="393b0-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="393b0-106">有关用户控件的示例, 请参阅<xref:System.Windows.Forms.UserControl> [如何:在 Windows 窗体控件](how-to-apply-attributes-in-windows-forms-controls.md)中应用特性。</span><span class="sxs-lookup"><span data-stu-id="393b0-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>

<span data-ttu-id="393b0-107">Visual Studio 中的 Windows 窗体设计器为创作用户控件提供丰富的设计时支持。</span><span class="sxs-lookup"><span data-stu-id="393b0-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>

- [<span data-ttu-id="393b0-108">如何：在 "选择工具箱项" 对话框中显示控件</span><span class="sxs-lookup"><span data-stu-id="393b0-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [<span data-ttu-id="393b0-109">演练：用 DesignerSerializationVisibilityAttribute 序列化标准类型的集合</span><span class="sxs-lookup"><span data-stu-id="393b0-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="393b0-110">演练：使用 Visual 从 Windows 窗体控件继承C#</span><span class="sxs-lookup"><span data-stu-id="393b0-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="393b0-111">如何：为控件提供工具箱位图</span><span class="sxs-lookup"><span data-stu-id="393b0-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="393b0-112">如何：从现有 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="393b0-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="393b0-113">演练：在设计时调试自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="393b0-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="393b0-114">如何：从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="393b0-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="393b0-115">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="393b0-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="393b0-116">如何：在设计时将控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="393b0-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="393b0-117">如何：从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="393b0-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="393b0-118">如何：Windows 窗体的创作控件</span><span class="sxs-lookup"><span data-stu-id="393b0-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="393b0-119">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="393b0-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="393b0-120">演练：使用视觉对象创作复合控件C#</span><span class="sxs-lookup"><span data-stu-id="393b0-120">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="393b0-121">演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="393b0-121">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="393b0-122">[如何：创建利用设计时功能的 Windows 窗体控件](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="393b0-122">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="393b0-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="393b0-123">See also</span></span>

- [<span data-ttu-id="393b0-124">如何：在 Windows 窗体控件中应用特性</span><span class="sxs-lookup"><span data-stu-id="393b0-124">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="393b0-125">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="393b0-125">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="393b0-126">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="393b0-126">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
