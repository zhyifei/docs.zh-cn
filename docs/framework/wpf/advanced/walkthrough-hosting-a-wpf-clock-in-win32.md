---
title: 演练：在 Win32 中承载 WPF 时钟
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 42ed51a1a1ce59b6a3cc3319d86d3a7445403ce4
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919746"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="7d080-102">演练：在 Win32 中承载 WPF 时钟</span><span class="sxs-lookup"><span data-stu-id="7d080-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>

<span data-ttu-id="7d080-103">若要将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 放置在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 应用程序内，请使用 <xref:System.Windows.Interop.HwndSource>，它提供包含 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的 HWND。</span><span class="sxs-lookup"><span data-stu-id="7d080-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="7d080-104">首先创建 <xref:System.Windows.Interop.HwndSource>，并为其提供类似于 CreateWindow 的参数。</span><span class="sxs-lookup"><span data-stu-id="7d080-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="7d080-105">然后，告诉 <xref:System.Windows.Interop.HwndSource> 所需的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容。</span><span class="sxs-lookup"><span data-stu-id="7d080-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="7d080-106">最后，获取 <xref:System.Windows.Interop.HwndSource>中的 HWND。</span><span class="sxs-lookup"><span data-stu-id="7d080-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="7d080-107">本演练演示了如何在重新实现 "操作系统**日期和时间属性**" 对话框的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 应用程序中创建混合 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7d080-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d080-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="7d080-108">Prerequisites</span></span>

<span data-ttu-id="7d080-109">请参阅[WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)。</span><span class="sxs-lookup"><span data-stu-id="7d080-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="7d080-110">如何使用本教程</span><span class="sxs-lookup"><span data-stu-id="7d080-110">How to Use This Tutorial</span></span>

<span data-ttu-id="7d080-111">本教程重点介绍生成互操作应用程序的重要步骤。</span><span class="sxs-lookup"><span data-stu-id="7d080-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="7d080-112">本教程通过示例[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)进行了支持，但该示例反射了最终产品。</span><span class="sxs-lookup"><span data-stu-id="7d080-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="7d080-113">本教程记录的步骤如下所示：你自己的现有 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 项目，可能是预先存在的项目，并将托管 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 添加到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d080-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="7d080-114">可以将最终产品与[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)进行比较。</span><span class="sxs-lookup"><span data-stu-id="7d080-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="7d080-115">Win32 中的 Windows Presentation Framework 的演练 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="7d080-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="7d080-116">下图显示了本教程的预期最终产品：</span><span class="sxs-lookup"><span data-stu-id="7d080-116">The following graphic shows the intended end product of this tutorial:</span></span>

