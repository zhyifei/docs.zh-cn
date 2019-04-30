---
title: 在 Windows 窗体中的高 DPI 支持
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1641702c7b1c3d3b0e83c59a96529de70f699d17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966932"
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="66304-102">在 Windows 窗体中的高 DPI 支持</span><span class="sxs-lookup"><span data-stu-id="66304-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="66304-103">从.NET Framework 4.7 开始，Windows 窗体包括增强功能的常见高 DPI 和动态 DPI 方案。</span><span class="sxs-lookup"><span data-stu-id="66304-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="66304-104">这些问题包括：</span><span class="sxs-lookup"><span data-stu-id="66304-104">These include:</span></span>

- <span data-ttu-id="66304-105">改进的缩放和多个 Windows 窗体的布局控件，如<xref:System.Windows.Forms.MonthCalendar>控件和<xref:System.Windows.Forms.CheckedListBox>控件。</span><span class="sxs-lookup"><span data-stu-id="66304-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="66304-106">单次传递缩放。</span><span class="sxs-lookup"><span data-stu-id="66304-106">Single-pass scaling.</span></span>  <span data-ttu-id="66304-107">在.NET Framework 4.6 和更早版本中，通过多个通过，这导致一些控件，以扩展超过需要执行缩放。</span><span class="sxs-lookup"><span data-stu-id="66304-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="66304-108">对 Windows 窗体应用程序已启动后在用户更改 DPI 或缩放系数的动态 DPI 方案的支持。</span><span class="sxs-lookup"><span data-stu-id="66304-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="66304-109">在版本的.NET Framework 从.NET Framework 4.7 开始，增强了高 DPI 支持是可选功能。</span><span class="sxs-lookup"><span data-stu-id="66304-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="66304-110">必须配置应用程序以充分利用它。</span><span class="sxs-lookup"><span data-stu-id="66304-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="66304-111">高 DPI 支持在 Windows 窗体应用中配置</span><span class="sxs-lookup"><span data-stu-id="66304-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="66304-112">支持高 DPI 识别的新 Windows 窗体功能是仅在面向.NET Framework 4.7 和从 Windows 10 创意者更新的 Windows 操作系统上运行的应用程序中可用。</span><span class="sxs-lookup"><span data-stu-id="66304-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="66304-113">此外，若要在 Windows 窗体应用程序中配置高 DPI 支持，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="66304-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="66304-114">声明与 Windows 10 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="66304-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="66304-115">若要执行此操作，以下代码添加到清单文件：</span><span class="sxs-lookup"><span data-stu-id="66304-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="66304-116">启用中的每监视器 DPI 感知*app.config*文件。</span><span class="sxs-lookup"><span data-stu-id="66304-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="66304-117">Windows 窗体引入了一个新[ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../configure-apps/file-schema/winforms/index.md)元素以支持新功能和自定义项添加从.NET Framework 4.7 开始。</span><span class="sxs-lookup"><span data-stu-id="66304-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="66304-118">若要充分利用支持高 DPI 的新功能，以下代码添加到应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="66304-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="66304-119">在以前版本的.NET Framework，您可以使用清单添加高 DPI 支持。</span><span class="sxs-lookup"><span data-stu-id="66304-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="66304-120">不再建议使用此方法，因为它会替代 app.config 文件中定义的设置。</span><span class="sxs-lookup"><span data-stu-id="66304-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="66304-121">调用静态<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="66304-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="66304-122">这应该是应用程序的入口点中的第一个方法调用。</span><span class="sxs-lookup"><span data-stu-id="66304-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="66304-123">例如：</span><span class="sxs-lookup"><span data-stu-id="66304-123">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="66304-124">选择退出各个高 DPI 功能</span><span class="sxs-lookup"><span data-stu-id="66304-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="66304-125">设置`DpiAwareness`值设为`PerMonitorV2`使支持的.NET Framework 版本从.NET Framework 4.7 开始的所有高 DPI 感知功能。</span><span class="sxs-lookup"><span data-stu-id="66304-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="66304-126">通常情况下，这是适合大多数 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="66304-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="66304-127">但是，你可能想要选择退出一个或多个单独的功能。</span><span class="sxs-lookup"><span data-stu-id="66304-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="66304-128">执行此操作的最重要的原因是，现有的应用程序代码已处理该功能。</span><span class="sxs-lookup"><span data-stu-id="66304-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="66304-129">例如，如果你的应用程序处理自动缩放，你可能想要禁用自动调整大小功能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="66304-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="66304-130">有关各个键及其值的列表，请参阅[Windows 窗体添加配置元素](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)。</span><span class="sxs-lookup"><span data-stu-id="66304-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="66304-131">新 DPI 更改事件</span><span class="sxs-lookup"><span data-stu-id="66304-131">New DPI change events</span></span>

