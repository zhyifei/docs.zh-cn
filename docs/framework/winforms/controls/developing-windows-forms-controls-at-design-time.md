---
title: 디자인 타임에 컨트롤 개발
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: dac049ea6a51037daa0e23dc93476e4410b2df06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745988"
---
# <a name="develop-windows-forms-controls-at-design-time"></a><span data-ttu-id="b55b6-102">在设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="b55b6-102">Develop Windows Forms controls at design time</span></span>

<span data-ttu-id="b55b6-103">.NET Framework는 컨트롤 제작자에게 다양한 컨트롤 제작 기술을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="b55b6-104">제작자는 더 이상 기존 컨트롤의 컬렉션으로 작동하는 복합 컨트롤을 디자인하도록 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="b55b6-105">상속을 통해 기존의 복합 컨트롤 또는 Windows Forms 컨트롤에서 사용자 정의 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="b55b6-106">또한 사용자 지정 그리기를 구현하는 사용자 정의 컨트롤을 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="b55b6-107">이러한 옵션을 사용하면 시각적 인터페이스의 디자인과 기능에 많은 유연성을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="b55b6-108">이러한 기능을 이용하려면 개체 지향 프로그래밍 개념을 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="b55b6-109">无需透彻地理解继承，但你可能会发现，引用[继承基础知识（Visual Basic）](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)是非常有用的。</span><span class="sxs-lookup"><span data-stu-id="b55b6-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>

