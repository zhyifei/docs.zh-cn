---
title: 使用 .NET Framework 开发自定义 Windows 窗体控件
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
ms.openlocfilehash: 3d628d75b75c311c266648886b3b971c4833d172
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972245"
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="c930c-102">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="c930c-102">Developing Custom Windows Forms Controls with the .NET Framework</span></span>
<span data-ttu-id="c930c-103">Windows 窗体控件是可以重用的组件，可以封装用户界面功能并用于客户端基于 Windows 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c930c-103">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="c930c-104">Windows 窗体不仅可以提供许多易用的控件，而且还可以提供用于开发你自己的控件的基础结构。</span><span class="sxs-lookup"><span data-stu-id="c930c-104">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="c930c-105">你可以组合现有的控件、扩展现有的控件或创作你自己的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="c930c-105">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="c930c-106">本节介绍了背景信息和示例，有助于你开发 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="c930c-106">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c930c-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="c930c-107">In This Section</span></span>  
 [<span data-ttu-id="c930c-108">在 Windows 窗体中使用控件的概述</span><span class="sxs-lookup"><span data-stu-id="c930c-108">Overview of Using Controls in Windows Forms</span></span>](overview-of-using-controls-in-windows-forms.md)  
 <span data-ttu-id="c930c-109">突出显示使用 Windows 窗体应用程序中的控件的重要元素。</span><span class="sxs-lookup"><span data-stu-id="c930c-109">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="c930c-110">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="c930c-110">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="c930c-111">描述你可以使用 <xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间创作的不同类型的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="c930c-111">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="c930c-112">Windows 窗体控件开发基础知识</span><span class="sxs-lookup"><span data-stu-id="c930c-112">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)  
 <span data-ttu-id="c930c-113">讨论开发 Windows 窗体控件的前几个步骤。</span><span class="sxs-lookup"><span data-stu-id="c930c-113">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="c930c-114">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="c930c-114">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)  
 <span data-ttu-id="c930c-115">演示如何将属性添加到 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="c930c-115">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="c930c-116">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="c930c-116">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)  
 <span data-ttu-id="c930c-117">演示如何处理和定义 Windows 窗体控件中的事件。</span><span class="sxs-lookup"><span data-stu-id="c930c-117">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="c930c-118">Windows 窗体控件中的特性</span><span class="sxs-lookup"><span data-stu-id="c930c-118">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="c930c-119">描述你可以应用到自定义控件和组件的属性或其他成员的特性。</span><span class="sxs-lookup"><span data-stu-id="c930c-119">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="c930c-120">自定义控件的绘制和呈现</span><span class="sxs-lookup"><span data-stu-id="c930c-120">Custom Control Painting and Rendering</span></span>](custom-control-painting-and-rendering.md)  
 <span data-ttu-id="c930c-121">演示如何自定义控件的外观。</span><span class="sxs-lookup"><span data-stu-id="c930c-121">Shows how to customize the appearance of your controls.</span></span>  
  
 [<span data-ttu-id="c930c-122">Windows 窗体控件的布局</span><span class="sxs-lookup"><span data-stu-id="c930c-122">Layout in Windows Forms Controls</span></span>](layout-in-windows-forms-controls.md)  
 <span data-ttu-id="c930c-123">演示如何创建控件和窗体的复杂布局。</span><span class="sxs-lookup"><span data-stu-id="c930c-123">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 [<span data-ttu-id="c930c-124">Windows 窗体控件中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="c930c-124">Multithreading in Windows Forms Controls</span></span>](multithreading-in-windows-forms-controls.md)  
 <span data-ttu-id="c930c-125">演示如何实现多线程控件。</span><span class="sxs-lookup"><span data-stu-id="c930c-125">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c930c-126">参考</span><span class="sxs-lookup"><span data-stu-id="c930c-126">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="c930c-127">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="c930c-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="c930c-128">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="c930c-128">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c930c-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="c930c-129">Related Sections</span></span>  
 <span data-ttu-id="c930c-130">[组件的设计时特性](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c930c-130">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="c930c-131">将列出的元数据特性应用到组件和控件，以便在设计时正确显示在可视化设计器中。</span><span class="sxs-lookup"><span data-stu-id="c930c-131">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="c930c-132">[扩展设计时支持](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c930c-132">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="c930c-133">描述如何实现提供设计时支持的类，例如编辑器和设计器。</span><span class="sxs-lookup"><span data-stu-id="c930c-133">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 <span data-ttu-id="c930c-134">[如何：许可组件和控件](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="c930c-134">[How to: License Components and Controls](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span></span>  
 <span data-ttu-id="c930c-135">描述如何实现授予控件或组件许可权限。</span><span class="sxs-lookup"><span data-stu-id="c930c-135">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="c930c-136">另请参阅[设计时开发 Windows 窗体控件](developing-windows-forms-controls-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="c930c-136">Also see [Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md).</span></span>