<span data-ttu-id="66304-132">从.NET Framework 4.7 开始，三个新事件使您能够以编程方式处理动态 DPI 更改：</span><span class="sxs-lookup"><span data-stu-id="66304-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="66304-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>其父控件的 DPI 更改事件之后以编程方式更改控件的 DPI 设置或窗体已发生时激发。</span><span class="sxs-lookup"><span data-stu-id="66304-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="66304-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>这在其父控件的 DPI 更改事件之前以编程方式更改控件的 DPI 设置或窗体已发生时被激发。</span><span class="sxs-lookup"><span data-stu-id="66304-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="66304-135"><xref:System.Windows.Forms.Form.DpiChanged>这当前显示窗体的显示设备上的 DPI 设置更改时激发。</span><span class="sxs-lookup"><span data-stu-id="66304-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="66304-136">新的帮助器方法和属性</span><span class="sxs-lookup"><span data-stu-id="66304-136">New helper methods and properties</span></span>

<span data-ttu-id="66304-137">.NET Framework 4.7 也将添加大量新的帮助器方法和属性，提供有关 DPI 缩放信息，可用于执行 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="66304-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="66304-138">这些问题包括：</span><span class="sxs-lookup"><span data-stu-id="66304-138">These include:</span></span>

- <span data-ttu-id="66304-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>其中将一个值，从逻辑转换为设备像素为单位。</span><span class="sxs-lookup"><span data-stu-id="66304-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="66304-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>这可以扩展到设备的逻辑 DPI 的位图图像。</span><span class="sxs-lookup"><span data-stu-id="66304-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="66304-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>它将返回当前设备的 DPI。</span><span class="sxs-lookup"><span data-stu-id="66304-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="66304-142">版本控制考虑事项</span><span class="sxs-lookup"><span data-stu-id="66304-142">Versioning considerations</span></span>

<span data-ttu-id="66304-143">除了.NET Framework 4.7 和 Windows 10 创意者更新上运行，你的应用程序还可能会运行它不与高 DPI 改进兼容的环境中。</span><span class="sxs-lookup"><span data-stu-id="66304-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="66304-144">在这种情况下，你将需要开发的应用程序回退。</span><span class="sxs-lookup"><span data-stu-id="66304-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="66304-145">你可以执行[自定义绘图](./controls/user-drawn-controls.md)来处理缩放。</span><span class="sxs-lookup"><span data-stu-id="66304-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="66304-146">若要执行此操作，还需要确定您的应用程序正在其运行的操作系统。</span><span class="sxs-lookup"><span data-stu-id="66304-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="66304-147">可以使用如下所示的代码执行的操作：</span><span class="sxs-lookup"><span data-stu-id="66304-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="66304-148">请注意，是否未列出的应用程序清单中受支持的操作系统，你的应用程序不会成功检测 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="66304-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="66304-149">此外可以检查生成应用程序时所针对的.NET framework 版本：</span><span class="sxs-lookup"><span data-stu-id="66304-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="66304-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="66304-150">See also</span></span>

- [<span data-ttu-id="66304-151">Windows 窗体添加配置元素</span><span class="sxs-lookup"><span data-stu-id="66304-151">Windows Forms Add Configuration Element</span></span>](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="66304-152">调整 Windows 窗体的大小和比例</span><span class="sxs-lookup"><span data-stu-id="66304-152">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
