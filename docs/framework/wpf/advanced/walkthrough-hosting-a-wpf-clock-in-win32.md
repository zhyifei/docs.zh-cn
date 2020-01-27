---
title: 演练：在 Win32 中承载 WPF 时钟
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 79f79e42652ca51c409fabb12a572485ad734b35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744896"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a><span data-ttu-id="fc4af-102">演练：在 Win32 中承载 WPF 时钟</span><span class="sxs-lookup"><span data-stu-id="fc4af-102">Walkthrough: Host a WPF Clock in Win32</span></span>

<span data-ttu-id="fc4af-103">若要将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 放入 Win32 应用程序中，请使用 <xref:System.Windows.Interop.HwndSource>，它提供包含 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的 HWND。</span><span class="sxs-lookup"><span data-stu-id="fc4af-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="fc4af-104">首先创建 <xref:System.Windows.Interop.HwndSource>，并为其提供类似于 CreateWindow 的参数。</span><span class="sxs-lookup"><span data-stu-id="fc4af-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="fc4af-105">然后，告诉 <xref:System.Windows.Interop.HwndSource> 所需的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容。</span><span class="sxs-lookup"><span data-stu-id="fc4af-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="fc4af-106">最后，获取 <xref:System.Windows.Interop.HwndSource>中的 HWND。</span><span class="sxs-lookup"><span data-stu-id="fc4af-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="fc4af-107">本演练演示如何在重新实现 "操作系统**日期和时间属性**" 对话框的 Win32 应用程序中创建混合 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fc4af-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside Win32 application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fc4af-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="fc4af-108">Prerequisites</span></span>

<span data-ttu-id="fc4af-109">请参阅[WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)。</span><span class="sxs-lookup"><span data-stu-id="fc4af-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="fc4af-110">이 자습서의 사용 방법</span><span class="sxs-lookup"><span data-stu-id="fc4af-110">How to Use This Tutorial</span></span>

<span data-ttu-id="fc4af-111">이 자습서는 상호 운용 애플리케이션을 생성하는 중요한 단계에 대해 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="fc4af-112">本教程通过示例[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)进行了支持，但该示例反射了最终产品。</span><span class="sxs-lookup"><span data-stu-id="fc4af-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="fc4af-113">本教程介绍的步骤如下所示：从自己的现有 Win32 项目开始（可能是预先存在的项目），并向应用程序添加托管的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fc4af-113">This tutorial documents the steps as if you were starting with an existing Win32 project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="fc4af-114">可以将最终产品与[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)进行比较。</span><span class="sxs-lookup"><span data-stu-id="fc4af-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="fc4af-115">Win32 내에서 Windows Presentation Framework의 연습(HwndSource)</span><span class="sxs-lookup"><span data-stu-id="fc4af-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="fc4af-116">다음 그래픽에서는 이 자습서의 의도된 최종 제품을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-116">The following graphic shows the intended end product of this tutorial:</span></span>

