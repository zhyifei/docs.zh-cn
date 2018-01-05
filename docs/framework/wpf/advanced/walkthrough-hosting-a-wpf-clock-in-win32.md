---
title: "演练：在 Win32 中承载 WPF 时钟"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: caf652f8a80da8e927a74ffc012d09b2389b1b09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="fe422-102">演练：在 Win32 中承载 WPF 时钟</span><span class="sxs-lookup"><span data-stu-id="fe422-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>
<span data-ttu-id="fe422-103">将[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]应用程序，使用<xref:System.Windows.Interop.HwndSource>，它提供了包含 HWND 你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容。</span><span class="sxs-lookup"><span data-stu-id="fe422-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="fe422-104">首先创建<xref:System.Windows.Interop.HwndSource>，并向其提供类似于 CreateWindow 的参数。</span><span class="sxs-lookup"><span data-stu-id="fe422-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span>  <span data-ttu-id="fe422-105">然后，通知<xref:System.Windows.Interop.HwndSource>有关[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]你要在其中包含内容。</span><span class="sxs-lookup"><span data-stu-id="fe422-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span>  <span data-ttu-id="fe422-106">最后，获取外的 HWND <xref:System.Windows.Interop.HwndSource>。</span><span class="sxs-lookup"><span data-stu-id="fe422-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="fe422-107">本演练阐释了如何创建混合[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]重新实现操作系统的应用程序**日期和时间属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="fe422-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fe422-108">系统必备</span><span class="sxs-lookup"><span data-stu-id="fe422-108">Prerequisites</span></span>  
 <span data-ttu-id="fe422-109">请参阅[WPF 和 Win32 间的互操作](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)。</span><span class="sxs-lookup"><span data-stu-id="fe422-109">See [WPF and Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="fe422-110">如何使用本教程</span><span class="sxs-lookup"><span data-stu-id="fe422-110">How to Use This Tutorial</span></span>  
 <span data-ttu-id="fe422-111">本教程重点介绍生成互操作应用程序的重要步骤。</span><span class="sxs-lookup"><span data-stu-id="fe422-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="fe422-112">本教程支持通过一个示例中， [Win32 时钟间的互操作示例](http://go.microsoft.com/fwlink/?LinkID=160051)，但该示例是最终产品的反射。</span><span class="sxs-lookup"><span data-stu-id="fe422-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="fe422-113">本教程介绍的步骤，就像已启动与现有[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]你自己的项目，可能是一个预先存在的项目，和你正将添加一个承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe422-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="fe422-114">你可以比较与你最终产品[Win32 时钟间的互操作示例](http://go.microsoft.com/fwlink/?LinkID=160051)。</span><span class="sxs-lookup"><span data-stu-id="fe422-114">You can compare your end product with [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="fe422-115">Win32 中的 Windows Presentation Framework 的演练 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="fe422-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>  
 <span data-ttu-id="fe422-116">下图显示了本教程的预期最终产品：</span><span class="sxs-lookup"><span data-stu-id="fe422-116">The following graphic shows the intended end product of this tutorial:</span></span>  
  
 <span data-ttu-id="fe422-117">![“日期和时间属性”对话框](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span><span class="sxs-lookup"><span data-stu-id="fe422-117">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span></span>  
  
 <span data-ttu-id="fe422-118">可以通过创建 c + + 重新创建此对话框[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目中[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]，并使用对话框编辑器创建以下：</span><span class="sxs-lookup"><span data-stu-id="fe422-118">You can recreate this dialog by creating C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and using the dialog editor to create the following:</span></span>  
  
 <span data-ttu-id="fe422-119">![“日期和时间属性”对话框](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span><span class="sxs-lookup"><span data-stu-id="fe422-119">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span></span>  
  
 <span data-ttu-id="fe422-120">(不需要使用[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]使用<xref:System.Windows.Interop.HwndSource>，且不需要使用 c + + 编写[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]程序，但这的相当典型的方式做到这一点，并且适于本身非常好的分步说明教程)。</span><span class="sxs-lookup"><span data-stu-id="fe422-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>  
  
 <span data-ttu-id="fe422-121">您需要实现五个特定的子步骤才能将放置[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟在对话框：</span><span class="sxs-lookup"><span data-stu-id="fe422-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>  
  
1.  <span data-ttu-id="fe422-122">启用你[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目以调用托管的代码 (**/clr**) 通过更改中的项目设置[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fe422-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="fe422-123">创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>中单独的 DLL。</span><span class="sxs-lookup"><span data-stu-id="fe422-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>  
  
3.  <span data-ttu-id="fe422-124">将它放[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>内<xref:System.Windows.Interop.HwndSource>。</span><span class="sxs-lookup"><span data-stu-id="fe422-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>  
  
4.  <span data-ttu-id="fe422-125">为此获取 HWND<xref:System.Windows.Controls.Page>使用<xref:System.Windows.Interop.HwndSource.Handle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="fe422-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>  
  
5.  <span data-ttu-id="fe422-126">使用[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]来决定在何处放置在较大 HWND[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]应用程序</span><span class="sxs-lookup"><span data-stu-id="fe422-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>  
  
## <a name="clr"></a><span data-ttu-id="fe422-127">/clr</span><span class="sxs-lookup"><span data-stu-id="fe422-127">/clr</span></span>  
 <span data-ttu-id="fe422-128">第一步是将此非托管[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目到一个可以调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="fe422-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span>  <span data-ttu-id="fe422-129">使用 /clr 编译器选项，将其链接到你想要使用，并调整与一起使用的 Main 方法的所需 Dll [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fe422-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="fe422-130">若要启用 c + + 项目中的托管代码的使用： win32clock 项目右键单击并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="fe422-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span>  <span data-ttu-id="fe422-131">上**常规**属性页 （默认值）、 公共语言运行时将支持更改为`/clr`。</span><span class="sxs-lookup"><span data-stu-id="fe422-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>  
  
 <span data-ttu-id="fe422-132">接下来，添加对所需的 Dll 的引用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll、 PresentationFramework.dll、 System.dll、 WindowsBase.dll、 UIAutomationProvider.dll 和 UIAutomationTypes.dll。</span><span class="sxs-lookup"><span data-stu-id="fe422-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="fe422-133">（以下说明假定操作系统安装在 C: 驱动器上。）</span><span class="sxs-lookup"><span data-stu-id="fe422-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>  
  
1.  <span data-ttu-id="fe422-134">右键单击 win32clock 项目并选择**引用...**，该对话框中：</span><span class="sxs-lookup"><span data-stu-id="fe422-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>  
  
2.  <span data-ttu-id="fe422-135">右键单击 win32clock 项目并选择**引用...**.</span><span class="sxs-lookup"><span data-stu-id="fe422-135">Right-click win32clock project and select **References...**.</span></span>  
  
3.  <span data-ttu-id="fe422-136">单击**添加新引用**，单击浏览卡，输入 C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll，然后单击确定。</span><span class="sxs-lookup"><span data-stu-id="fe422-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>  
  
4.  <span data-ttu-id="fe422-137">对 PresentationFramework.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll。</span><span class="sxs-lookup"><span data-stu-id="fe422-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>  
  
5.  <span data-ttu-id="fe422-138">对 WindowsBase.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll。</span><span class="sxs-lookup"><span data-stu-id="fe422-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>  
  
6.  <span data-ttu-id="fe422-139">对 UIAutomationTypes.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll。</span><span class="sxs-lookup"><span data-stu-id="fe422-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>  
  
7.  <span data-ttu-id="fe422-140">对 UIAutomationProvider.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll。</span><span class="sxs-lookup"><span data-stu-id="fe422-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>  
  
8.  <span data-ttu-id="fe422-141">单击**添加新引用**，选择 System.dll，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fe422-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>  
  
9. <span data-ttu-id="fe422-142">单击**确定**退出 win32clock 属性页中添加引用。</span><span class="sxs-lookup"><span data-stu-id="fe422-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
 <span data-ttu-id="fe422-143">最后，添加`STAThreadAttribute`到`_tWinMain`方法用于[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fe422-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 <span data-ttu-id="fe422-144">此特性告知[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]，当它初始化[!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]，它应使用单线程的单元模型 (STA)，进行所需[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)](和[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="fe422-144">This attribute tells the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>  
  
## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="fe422-145">创建 Windows Presentation Framework 页</span><span class="sxs-lookup"><span data-stu-id="fe422-145">Create a Windows Presentation Framework Page</span></span>  
 <span data-ttu-id="fe422-146">接下来，创建一个 DLL，它定义[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="fe422-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="fe422-147">通常很容易创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>作为独立的应用程序，并编写并调试[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]部分通过这种方式。</span><span class="sxs-lookup"><span data-stu-id="fe422-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span>  <span data-ttu-id="fe422-148">完成后，该项目均可转换为 DLL，请右键单击该项目，单击**属性**，转到应用程序，并将输出类型更改为 Windows 类库。</span><span class="sxs-lookup"><span data-stu-id="fe422-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>  
  
 <span data-ttu-id="fe422-149">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]然后可以与组合 dll 项目[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目 （一个解决方案包含两个项目） – 右击该解决方案，选择**添加 \ 现有项目**。</span><span class="sxs-lookup"><span data-stu-id="fe422-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>  
  
 <span data-ttu-id="fe422-150">使用该[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]dll[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目中，你需要添加的引用：</span><span class="sxs-lookup"><span data-stu-id="fe422-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>  
  
1.  <span data-ttu-id="fe422-151">右键单击 win32clock 项目并选择**引用...**.</span><span class="sxs-lookup"><span data-stu-id="fe422-151">Right-click win32clock project and select **References...**.</span></span>  
  
2.  <span data-ttu-id="fe422-152">单击**添加新引用**。</span><span class="sxs-lookup"><span data-stu-id="fe422-152">Click **Add New Reference**.</span></span>  
  
3.  <span data-ttu-id="fe422-153">单击“项目”选项卡。选择 WPFClock，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="fe422-153">Click the **Projects** tab.  Select WPFClock, click OK.</span></span>  
  
4.  <span data-ttu-id="fe422-154">单击**确定**退出 win32clock 属性页中添加引用。</span><span class="sxs-lookup"><span data-stu-id="fe422-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
## <a name="hwndsource"></a><span data-ttu-id="fe422-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="fe422-155">HwndSource</span></span>  
 <span data-ttu-id="fe422-156">接下来，使用<xref:System.Windows.Interop.HwndSource>以便[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>如下所示 HWND。</span><span class="sxs-lookup"><span data-stu-id="fe422-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span>  <span data-ttu-id="fe422-157">将此代码块添加到 C++ 文件中：</span><span class="sxs-lookup"><span data-stu-id="fe422-157">You add this block of code to a C++ file:</span></span>  
  
```  
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
  
 <span data-ttu-id="fe422-158">这是一长段代码，可以作一些解释。</span><span class="sxs-lookup"><span data-stu-id="fe422-158">This is a long piece of code that could use some explanation.</span></span>  <span data-ttu-id="fe422-159">第一部分是各种子句，无需完全限定所有调用：</span><span class="sxs-lookup"><span data-stu-id="fe422-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 <span data-ttu-id="fe422-160">然后，定义一个函数来创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容，将<xref:System.Windows.Interop.HwndSource>解决它，并返回 HWND:</span><span class="sxs-lookup"><span data-stu-id="fe422-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 <span data-ttu-id="fe422-161">首先创建<xref:System.Windows.Interop.HwndSource>，其参数位于类似于 CreateWindow:</span><span class="sxs-lookup"><span data-stu-id="fe422-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 <span data-ttu-id="fe422-162">则你创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容类通过调用其构造函数：</span><span class="sxs-lookup"><span data-stu-id="fe422-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 <span data-ttu-id="fe422-163">然后连接到页<xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="fe422-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
source->RootVisual = page;  
```  
  
 <span data-ttu-id="fe422-164">和中的最后一行，返回的 HWND <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="fe422-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a><span data-ttu-id="fe422-165">放置 Hwnd</span><span class="sxs-lookup"><span data-stu-id="fe422-165">Positioning the Hwnd</span></span>  
 <span data-ttu-id="fe422-166">既然你已包含 HWND[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟，你必须将在该 HWND[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]对话框。</span><span class="sxs-lookup"><span data-stu-id="fe422-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span>  <span data-ttu-id="fe422-167">如果你知道只需在何处放置 HWND，只需将该大小和位置`GetHwnd`前面定义的函数。</span><span class="sxs-lookup"><span data-stu-id="fe422-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span>  <span data-ttu-id="fe422-168">但是，由于已使用资源文件来定义对话框，因此你不完全确定任何 HWND 的放置位置。</span><span class="sxs-lookup"><span data-stu-id="fe422-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span>  <span data-ttu-id="fe422-169">你可以使用[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]对话框编辑器将[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]静态控制想时钟转 （"插入时钟此处"），并使用它来定位[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟。</span><span class="sxs-lookup"><span data-stu-id="fe422-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>  
  
 <span data-ttu-id="fe422-170">哪里处理 WM_INITDIALOG，因此，使用`GetDlgItem`占位符静态检索 HWND:</span><span class="sxs-lookup"><span data-stu-id="fe422-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 <span data-ttu-id="fe422-171">您然后计算的大小和位置的占位符静态，以便您可以放入[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟在该位置：</span><span class="sxs-lookup"><span data-stu-id="fe422-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>  
  
 <span data-ttu-id="fe422-172">RECT 矩形；</span><span class="sxs-lookup"><span data-stu-id="fe422-172">RECT rectangle;</span></span>  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 <span data-ttu-id="fe422-173">然后，你隐藏占位符 STATIC：</span><span class="sxs-lookup"><span data-stu-id="fe422-173">Then you hide the placeholder STATIC:</span></span>  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 <span data-ttu-id="fe422-174">并创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟 HWND 在该位置：</span><span class="sxs-lookup"><span data-stu-id="fe422-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 <span data-ttu-id="fe422-175">使教程生动有趣，并生成一个真实[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟，你将需要创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]此时时钟控件。</span><span class="sxs-lookup"><span data-stu-id="fe422-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="fe422-176">你可以在标记中执行大部分操作，代码隐藏中只有几个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fe422-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="fe422-177">由于本教程是有关间的互操作而不是考虑控件的设计，完成代码[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供时钟此处代码块，而不离散说明如何生成或每个部分的含义。</span><span class="sxs-lookup"><span data-stu-id="fe422-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="fe422-178">随意尝试此代码来更改控件的外观或功能。</span><span class="sxs-lookup"><span data-stu-id="fe422-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>  
  
 <span data-ttu-id="fe422-179">此处为标记：</span><span class="sxs-lookup"><span data-stu-id="fe422-179">Here is the markup:</span></span>  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 <span data-ttu-id="fe422-180">以下是附带的代码隐藏：</span><span class="sxs-lookup"><span data-stu-id="fe422-180">And here is the accompanying code-behind:</span></span>  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 <span data-ttu-id="fe422-181">最终结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="fe422-181">The final result looks like:</span></span>  
  
 <span data-ttu-id="fe422-182">![“日期和时间属性”对话框](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span><span class="sxs-lookup"><span data-stu-id="fe422-182">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span></span>  
  
 <span data-ttu-id="fe422-183">若要比较的代码生成此屏幕截图中，你最终结果，请参阅[Win32 时钟间的互操作示例](http://go.microsoft.com/fwlink/?LinkID=160051)。</span><span class="sxs-lookup"><span data-stu-id="fe422-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe422-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe422-184">See Also</span></span>  
 <xref:System.Windows.Interop.HwndSource>  
 [<span data-ttu-id="fe422-185">WPF 和 Win32 互操作</span><span class="sxs-lookup"><span data-stu-id="fe422-185">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [<span data-ttu-id="fe422-186">Win32 时钟互操作示例</span><span class="sxs-lookup"><span data-stu-id="fe422-186">Win32 Clock Interoperation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160051)
