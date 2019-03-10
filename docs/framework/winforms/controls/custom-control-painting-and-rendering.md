---
title: 自定义控件的绘制和呈现
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: ec9002ffa4a7e2c82f59d52344764a01afe4c568
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722134"
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="a11c9-102">自定义控件的绘制和呈现</span><span class="sxs-lookup"><span data-stu-id="a11c9-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="a11c9-103">自定义绘制的控件是可轻松在.NET Framework 的许多复杂任务之一。</span><span class="sxs-lookup"><span data-stu-id="a11c9-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="a11c9-104">在创作时自定义控件，有许多种有关控件的图形外观。</span><span class="sxs-lookup"><span data-stu-id="a11c9-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="a11c9-105">如果创作继承的控件`Control`，必须提供代码，使您的控件来呈现其图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="a11c9-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="a11c9-106">如果通过继承创建用户控件`UserControl`，继承或从一个 Windows 窗体控件，可以忽略在标准的图形表示形式，并提供你自己的图形代码。</span><span class="sxs-lookup"><span data-stu-id="a11c9-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="a11c9-107">如果你想要提供的构成控件的自定义呈现`UserControl`创作，你的选项变得更为有限，但仍允许范围广泛的控件和应用程序的图形化可能性。</span><span class="sxs-lookup"><span data-stu-id="a11c9-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a11c9-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="a11c9-108">In This Section</span></span>  
 [<span data-ttu-id="a11c9-109">呈现 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="a11c9-109">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)  
 <span data-ttu-id="a11c9-110">演示如何编写显示一个控件的逻辑。</span><span class="sxs-lookup"><span data-stu-id="a11c9-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="a11c9-111">用户绘制的控件</span><span class="sxs-lookup"><span data-stu-id="a11c9-111">User-Drawn Controls</span></span>](user-drawn-controls.md)  
 <span data-ttu-id="a11c9-112">概述在编写和重写为您的控件的呈现代码中所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="a11c9-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="a11c9-113">构成控件</span><span class="sxs-lookup"><span data-stu-id="a11c9-113">Constituent Controls</span></span>](constituent-controls.md)  
 <span data-ttu-id="a11c9-114">介绍如何在你的用户控件和窗体中实现的构成控件的自定义呈现代码。</span><span class="sxs-lookup"><span data-stu-id="a11c9-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="a11c9-115">如何：使控件在运行时不可见</span><span class="sxs-lookup"><span data-stu-id="a11c9-115">How to: Make Your Control Invisible at Run Time</span></span>](how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="a11c9-116">演示如何使用<xref:System.Windows.Forms.Control.Visible%2A>隐藏和显示控件的属性。</span><span class="sxs-lookup"><span data-stu-id="a11c9-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="a11c9-117">如何：使控件拥有透明背景</span><span class="sxs-lookup"><span data-stu-id="a11c9-117">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="a11c9-118">演示如何使用<xref:System.Windows.Forms.Control.SetStyle%2A>方法来创建不透明、 透明或部分透明的背景颜色。</span><span class="sxs-lookup"><span data-stu-id="a11c9-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="a11c9-119">使用视觉样式呈现控件</span><span class="sxs-lookup"><span data-stu-id="a11c9-119">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="a11c9-120">演示如何呈现支持它们的操作系统中使用视觉样式的控件。</span><span class="sxs-lookup"><span data-stu-id="a11c9-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a11c9-121">参考</span><span class="sxs-lookup"><span data-stu-id="a11c9-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="a11c9-122">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="a11c9-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="a11c9-123">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="a11c9-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="a11c9-124">介绍了此方法。</span><span class="sxs-lookup"><span data-stu-id="a11c9-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a11c9-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="a11c9-125">Related Sections</span></span>  
 [<span data-ttu-id="a11c9-126">如何：创建用于绘制图形对象</span><span class="sxs-lookup"><span data-stu-id="a11c9-126">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="a11c9-127">引入了[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]从 Visual Studio 角度来看，并提供链接的详细信息的图形功能。</span><span class="sxs-lookup"><span data-stu-id="a11c9-127">Introduces [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="a11c9-128">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="a11c9-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="a11c9-129">描述可以创作自定义控件的类型。</span><span class="sxs-lookup"><span data-stu-id="a11c9-129">Describes the kinds of custom controls you can author.</span></span>
