---
title: 禁用 Visual Studio 中的 DPI 识别功能
description: 讨论 HDPI 监视器上的 Windows 窗体设计器以及如何运行 Visual Studio 作为不识别 DPI 的进程的限制。
ms.date: 12/17/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 0820450fb9ae257cba87b3055ea1dde91112b19e
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655993"
---
# <a name="disable-dpi-awareness-in-visual-studio"></a><span data-ttu-id="7b604-103">禁用 Visual Studio 中的 DPI 识别功能</span><span class="sxs-lookup"><span data-stu-id="7b604-103">Disable DPI-awareness in Visual Studio</span></span>

<span data-ttu-id="7b604-104">Visual Studio 是以每英寸点数 (DPI) 识别应用程序，这意味着会自动显示刻度。</span><span class="sxs-lookup"><span data-stu-id="7b604-104">Visual Studio is a dots per inch (DPI) aware application, which means the display scales automatically.</span></span> <span data-ttu-id="7b604-105">如果应用程序指出它没有感知 DPI，操作系统将缩放应用程序作为位图。</span><span class="sxs-lookup"><span data-stu-id="7b604-105">If an application states that it's not DPI-aware, the operating system scales the application as a bitmap.</span></span> <span data-ttu-id="7b604-106">此行为也被称为 DPI 虚拟化。</span><span class="sxs-lookup"><span data-stu-id="7b604-106">This behavior is also called DPI virtualization.</span></span> <span data-ttu-id="7b604-107">应用程序仍然认为它正以 100%缩放或 96 dpi。</span><span class="sxs-lookup"><span data-stu-id="7b604-107">The application still thinks that it's running at 100% scaling, or 96 dpi.</span></span>

## <a name="windows-forms-designer-on-hdpi-monitors"></a><span data-ttu-id="7b604-108">HDPI 监视器上的 Windows 窗体设计器</span><span class="sxs-lookup"><span data-stu-id="7b604-108">Windows Forms Designer on HDPI monitors</span></span>

<span data-ttu-id="7b604-109">**Windows 窗体设计器**Visual Studio 中不具有缩放支持。</span><span class="sxs-lookup"><span data-stu-id="7b604-109">The **Windows Forms Designer** in Visual Studio doesn't have scaling support.</span></span> <span data-ttu-id="7b604-110">这会导致显示问题时打开中的某些窗体**Windows 窗体设计器**上高点 / 英寸 (HDPI) 监视器。</span><span class="sxs-lookup"><span data-stu-id="7b604-110">This causes display issues when you open some forms in the **Windows Forms Designer** on high dots per inch (HDPI) monitors.</span></span> <span data-ttu-id="7b604-111">有关示例，可以显示控件重叠，如下图中所示：</span><span class="sxs-lookup"><span data-stu-id="7b604-111">For examples, controls can appear to overlap as shown in the following image:</span></span>

![HDPI 监视器上的 Windows 窗体设计器](media/disable-dpi-awareness-visual-studio/win-forms-designer-hdpi.png)

<span data-ttu-id="7b604-113">在 Visual Studio 2017 版本 15.8 及更高版本，当您打开中的窗体**Windows 窗体设计器**的 HDPI 监视器，在 Visual Studio 将在设计器的顶部显示黄色条信息性：</span><span class="sxs-lookup"><span data-stu-id="7b604-113">In Visual Studio 2017 version 15.8 and later, when you open a form in the **Windows Forms Designer** on an HDPI monitor, Visual Studio displays a yellow informational bar at the top of the designer:</span></span>

![在不识别 DPI 的模式下重新启动 Visual Studio 中的信息栏](media/disable-dpi-awareness-visual-studio/scaling-gold-bar.png)

<span data-ttu-id="7b604-115">消息读取**主显示器上的缩放设置为 200%(192 dpi)。这可能导致设计器窗口中的呈现问题。**</span><span class="sxs-lookup"><span data-stu-id="7b604-115">The message reads **Scaling on your main display is set to 200% (192 dpi). This might cause rendering problems in the designer window.**</span></span>