![显示 "日期和时间属性" 对话框的屏幕截图。](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="fc4af-118">可以通过在 Visual Studio 中创建C++ Win32 项目，并使用对话框编辑器创建以下内容来重新创建此对话框：</span><span class="sxs-lookup"><span data-stu-id="fc4af-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

!["重新创建日期和时间属性" 对话框](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="fc4af-120">（您无需使用 Visual Studio 就 <xref:System.Windows.Interop.HwndSource>，也不需要使用C++编写 Win32 程序，但这是执行此操作的一种相当典型的方法，并且非常适合逐步教程说明）。</span><span class="sxs-lookup"><span data-stu-id="fc4af-120">(You do not need to use Visual Studio to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write Win32 programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="fc4af-121">需要完成五个特定的子步骤，才能将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟添加到对话框中：</span><span class="sxs-lookup"><span data-stu-id="fc4af-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="fc4af-122">通过在 Visual Studio 中更改项目设置，使 Win32 项目可以调用托管代码（ **/clr**）。</span><span class="sxs-lookup"><span data-stu-id="fc4af-122">Enable your Win32 project to call managed code (**/clr**) by changing project settings in Visual Studio.</span></span>

2. <span data-ttu-id="fc4af-123">在单独的 DLL 中创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="fc4af-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="fc4af-124">将该 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 置于 <xref:System.Windows.Interop.HwndSource>内。</span><span class="sxs-lookup"><span data-stu-id="fc4af-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="fc4af-125">使用 <xref:System.Windows.Interop.HwndSource.Handle%2A> 属性获取该 <xref:System.Windows.Controls.Page> 的 HWND。</span><span class="sxs-lookup"><span data-stu-id="fc4af-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="fc4af-126">使用 Win32 确定在较大的 Win32 应用程序中放置 HWND 的位置</span><span class="sxs-lookup"><span data-stu-id="fc4af-126">Use Win32 to decide where to place the HWND within the larger Win32 application</span></span>

## <a name="clr"></a><span data-ttu-id="fc4af-127">/clr</span><span class="sxs-lookup"><span data-stu-id="fc4af-127">/clr</span></span>

<span data-ttu-id="fc4af-128">第一步是将此非托管 Win32 项目转换为可以调用托管代码的项目。</span><span class="sxs-lookup"><span data-stu-id="fc4af-128">The first step is to turn this unmanaged Win32 project into one that can call managed code.</span></span> <span data-ttu-id="fc4af-129">使用/clr 编译器选项，它将链接到要使用的必要 Dll，并调整 Main 方法以便与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]一起使用。</span><span class="sxs-lookup"><span data-stu-id="fc4af-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="fc4af-130">若要允许在C++项目中使用托管代码：右键单击 "win32clock 项目"，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="fc4af-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="fc4af-131">在 "**常规**" 属性页（默认值）上，将 "公共语言运行时支持" 更改为 `/clr`。</span><span class="sxs-lookup"><span data-stu-id="fc4af-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="fc4af-132">接下来，添加对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]： PresentationCore、PresentationFramework、、WindowsBase、Uiautomationprovider.dll 和 Uiautomationtypes.dll 所需的 Dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="fc4af-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="fc4af-133">다음 지침에서는 운영 체제가 C: 드라이브에 설치되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="fc4af-134">右键单击 "win32clock 项目"，然后选择 "**引用 ...** "，然后在该对话框中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fc4af-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="fc4af-135">右键单击 "win32clock 项目"，然后选择 "**引用 ...** "。</span><span class="sxs-lookup"><span data-stu-id="fc4af-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="fc4af-136">单击 "**添加新引用**"，单击 "浏览" 选项卡，输入 C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll，然后单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="fc4af-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="fc4af-137">PresentationFramework.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="fc4af-138">WindowsBase.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="fc4af-139">UIAutomationTypes.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="fc4af-140">UIAutomationProvider.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="fc4af-141">单击 "**添加新引用**"，选择 "系统"，然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="fc4af-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="fc4af-142">单击 **"确定"** 退出用于添加引用的 Win32clock 属性页。</span><span class="sxs-lookup"><span data-stu-id="fc4af-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="fc4af-143">最后，将 `STAThreadAttribute` 添加到 `_tWinMain` 方法以便与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]一起使用：</span><span class="sxs-lookup"><span data-stu-id="fc4af-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="fc4af-144">此属性告知公共语言运行时（CLR）当初始化组件对象模型（COM）时，它应使用单线程单元模型（STA），这是 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] （和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]）所必需的。</span><span class="sxs-lookup"><span data-stu-id="fc4af-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="fc4af-145">Windows Presentation Framework 페이지 만들기</span><span class="sxs-lookup"><span data-stu-id="fc4af-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="fc4af-146">接下来，创建一个定义 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>的 DLL。</span><span class="sxs-lookup"><span data-stu-id="fc4af-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="fc4af-147">通常最简单的方法是将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 创建为独立应用程序，并以这种方式编写和调试 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 部分。</span><span class="sxs-lookup"><span data-stu-id="fc4af-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="fc4af-148">完成后，可以通过右键单击项目，单击 "**属性**"，转到 "应用程序"，并将 "输出类型" 更改为 "Windows 类库"，将该项目转换为 DLL。</span><span class="sxs-lookup"><span data-stu-id="fc4af-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="fc4af-149">然后，可以将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll 项目与 Win32 项目（一个包含两个项目的解决方案）结合在一起-右键单击解决方案，选择 " **Add\Existing 项目**"。</span><span class="sxs-lookup"><span data-stu-id="fc4af-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the Win32 project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="fc4af-150">若要从 Win32 项目使用该 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll，需要添加引用：</span><span class="sxs-lookup"><span data-stu-id="fc4af-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the Win32 project, you need to add a reference:</span></span>

1. <span data-ttu-id="fc4af-151">右键单击 "win32clock 项目"，然后选择 "**引用 ...** "。</span><span class="sxs-lookup"><span data-stu-id="fc4af-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="fc4af-152">单击 "**添加新引用**"。</span><span class="sxs-lookup"><span data-stu-id="fc4af-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="fc4af-153">单击 "**项目**" 选项卡。选择 "WPFClock"，然后单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="fc4af-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="fc4af-154">单击 **"确定"** 退出用于添加引用的 Win32clock 属性页。</span><span class="sxs-lookup"><span data-stu-id="fc4af-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="fc4af-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="fc4af-155">HwndSource</span></span>

<span data-ttu-id="fc4af-156">接下来，使用 <xref:System.Windows.Interop.HwndSource> 使 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 外观类似于 HWND。</span><span class="sxs-lookup"><span data-stu-id="fc4af-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="fc4af-157">다음 코드 블록을 C++ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-157">You add this block of code to a C++ file:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;

    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
        HwndSource^ source = gcnew HwndSource(
            0, // class style
            WS_VISIBLE | WS_CHILD, // style
            0, // exstyle
            x, y, width, height,
            "hi", // NAME
            IntPtr(parent)        // parent window
            );

        UIElement^ page = gcnew WPFClock::Clock();
        source->RootVisual = page;
        return (HWND) source->Handle.ToPointer();
    }
}
}
```

 <span data-ttu-id="fc4af-158">다음은 약간의 설명이 필요할 수 있는 긴 코드 조각입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="fc4af-159">첫 번째 부분은 다양한 절이어서 모든 호출을 정규화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="fc4af-160">然后定义一个函数，该函数创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容，在其周围放置 <xref:System.Windows.Interop.HwndSource> 并返回 HWND：</span><span class="sxs-lookup"><span data-stu-id="fc4af-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="fc4af-161">首先创建一个 <xref:System.Windows.Interop.HwndSource>，其参数与 CreateWindow 类似：</span><span class="sxs-lookup"><span data-stu-id="fc4af-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

<span data-ttu-id="fc4af-162">然后通过调用其构造函数创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类：</span><span class="sxs-lookup"><span data-stu-id="fc4af-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="fc4af-163">然后，将该页连接到 <xref:System.Windows.Interop.HwndSource>：</span><span class="sxs-lookup"><span data-stu-id="fc4af-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="fc4af-164">在最后一行中，返回 <xref:System.Windows.Interop.HwndSource>的 HWND：</span><span class="sxs-lookup"><span data-stu-id="fc4af-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="fc4af-165">Hwnd 위치 지정</span><span class="sxs-lookup"><span data-stu-id="fc4af-165">Positioning the Hwnd</span></span>

<span data-ttu-id="fc4af-166">现在，你已具有包含 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟的 HWND，你需要将该 HWND 置于 Win32 对话框内。</span><span class="sxs-lookup"><span data-stu-id="fc4af-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the Win32 dialog.</span></span> <span data-ttu-id="fc4af-167">如果只知道放置 HWND 的位置，只需将该大小和位置传递到前面定义的 `GetHwnd` 函数。</span><span class="sxs-lookup"><span data-stu-id="fc4af-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="fc4af-168">그러나 리소스 파일을 사용하여 대화 상자를 정의했으므로 HWND를 배치할 위치를 정확하게 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="fc4af-169">你可以使用 Visual Studio 对话框编辑器将 Win32 静态控件放置在希望时钟进入的位置（"在此处插入时钟"），并使用它来定位 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟。</span><span class="sxs-lookup"><span data-stu-id="fc4af-169">You can use the Visual Studio dialog editor to put a Win32 STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="fc4af-170">在其中处理 WM_INITDIALOG 的情况下，使用 `GetDlgItem` 检索占位符 STATIC 的 HWND：</span><span class="sxs-lookup"><span data-stu-id="fc4af-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="fc4af-171">然后，计算占位符的大小和位置，以便在该位置放置 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟：</span><span class="sxs-lookup"><span data-stu-id="fc4af-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="fc4af-172">RECT 사각형의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="fc4af-173">그런 다음 자리 표시자 STATIC을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="fc4af-174">并在该位置创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟 HWND：</span><span class="sxs-lookup"><span data-stu-id="fc4af-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="fc4af-175">为了使本教程有趣，并生成真正的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟，此时需要创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟控件。</span><span class="sxs-lookup"><span data-stu-id="fc4af-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="fc4af-176">코드 숨김에서 몇 개의 이벤트 처리기만 사용하여 태그에서 거의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="fc4af-177">由于本教程介绍互操作性，而不是关于控件设计的，因此，此处提供了 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟的完整代码作为代码块提供，没有用于构建或每个部分所代表的单独说明。</span><span class="sxs-lookup"><span data-stu-id="fc4af-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="fc4af-178">이 코드를 자유롭게 사용하여 컨트롤의 모양과 느낌 또는 기능을 변경해 보세요.</span><span class="sxs-lookup"><span data-stu-id="fc4af-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="fc4af-179">다음은 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="fc4af-180">다음은 함께 제공되는 코드 숨김입니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="fc4af-181">최종 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fc4af-181">The final result looks like:</span></span>

!["最终结果日期和时间属性" 对话框](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="fc4af-183">若要将最终结果与生成此屏幕截图的代码进行比较，请参阅[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)。</span><span class="sxs-lookup"><span data-stu-id="fc4af-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc4af-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc4af-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="fc4af-185">WPF 및 Win32 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="fc4af-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="fc4af-186">Win32 시계 상호 운용 샘플</span><span class="sxs-lookup"><span data-stu-id="fc4af-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
