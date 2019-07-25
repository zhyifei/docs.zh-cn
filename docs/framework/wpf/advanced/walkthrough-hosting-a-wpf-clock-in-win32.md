---
title: 演练：在 Win32 中承载 WPF 时钟
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 27e1a2e88beeacf8c2cd98f61b11542ee2341e8f
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433980"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="dad76-102">演练：在 Win32 中承载 WPF 时钟</span><span class="sxs-lookup"><span data-stu-id="dad76-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>

<span data-ttu-id="dad76-103">若要[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]放置[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]在应用程序<xref:System.Windows.Interop.HwndSource>内, 请使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , 它提供包含内容的 HWND。</span><span class="sxs-lookup"><span data-stu-id="dad76-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="dad76-104">首先创建, 并<xref:System.Windows.Interop.HwndSource>为其提供类似于 CreateWindow 的参数。</span><span class="sxs-lookup"><span data-stu-id="dad76-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="dad76-105">然后, 告诉<xref:System.Windows.Interop.HwndSource>您所需[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的内容。</span><span class="sxs-lookup"><span data-stu-id="dad76-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="dad76-106">最后, 获取中的 HWND <xref:System.Windows.Interop.HwndSource>。</span><span class="sxs-lookup"><span data-stu-id="dad76-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="dad76-107">本演练演示了如何在重新实现 " [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]操作系统[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] **日期和时间属性**" 对话框的应用程序中创建混合。</span><span class="sxs-lookup"><span data-stu-id="dad76-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dad76-108">系统必备</span><span class="sxs-lookup"><span data-stu-id="dad76-108">Prerequisites</span></span>

<span data-ttu-id="dad76-109">请参阅[WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)。</span><span class="sxs-lookup"><span data-stu-id="dad76-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="dad76-110">如何使用本教程</span><span class="sxs-lookup"><span data-stu-id="dad76-110">How to Use This Tutorial</span></span>

<span data-ttu-id="dad76-111">本教程重点介绍生成互操作应用程序的重要步骤。</span><span class="sxs-lookup"><span data-stu-id="dad76-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="dad76-112">本教程通过示例[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)进行了支持, 但该示例反射了最终产品。</span><span class="sxs-lookup"><span data-stu-id="dad76-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="dad76-113">本教程介绍的步骤如下所示: 从自己的现有[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目开始, 可能是预先存在的项目, 并将托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="dad76-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="dad76-114">可以将最终产品与[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)进行比较。</span><span class="sxs-lookup"><span data-stu-id="dad76-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="dad76-115">Win32 中的 Windows Presentation Framework 的演练 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="dad76-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="dad76-116">下图显示了本教程的预期最终产品：</span><span class="sxs-lookup"><span data-stu-id="dad76-116">The following graphic shows the intended end product of this tutorial:</span></span>

![显示 "日期和时间属性" 对话框的屏幕截图。](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="dad76-118">可以通过在 Visual Studio 中创建C++ Win32 项目, 并使用对话框编辑器创建以下内容来重新创建此对话框:</span><span class="sxs-lookup"><span data-stu-id="dad76-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

!["重新创建日期和时间属性" 对话框](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="dad76-120">[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] (您无需<xref:System.Windows.Interop.HwndSource>使用, 也不需要使用C++来编写[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]程序, 但这是执行此操作的一种相当典型的方法, 并且非常适合逐步教程说明)。</span><span class="sxs-lookup"><span data-stu-id="dad76-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="dad76-121">需要完成五个特定的子步骤, 才能将[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟放入对话框:</span><span class="sxs-lookup"><span data-stu-id="dad76-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="dad76-122">通过更改[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]中[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]的项目设置, 使你的项目可以调用托管代码 ( **/clr**)。</span><span class="sxs-lookup"><span data-stu-id="dad76-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>

2. <span data-ttu-id="dad76-123">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 在单独<xref:System.Windows.Controls.Page>的 DLL 中创建。</span><span class="sxs-lookup"><span data-stu-id="dad76-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="dad76-124">将其放入<xref:System.Windows.Interop.HwndSource>。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page></span><span class="sxs-lookup"><span data-stu-id="dad76-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="dad76-125">使用属性获取的<xref:System.Windows.Controls.Page>HWND <xref:System.Windows.Interop.HwndSource.Handle%2A> 。</span><span class="sxs-lookup"><span data-stu-id="dad76-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="dad76-126">用于[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]决定在较大[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]的应用程序中放置 HWND 的位置</span><span class="sxs-lookup"><span data-stu-id="dad76-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>

## <a name="clr"></a><span data-ttu-id="dad76-127">/clr</span><span class="sxs-lookup"><span data-stu-id="dad76-127">/clr</span></span>

<span data-ttu-id="dad76-128">第一步是将此非托管[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目转换为可以调用托管代码的项目。</span><span class="sxs-lookup"><span data-stu-id="dad76-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span> <span data-ttu-id="dad76-129">使用/clr 编译器选项, 它将链接到您想要使用的所需 Dll, 并调整 Main 方法以便与一起[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="dad76-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="dad76-130">若要允许在C++项目中使用托管代码:右键单击 "win32clock 项目", 然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="dad76-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="dad76-131">在 "**常规**" 属性页 (默认值) 上, 将 "公共语言`/clr`运行时支持" 更改为。</span><span class="sxs-lookup"><span data-stu-id="dad76-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="dad76-132">接下来, 添加对所需的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]dll 的引用:PresentationCore、PresentationFramework、WindowsBase、Uiautomationprovider.dll、Uiautomationtypes.dll 和的链接的链接。</span><span class="sxs-lookup"><span data-stu-id="dad76-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="dad76-133">（以下说明假定操作系统安装在 C: 驱动器上。）</span><span class="sxs-lookup"><span data-stu-id="dad76-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="dad76-134">右键单击 "win32clock 项目", 然后选择 "**引用 ...** ", 然后在该对话框中执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="dad76-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="dad76-135">右键单击 "win32clock 项目", 然后选择 "**引用 ...** "。</span><span class="sxs-lookup"><span data-stu-id="dad76-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="dad76-136">单击 "**添加新引用**", 单击 "浏览" 选项卡, 输入 C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, 然后单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="dad76-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="dad76-137">针对 PresentationFramework 重复:C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll。</span><span class="sxs-lookup"><span data-stu-id="dad76-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="dad76-138">针对 WindowsBase 重复:C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll。</span><span class="sxs-lookup"><span data-stu-id="dad76-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="dad76-139">针对 Uiautomationtypes.dll 重复:C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll。</span><span class="sxs-lookup"><span data-stu-id="dad76-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="dad76-140">针对 Uiautomationprovider.dll 重复:C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll。</span><span class="sxs-lookup"><span data-stu-id="dad76-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="dad76-141">单击 "**添加新引用**", 选择 "系统", 然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="dad76-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="dad76-142">单击 **"确定"** 退出用于添加引用的 Win32clock 属性页。</span><span class="sxs-lookup"><span data-stu-id="dad76-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="dad76-143">最后, 将添加`STAThreadAttribute` `_tWinMain`到方法以便与一起[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用:</span><span class="sxs-lookup"><span data-stu-id="dad76-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="dad76-144">此属性告知公共语言运行时 (CLR) 当初始化组件对象模型 (COM) 时, 它应使用单线程单元模型 (STA), 这对于[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (和[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]) 是必需的。</span><span class="sxs-lookup"><span data-stu-id="dad76-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="dad76-145">创建 Windows Presentation Framework 页</span><span class="sxs-lookup"><span data-stu-id="dad76-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="dad76-146">接下来, 创建一个定义的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>DLL。</span><span class="sxs-lookup"><span data-stu-id="dad76-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="dad76-147">通常, 将创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>为独立应用程序, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]并编写和调试此部分。</span><span class="sxs-lookup"><span data-stu-id="dad76-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="dad76-148">完成后, 可以通过右键单击项目, 单击 "**属性**", 转到 "应用程序", 并将 "输出类型" 更改为 "Windows 类库", 将该项目转换为 DLL。</span><span class="sxs-lookup"><span data-stu-id="dad76-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="dad76-149">然后[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , 可以将 dll 项目[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]与项目 (一个包含两个项目的解决方案) 结合在一起-右键单击解决方案, 选择 " **Add\Existing 项目**"。</span><span class="sxs-lookup"><span data-stu-id="dad76-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="dad76-150">若要[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]从项目中使用该 dll, 需要添加引用:</span><span class="sxs-lookup"><span data-stu-id="dad76-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>

1. <span data-ttu-id="dad76-151">右键单击 "win32clock 项目", 然后选择 "**引用 ...** "。</span><span class="sxs-lookup"><span data-stu-id="dad76-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="dad76-152">单击 "**添加新引用**"。</span><span class="sxs-lookup"><span data-stu-id="dad76-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="dad76-153">单击“项目”选项卡。选择 WPFClock，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="dad76-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="dad76-154">单击 **"确定"** 退出用于添加引用的 Win32clock 属性页。</span><span class="sxs-lookup"><span data-stu-id="dad76-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="dad76-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="dad76-155">HwndSource</span></span>

<span data-ttu-id="dad76-156">接下来, 您<xref:System.Windows.Interop.HwndSource>将使用来[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使其<xref:System.Windows.Controls.Page>看起来像一个 HWND。</span><span class="sxs-lookup"><span data-stu-id="dad76-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="dad76-157">将此代码块添加到 C++ 文件中：</span><span class="sxs-lookup"><span data-stu-id="dad76-157">You add this block of code to a C++ file:</span></span>

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

 <span data-ttu-id="dad76-158">这是一长段代码，可以作一些解释。</span><span class="sxs-lookup"><span data-stu-id="dad76-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="dad76-159">第一部分是各种子句，无需完全限定所有调用：</span><span class="sxs-lookup"><span data-stu-id="dad76-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="dad76-160">然后定义一个函数, 用于创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容, <xref:System.Windows.Interop.HwndSource>将其环绕, 然后返回 HWND:</span><span class="sxs-lookup"><span data-stu-id="dad76-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="dad76-161">首先, 创建一个<xref:System.Windows.Interop.HwndSource>, 其参数与 CreateWindow 类似:</span><span class="sxs-lookup"><span data-stu-id="dad76-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

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

<span data-ttu-id="dad76-162">然后通过调用其[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]构造函数来创建内容类:</span><span class="sxs-lookup"><span data-stu-id="dad76-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="dad76-163">然后, 将该页面连接到<xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="dad76-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="dad76-164">在最后一行中, 返回的<xref:System.Windows.Interop.HwndSource>HWND:</span><span class="sxs-lookup"><span data-stu-id="dad76-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="dad76-165">放置 Hwnd</span><span class="sxs-lookup"><span data-stu-id="dad76-165">Positioning the Hwnd</span></span>

<span data-ttu-id="dad76-166">现在, 你已拥有包含[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟的 hwnd, 你需要将该 hwnd 放入[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]对话框中。</span><span class="sxs-lookup"><span data-stu-id="dad76-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span> <span data-ttu-id="dad76-167">如果只知道放置 HWND 的位置, 只需将该大小和位置传递到前面定义的`GetHwnd`函数。</span><span class="sxs-lookup"><span data-stu-id="dad76-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="dad76-168">但是，由于已使用资源文件来定义对话框，因此你不完全确定任何 HWND 的放置位置。</span><span class="sxs-lookup"><span data-stu-id="dad76-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="dad76-169">可以使用[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]对话框编辑器[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]将静态控件放置在希望时钟进入的位置 ("在此处插入时钟"), 并[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]使用它来定位时钟。</span><span class="sxs-lookup"><span data-stu-id="dad76-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="dad76-170">在其中处理 WM_INITDIALOG 的情况下`GetDlgItem` , 你可以使用来检索占位符 STATIC 的 HWND:</span><span class="sxs-lookup"><span data-stu-id="dad76-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="dad76-171">然后, 计算占位符的大小和位置, 以便可以[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]将该时钟放置在该位置:</span><span class="sxs-lookup"><span data-stu-id="dad76-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="dad76-172">RECT 矩形；</span><span class="sxs-lookup"><span data-stu-id="dad76-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="dad76-173">然后，你隐藏占位符 STATIC：</span><span class="sxs-lookup"><span data-stu-id="dad76-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="dad76-174">并在该[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]位置创建时钟 HWND:</span><span class="sxs-lookup"><span data-stu-id="dad76-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="dad76-175">为了使本教程有趣, 并生成一个实际[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟, 此时需要创建一个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟控件。</span><span class="sxs-lookup"><span data-stu-id="dad76-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="dad76-176">你可以在标记中执行大部分操作，代码隐藏中只有几个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="dad76-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="dad76-177">由于本教程介绍互操作性, 而不是关于控件设计的, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]因此在此处以代码块的形式提供了时钟的完整代码, 但没有用于构建或每个部分所代表的单独说明。</span><span class="sxs-lookup"><span data-stu-id="dad76-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="dad76-178">随意尝试此代码来更改控件的外观或功能。</span><span class="sxs-lookup"><span data-stu-id="dad76-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="dad76-179">此处为标记：</span><span class="sxs-lookup"><span data-stu-id="dad76-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="dad76-180">以下是附带的代码隐藏：</span><span class="sxs-lookup"><span data-stu-id="dad76-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="dad76-181">最终结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="dad76-181">The final result looks like:</span></span>

!["最终结果日期和时间属性" 对话框](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="dad76-183">若要将最终结果与生成此屏幕截图的代码进行比较, 请参阅[Win32 时钟互操作示例](https://go.microsoft.com/fwlink/?LinkID=160051)。</span><span class="sxs-lookup"><span data-stu-id="dad76-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="dad76-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="dad76-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="dad76-185">WPF 和 Win32 互操作</span><span class="sxs-lookup"><span data-stu-id="dad76-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="dad76-186">Win32 时钟互操作示例</span><span class="sxs-lookup"><span data-stu-id="dad76-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