![显示 "日期和时间属性" 对话框的屏幕截图。](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="7d080-118">可以通过在 Visual Studio 中创建C++ Win32 项目，并使用对话框编辑器创建以下内容来重新创建此对话框：</span><span class="sxs-lookup"><span data-stu-id="7d080-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

!["重新创建日期和时间属性" 对话框](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="7d080-120">（您无需使用 Visual Studio 就 <xref:System.Windows.Interop.HwndSource>，也不需要使用C++编写[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]程序，但这是执行此操作的一种相当典型的方法，并且非常适合逐步教程说明）。</span><span class="sxs-lookup"><span data-stu-id="7d080-120">(You do not need to use Visual Studio to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="7d080-121">需要完成五个特定的子步骤，才能将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟添加到对话框中：</span><span class="sxs-lookup"><span data-stu-id="7d080-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="7d080-122">通过在 Visual Studio 中更改项目设置，使你的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 项目可以调用托管代码（ **/clr**）。</span><span class="sxs-lookup"><span data-stu-id="7d080-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in Visual Studio.</span></span>

2. <span data-ttu-id="7d080-123">在单独的 DLL 中创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="7d080-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="7d080-124">将该 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 置于 <xref:System.Windows.Interop.HwndSource>内。</span><span class="sxs-lookup"><span data-stu-id="7d080-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="7d080-125">使用 <xref:System.Windows.Interop.HwndSource.Handle%2A> 属性获取该 <xref:System.Windows.Controls.Page> 的 HWND。</span><span class="sxs-lookup"><span data-stu-id="7d080-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="7d080-126">使用 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 确定在较大的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 应用程序中放置 HWND 的位置</span><span class="sxs-lookup"><span data-stu-id="7d080-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>

## <a name="clr"></a><span data-ttu-id="7d080-127">/clr</span><span class="sxs-lookup"><span data-stu-id="7d080-127">/clr</span></span>

<span data-ttu-id="7d080-128">第一步是将此非托管 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 项目转换为可以调用托管代码的项目。</span><span class="sxs-lookup"><span data-stu-id="7d080-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span> <span data-ttu-id="7d080-129">使用/clr 编译器选项，它将链接到要使用的必要 Dll，并调整 Main 方法以便与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]一起使用。</span><span class="sxs-lookup"><span data-stu-id="7d080-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="7d080-130">若要允许在C++项目中使用托管代码：右键单击 "win32clock 项目"，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="7d080-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="7d080-131">在 "**常规**" 属性页（默认值）上，将 "公共语言运行时支持" 更改为 `/clr`。</span><span class="sxs-lookup"><span data-stu-id="7d080-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="7d080-132">接下来，添加对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]： PresentationCore、PresentationFramework、、WindowsBase、Uiautomationprovider.dll 和 Uiautomationtypes.dll 所需的 Dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="7d080-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="7d080-133">（以下说明假定操作系统安装在 C: 驱动器上。）</span><span class="sxs-lookup"><span data-stu-id="7d080-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="7d080-134">右键单击 "win32clock 项目"，然后选择 "**引用 ...** "，然后在该对话框中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7d080-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="7d080-135">右键单击 "win32clock 项目"，然后选择 "**引用 ...** "。</span><span class="sxs-lookup"><span data-stu-id="7d080-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="7d080-136">单击 "**添加新引用**"，单击 "浏览" 选项卡，输入 C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll，然后单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="7d080-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="7d080-137">对 PresentationFramework.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll。</span><span class="sxs-lookup"><span data-stu-id="7d080-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="7d080-138">对 WindowsBase.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll。</span><span class="sxs-lookup"><span data-stu-id="7d080-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="7d080-139">对 UIAutomationTypes.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll。</span><span class="sxs-lookup"><span data-stu-id="7d080-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="7d080-140">对 UIAutomationProvider.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll。</span><span class="sxs-lookup"><span data-stu-id="7d080-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="7d080-141">单击 "**添加新引用**"，选择 "系统"，然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="7d080-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="7d080-142">单击 **"确定"** 退出用于添加引用的 Win32clock 属性页。</span><span class="sxs-lookup"><span data-stu-id="7d080-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="7d080-143">最后，将 `STAThreadAttribute` 添加到 `_tWinMain` 方法以便与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]一起使用：</span><span class="sxs-lookup"><span data-stu-id="7d080-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="7d080-144">此属性告知公共语言运行时（CLR）当初始化组件对象模型（COM）时，它应使用单线程单元模型（STA），这是 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] （和 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]）所必需的。</span><span class="sxs-lookup"><span data-stu-id="7d080-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="7d080-145">创建 Windows Presentation Framework 页</span><span class="sxs-lookup"><span data-stu-id="7d080-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="7d080-146">接下来，创建一个定义 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>的 DLL。</span><span class="sxs-lookup"><span data-stu-id="7d080-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="7d080-147">通常最简单的方法是将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 创建为独立应用程序，并以这种方式编写和调试 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 部分。</span><span class="sxs-lookup"><span data-stu-id="7d080-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="7d080-148">完成后，可以通过右键单击项目，单击 "**属性**"，转到 "应用程序"，并将 "输出类型" 更改为 "Windows 类库"，将该项目转换为 DLL。</span><span class="sxs-lookup"><span data-stu-id="7d080-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="7d080-149">然后，可以将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll 项目与 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 项目（一个包含两个项目的解决方案）相结合–右键单击解决方案，选择 " **Add\Existing 项目**"。</span><span class="sxs-lookup"><span data-stu-id="7d080-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="7d080-150">若要从 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 项目中使用该 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll，需要添加引用：</span><span class="sxs-lookup"><span data-stu-id="7d080-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>

1. <span data-ttu-id="7d080-151">右键单击 "win32clock 项目"，然后选择 "**引用 ...** "。</span><span class="sxs-lookup"><span data-stu-id="7d080-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="7d080-152">单击 "**添加新引用**"。</span><span class="sxs-lookup"><span data-stu-id="7d080-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="7d080-153">单击 "**项目**" 选项卡。选择 "WPFClock"，然后单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="7d080-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="7d080-154">单击 **"确定"** 退出用于添加引用的 Win32clock 属性页。</span><span class="sxs-lookup"><span data-stu-id="7d080-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="7d080-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="7d080-155">HwndSource</span></span>

<span data-ttu-id="7d080-156">接下来，使用 <xref:System.Windows.Interop.HwndSource> 使 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> 外观类似于 HWND。</span><span class="sxs-lookup"><span data-stu-id="7d080-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="7d080-157">将此代码块添加到 C++ 文件中：</span><span class="sxs-lookup"><span data-stu-id="7d080-157">You add this block of code to a C++ file:</span></span>

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

 <span data-ttu-id="7d080-158">这是一长段代码，可以作一些解释。</span><span class="sxs-lookup"><span data-stu-id="7d080-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="7d080-159">第一部分是各种子句，无需完全限定所有调用：</span><span class="sxs-lookup"><span data-stu-id="7d080-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="7d080-160">然后定义一个函数，该函数创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容，在其周围放置 <xref:System.Windows.Interop.HwndSource> 并返回 HWND：</span><span class="sxs-lookup"><span data-stu-id="7d080-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="7d080-161">首先创建一个 <xref:System.Windows.Interop.HwndSource>，其参数与 CreateWindow 类似：</span><span class="sxs-lookup"><span data-stu-id="7d080-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

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

<span data-ttu-id="7d080-162">然后通过调用其构造函数创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类：</span><span class="sxs-lookup"><span data-stu-id="7d080-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="7d080-163">然后，将该页连接到 <xref:System.Windows.Interop.HwndSource>：</span><span class="sxs-lookup"><span data-stu-id="7d080-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="7d080-164">在最后一行中，返回 <xref:System.Windows.Interop.HwndSource>的 HWND：</span><span class="sxs-lookup"><span data-stu-id="7d080-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="7d080-165">放置 Hwnd</span><span class="sxs-lookup"><span data-stu-id="7d080-165">Positioning the Hwnd</span></span>

<span data-ttu-id="7d080-166">现在，你已具有包含 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟的 HWND，你需要将该 HWND 置于 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 对话框内。</span><span class="sxs-lookup"><span data-stu-id="7d080-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span> <span data-ttu-id="7d080-167">如果只知道放置 HWND 的位置，只需将该大小和位置传递到前面定义的 `GetHwnd` 函数。</span><span class="sxs-lookup"><span data-stu-id="7d080-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="7d080-168">但是，由于已使用资源文件来定义对话框，因此你不完全确定任何 HWND 的放置位置。</span><span class="sxs-lookup"><span data-stu-id="7d080-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="7d080-169">你可以使用 Visual Studio 对话框编辑器将 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 的静态控件放在希望时钟进入的位置（"在此处插入时钟"），并使用它来定位 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟。</span><span class="sxs-lookup"><span data-stu-id="7d080-169">You can use the Visual Studio dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="7d080-170">在其中处理 WM_INITDIALOG 的情况下，可以使用 `GetDlgItem` 来检索占位符 STATIC 的 HWND：</span><span class="sxs-lookup"><span data-stu-id="7d080-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="7d080-171">然后，计算占位符的大小和位置，以便在该位置放置 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟：</span><span class="sxs-lookup"><span data-stu-id="7d080-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="7d080-172">RECT 矩形；</span><span class="sxs-lookup"><span data-stu-id="7d080-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="7d080-173">然后，你隐藏占位符 STATIC：</span><span class="sxs-lookup"><span data-stu-id="7d080-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="7d080-174">并在该位置创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟 HWND：</span><span class="sxs-lookup"><span data-stu-id="7d080-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="7d080-175">为了使本教程有趣，并生成真正的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟，此时需要创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟控件。</span><span class="sxs-lookup"><span data-stu-id="7d080-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="7d080-176">你可以在标记中执行大部分操作，代码隐藏中只有几个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7d080-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="7d080-177">由于本教程介绍互操作性，而不是关于控件设计的，因此，此处提供了 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 时钟的完整代码作为代码块提供，没有用于构建或每个部分所代表的单独说明。</span><span class="sxs-lookup"><span data-stu-id="7d080-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="7d080-178">随意尝试此代码来更改控件的外观或功能。</span><span class="sxs-lookup"><span data-stu-id="7d080-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="7d080-179">此处为标记：</span><span class="sxs-lookup"><span data-stu-id="7d080-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="7d080-180">以下是附带的代码隐藏：</span><span class="sxs-lookup"><span data-stu-id="7d080-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="7d080-181">最终结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="7d080-181">The final result looks like:</span></span>

!["最终结果日期和时间属性" 对话框](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="7d080-183">若要将最终结果与生成此屏幕截图的代码进行比较，请参阅[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)。</span><span class="sxs-lookup"><span data-stu-id="7d080-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d080-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d080-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="7d080-185">WPF 和 Win32 互操作</span><span class="sxs-lookup"><span data-stu-id="7d080-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="7d080-186">Win32 时钟互操作示例</span><span class="sxs-lookup"><span data-stu-id="7d080-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