<span data-ttu-id="7b604-116">如果您不能在设计器中工作并不需要调整窗体布局，可以忽略信息栏，并在代码编辑器中或在其他类型的设计器中继续工作。</span><span class="sxs-lookup"><span data-stu-id="7b604-116">If you aren't working in the designer and don't need to adjust the layout of your form, you can ignore the informational bar and continue working in the code editor or in other types of designers.</span></span> <span data-ttu-id="7b604-117">(还可以[禁用通知](#disable-notifications)，以便不会继续显示信息栏。)仅**Windows 窗体设计器**受到影响。</span><span class="sxs-lookup"><span data-stu-id="7b604-117">(You can also [disable notifications](#disable-notifications) so that the informational bar doesn't continue to appear.) Only the **Windows Forms Designer** is affected.</span></span> <span data-ttu-id="7b604-118">如果需要在中工作**Windows 窗体设计器**下, 一步部分可帮助您[解决该问题](#to-resolve-the-problem)。</span><span class="sxs-lookup"><span data-stu-id="7b604-118">If you do need to work in the **Windows Forms Designer**, the next section helps you [resolve the problem](#to-resolve-the-problem).</span></span>

## <a name="to-resolve-the-problem"></a><span data-ttu-id="7b604-119">若要解决此问题</span><span class="sxs-lookup"><span data-stu-id="7b604-119">To resolve the problem</span></span>

<span data-ttu-id="7b604-120">有三个选项，若要解决显示问题的原因。</span><span class="sxs-lookup"><span data-stu-id="7b604-120">There are three options to resolve the display problem.</span></span>

### <a name="restart-visual-studio-as-a-dpi-unaware-process"></a><span data-ttu-id="7b604-121">不识别 DPI 的过程中重新启动 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b604-121">Restart Visual Studio as a DPI-unaware process</span></span>

<span data-ttu-id="7b604-122">您可以重新启动 Visual Studio 作为不识别 DPI 的进程通过选择黄色信息栏上的选项。</span><span class="sxs-lookup"><span data-stu-id="7b604-122">You can restart Visual Studio as a DPI-unaware process by selecting the option on the yellow informational bar.</span></span> <span data-ttu-id="7b604-123">这是解决此问题的首选的方法。</span><span class="sxs-lookup"><span data-stu-id="7b604-123">This is the preferred way of resolving the problem.</span></span>

<span data-ttu-id="7b604-124">Visual Studio 运行时作为不识别 DPI 的进程，设计器布局问题已得到解决，但字体可能显示模糊。</span><span class="sxs-lookup"><span data-stu-id="7b604-124">When Visual Studio runs as a DPI-unaware process, the designer layout issues are resolved, but fonts may appear blurry.</span></span> <span data-ttu-id="7b604-125">Visual Studio 作为说不识别 DPI 的进程运行时将显示不同的黄色条信息性消息**作为不识别 DPI 的进程运行 Visual Studio。WPF 和 XAML 设计器可能无法正常显示。**</span><span class="sxs-lookup"><span data-stu-id="7b604-125">Visual Studio displays a different yellow informational message when it runs as a DPI-unaware process that says **Visual Studio is running as a DPI-unaware process. WPF and XAML designers might not display correctly.**</span></span> <span data-ttu-id="7b604-126">信息栏还提供了一个选项**作为 DPI 感知进程重新启动 Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="7b604-126">The informational bar also provides an option to **Restart Visual Studio as a DPI-aware process**.</span></span>

> [!NOTE]
> - <span data-ttu-id="7b604-127">如果选择不识别 DPI 的过程中重新启动的选项时，必须取消停靠在 Visual Studio 中的工具窗口，可能会更改这些工具窗口的位置。</span><span class="sxs-lookup"><span data-stu-id="7b604-127">If you had undocked tool windows in Visual Studio when you selected the option to restart as a DPI-unaware process, the position of those tool windows may change.</span></span>
> - <span data-ttu-id="7b604-128">如果使用默认的 Visual Basic 配置文件，或者你有**保存新项目时创建**中取消选择选项**工具** > **选项** > **项目和解决方案**，作为不识别 DPI 的进程重新启动时，Visual Studio 无法重新打开你的项目。</span><span class="sxs-lookup"><span data-stu-id="7b604-128">If you use the default Visual Basic profile, or if you have the **Save new projects when created** option deselected in **Tools** > **Options** > **Projects and Solutions**, Visual Studio cannot reopen your project when it restarts as a DPI-unaware process.</span></span> <span data-ttu-id="7b604-129">但是，可以通过选择下打开该项目**文件** > **最近使用的项目和解决方案**。</span><span class="sxs-lookup"><span data-stu-id="7b604-129">However, you can open the project by selecting it under **File** > **Recent Projects and Solutions**.</span></span>

<span data-ttu-id="7b604-130">务必要完成其中的工作作为 DPI 感知进程重新启动 Visual Studio **Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="7b604-130">It's important to restart Visual Studio as a DPI-aware process when you're finished working in the **Windows Forms Designer**.</span></span> <span data-ttu-id="7b604-131">它作为运行时不识别 DPI 的过程，字体可以看起来很模糊和你可能会看到其他设计器中的问题，如**XAML 设计器**。</span><span class="sxs-lookup"><span data-stu-id="7b604-131">When it's running as a DPI-unaware process, fonts can look blurry and you may see issues in other designers such as the **XAML Designer**.</span></span> <span data-ttu-id="7b604-132">如果关闭并重新打开 Visual Studio，在不识别 DPI 的模式下运行时，它将成为 DPI 感知试。</span><span class="sxs-lookup"><span data-stu-id="7b604-132">If you close and reopen Visual Studio when it's running in DPI-unaware mode, it becomes DPI-aware again.</span></span> <span data-ttu-id="7b604-133">此外可以单击**作为 DPI 感知进程重新启动 Visual Studio**信息栏中的选项。</span><span class="sxs-lookup"><span data-stu-id="7b604-133">You can also click the **Restart Visual Studio as a DPI-aware process** option in the informational bar.</span></span>

### <a name="add-a-registry-entry"></a><span data-ttu-id="7b604-134">添加一个注册表项</span><span class="sxs-lookup"><span data-stu-id="7b604-134">Add a registry entry</span></span>

<span data-ttu-id="7b604-135">通过修改注册表，你可以将 Visual Studio 标记为 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="7b604-135">You can mark Visual Studio as DPI-unaware by modifying the registry.</span></span> <span data-ttu-id="7b604-136">打开**注册表编辑器**并添加到一个条目**通过 NT\CurrentVersion\AppCompatFlags\Layers**子项：</span><span class="sxs-lookup"><span data-stu-id="7b604-136">Open **Registry Editor** and add an entry to the **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers** subkey:</span></span>

<span data-ttu-id="7b604-137">**条目**:C:\Program 文件 (x86) \Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe</span><span class="sxs-lookup"><span data-stu-id="7b604-137">**Entry**: C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\devenv.exe</span></span>

   > [!NOTE]
   > <span data-ttu-id="7b604-138">如果您使用的 Professional 或 Enterprise 版的 Visual Studio 2017，替换**社区**与**Professional**或**企业**条目中。</span><span class="sxs-lookup"><span data-stu-id="7b604-138">If you're using the Professional or Enterprise edition of Visual Studio 2017, replace **Community** with **Professional** or **Enterprise** in the entry.</span></span> <span data-ttu-id="7b604-139">此外将根据需要驱动器号。</span><span class="sxs-lookup"><span data-stu-id="7b604-139">Also replace the drive letter as necessary.</span></span>

<span data-ttu-id="7b604-140">**类型**:REG_SZ</span><span class="sxs-lookup"><span data-stu-id="7b604-140">**Type**: REG_SZ</span></span>

<span data-ttu-id="7b604-141">**值**:DPIUNAWARE</span><span class="sxs-lookup"><span data-stu-id="7b604-141">**Value**: DPIUNAWARE</span></span>

> [!NOTE]
> <span data-ttu-id="7b604-142">Visual Studio 仍保持不识别 DPI 的模式，直到删除注册表项。</span><span class="sxs-lookup"><span data-stu-id="7b604-142">Visual Studio remains in DPI-unaware mode until you remove the registry entry.</span></span>

### <a name="set-your-display-scaling-setting-to-100"></a><span data-ttu-id="7b604-143">将缩放到 100%的设置显示设置</span><span class="sxs-lookup"><span data-stu-id="7b604-143">Set your display scaling setting to 100%</span></span>

<span data-ttu-id="7b604-144">若要设置您的显示设置为 100%缩放 Windows 10 中，键入**显示设置**在搜索框中，然后选择任务栏**更改显示设置**。</span><span class="sxs-lookup"><span data-stu-id="7b604-144">To set your display scaling setting to 100% in Windows 10, type **display settings** in the task bar search box, and then select **Change display settings**.</span></span> <span data-ttu-id="7b604-145">在中**设置**窗口中，将**更改的文本、 应用和其他项大小**到**100%**。</span><span class="sxs-lookup"><span data-stu-id="7b604-145">In the **Settings** window, set **Change the size of text, apps, and other items** to **100%**.</span></span>

<span data-ttu-id="7b604-146">缩放到 100%将显示设置可能不希望如此，因为这可以使用户界面太小，才能使用。</span><span class="sxs-lookup"><span data-stu-id="7b604-146">Setting your display scaling to 100% may be undesirable, because it can make the user interface too small to be usable.</span></span>

## <a name="disable-notifications"></a><span data-ttu-id="7b604-147">禁用通知</span><span class="sxs-lookup"><span data-stu-id="7b604-147">Disable notifications</span></span>

<span data-ttu-id="7b604-148">您可以选择不通知的 DPI 缩放在 Visual Studio 中的问题。</span><span class="sxs-lookup"><span data-stu-id="7b604-148">You can choose not to be notified of DPI scaling issues in Visual Studio.</span></span> <span data-ttu-id="7b604-149">你可能想要禁用通知，如果您未使用在设计器中，例如。</span><span class="sxs-lookup"><span data-stu-id="7b604-149">You might want to disable notifications if you aren't working in the designer, for example.</span></span>

<span data-ttu-id="7b604-150">若要禁用通知，请选择**工具** > **选项**以打开**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="7b604-150">To disable notifications, choose **Tools** > **Options** to open the **Options** dialog.</span></span> <span data-ttu-id="7b604-151">然后，选择**Windows 窗体设计器** > **常规**，并设置**DPI 缩放通知**到**False**。</span><span class="sxs-lookup"><span data-stu-id="7b604-151">Then, choose **Windows Forms Designer** > **General**, and set **DPI Scaling Notifications** to **False**.</span></span>

![DPI 缩放在 Visual Studio 中的通知选项](media/disable-dpi-awareness-visual-studio/notifications-option.png)

<span data-ttu-id="7b604-153">如果你想要以后重新启用缩放通知，将属性设置为 **，则返回 True**。</span><span class="sxs-lookup"><span data-stu-id="7b604-153">If you want to later reenable scaling notifications, set the property to **True**.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="7b604-154">疑难解答</span><span class="sxs-lookup"><span data-stu-id="7b604-154">Troubleshoot</span></span>

<span data-ttu-id="7b604-155">如果 Visual Studio 中的预期，DPI 识别转换不起作用，检查以查看是否有`dpiAwareness`中的值**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image 文件执行 Options\devenv.exe**子项在注册表编辑器中。</span><span class="sxs-lookup"><span data-stu-id="7b604-155">If the DPI-awareness transition isn't working as expected in Visual Studio, check to see if you have the `dpiAwareness` value in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\devenv.exe** subkey in Registry Editor.</span></span> <span data-ttu-id="7b604-156">如果存在，请删除值。</span><span class="sxs-lookup"><span data-stu-id="7b604-156">Delete the value if it's present.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b604-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b604-157">See also</span></span>

- [<span data-ttu-id="7b604-158">Windows 窗体中的自动缩放</span><span class="sxs-lookup"><span data-stu-id="7b604-158">Automatic scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