<span data-ttu-id="b55b6-110">Web Forms에서 사용할 사용자 지정 컨트롤을 만들려면 [사용자 지정 ASP.NET 서버 컨트롤 개발](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b55b6-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b55b6-111">단원 내용</span><span class="sxs-lookup"><span data-stu-id="b55b6-111">In this section</span></span>

<span data-ttu-id="b55b6-112">[演练：创作复合控件](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-112">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="b55b6-113">C#에서 간단한 복합 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-113">Shows how to create a simple composite control in C#.</span></span>

<span data-ttu-id="b55b6-114">[演练：从 Windows 窗体控件继承](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-114">[Walkthrough: Inheriting from a Windows Forms Control](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="b55b6-115">C#에서 상속을 사용하는 간단한 Windows Forms 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-115">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>

<span data-ttu-id="b55b6-116">[演练：使用 Windows 窗体控件上的智能标记执行常见任务](performing-common-tasks-using-smart-tags-on-wf-controls.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-116">[Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](performing-common-tasks-using-smart-tags-on-wf-controls.md)</span></span>\
<span data-ttu-id="b55b6-117">Windows Forms 컨트롤에서 스마트 태그 기능을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-117">Shows how to use the smart tag feature on Windows Forms controls.</span></span>

<span data-ttu-id="b55b6-118">[演练：用 DesignerSerializationVisibilityAttribute\ 序列化标准类型的集合](serializing-collections-designerserializationvisibilityattribute.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-118">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)\</span></span>
<span data-ttu-id="b55b6-119">演示如何使用 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> 特性序列化集合。</span><span class="sxs-lookup"><span data-stu-id="b55b6-119">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>

<span data-ttu-id="b55b6-120">[연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-120">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="b55b6-121">Windows Forms 컨트롤의 디자인 타임 동작을 디버그하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-121">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>

<span data-ttu-id="b55b6-122">[演练：创建利用 Visual Studio 设计时功能的 Windows 窗体控件](creating-a-wf-control-design-time-features.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-122">[Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md)</span></span>\
<span data-ttu-id="b55b6-123">복합 컨트롤을 디자인 환경에 긴밀하게 통합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-123">Shows how to tightly integrate a composite control into the design environment.</span></span>

<span data-ttu-id="b55b6-124">[방법: Windows Forms 컨트롤 작성](how-to-author-controls-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-124">[How to: Author Controls for Windows Forms](how-to-author-controls-for-windows-forms.md)</span></span>\
<span data-ttu-id="b55b6-125">Windows Forms 컨트롤을 구현할 때 고려해야 할 사항에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-125">Provides an overview of considerations for implementing a Windows Forms control.</span></span>

<span data-ttu-id="b55b6-126">[방법: 합성 컨트롤 제작](how-to-author-composite-controls.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-126">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>\
<span data-ttu-id="b55b6-127">복합 컨트롤에서 상속하여 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-127">Shows how to create a control by inheriting from a composite control.</span></span>

<span data-ttu-id="b55b6-128">[방법: UserControl 클래스에서 상속](how-to-inherit-from-the-usercontrol-class.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-128">[How to: Inherit from the UserControl Class](how-to-inherit-from-the-usercontrol-class.md)</span></span>\
<span data-ttu-id="b55b6-129">복합 컨트롤을 만드는 절차에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-129">Provides an overview of the procedure for creating a composite control.</span></span>

<span data-ttu-id="b55b6-130">[방법: 기존 Windows Forms 컨트롤에서 상속](how-to-inherit-from-existing-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-130">[How to: Inherit from Existing Windows Forms Controls](how-to-inherit-from-existing-windows-forms-controls.md)</span></span>\
<span data-ttu-id="b55b6-131">演示如何通过从 <xref:System.Windows.Forms.Button> 控件类继承来创建扩展控件。</span><span class="sxs-lookup"><span data-stu-id="b55b6-131">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>

<span data-ttu-id="b55b6-132">[방법: Control 클래스에서 상속](how-to-inherit-from-the-control-class.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-132">[How to: Inherit from the Control Class](how-to-inherit-from-the-control-class.md)</span></span>\
<span data-ttu-id="b55b6-133">확장 컨트롤을 만드는 방법에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-133">Provides an overview of creating an extended control.</span></span>

<span data-ttu-id="b55b6-134">[如何：在设计时将控件与窗体边缘对齐](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-134">[How to: Align a Control to the Edges of Forms at Design Time](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span></span>\
<span data-ttu-id="b55b6-135">演示如何使用 <xref:System.Windows.Forms.Control.Dock%2A> 属性将控件与它所占有窗体的边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="b55b6-135">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="b55b6-136">[방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-136">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>\
<span data-ttu-id="b55b6-137">**도구 상자 사용자 지정** 대화 상자에 표시되도록 컨트롤을 설치하는 절차를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-137">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>

<span data-ttu-id="b55b6-138">[如何：为控件提供工具箱位图](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-138">[How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span></span>\
<span data-ttu-id="b55b6-139">演示如何使用 <xref:System.Drawing.ToolboxBitmapAttribute> 在**工具箱**中的自定义控件旁边显示一个图标。</span><span class="sxs-lookup"><span data-stu-id="b55b6-139">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="b55b6-140">[방법: UserControl의 런타임 동작 테스트](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-140">[How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span></span>\
<span data-ttu-id="b55b6-141">**UserControl 테스트 컨테이너**를 사용하여 복합 컨트롤의 동작을 테스트하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-141">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>

<span data-ttu-id="b55b6-142">[Windows Forms 디자이너의 디자인 타임 오류](design-time-errors-in-the-windows-forms-designer.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-142">[Design-Time Errors in the Windows Forms Designer](design-time-errors-in-the-windows-forms-designer.md)</span></span>\
<span data-ttu-id="b55b6-143">Windows Forms 디자이너를 로드하지 못할 때 Microsoft Visual Studio에 표시되는 디자인 타임 오류 목록의 의미와 용도에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-143">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>

<span data-ttu-id="b55b6-144">[컨트롤 및 구성 요소 작성 문제 해결](troubleshooting-control-and-component-authoring.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-144">[Troubleshooting Control and Component Authoring](troubleshooting-control-and-component-authoring.md)</span></span>\
<span data-ttu-id="b55b6-145">사용자 지정 구성 요소 또는 컨트롤을 작성할 때 발생할 수 있는 일반적인 문제를 진단하고 수정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-145">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>

## <a name="reference"></a><span data-ttu-id="b55b6-146">참조</span><span class="sxs-lookup"><span data-stu-id="b55b6-146">Reference</span></span>

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a><span data-ttu-id="b55b6-147">관련 단원</span><span class="sxs-lookup"><span data-stu-id="b55b6-147">Related sections</span></span>

<span data-ttu-id="b55b6-148">[.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-148">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="b55b6-149">.NET Framework를 사용하여 사용자 지정 컨트롤을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-149">Discusses how to create your own custom controls with the .NET Framework.</span></span>

<span data-ttu-id="b55b6-150">[Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-150">[Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md)</span></span>\
<span data-ttu-id="b55b6-151">구성 요소의 생성과 사용을 간소화하도록 설계된 공용 언어 런타임을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-151">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="b55b6-152">이러한 간소화의 중요한 측면은 다양한 프로그래밍 언어를 사용하여 작성된 구성 요소 간의 향상된 상호 운용성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-152">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="b55b6-153">CLS(공용 언어 사양)를 사용하면 여러 프로그래밍 언어를 사용하는 도구와 구성 요소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-153">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>

<span data-ttu-id="b55b6-154">[연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span><span class="sxs-lookup"><span data-stu-id="b55b6-154">[Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span></span>\
<span data-ttu-id="b55b6-155">**도구 상자 사용자 지정** 대화 상자에 구성 요소 또는 컨트롤을 표시하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b55b6-155">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
