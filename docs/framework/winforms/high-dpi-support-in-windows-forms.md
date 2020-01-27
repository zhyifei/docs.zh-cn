---
title: 높은 DPI 지원
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
ms.openlocfilehash: a5c3125475c2de2cf83a3d97e356b26c0acdde99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741895"
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="4c7f8-102">Windows 窗体中的高 DPI 支持</span><span class="sxs-lookup"><span data-stu-id="4c7f8-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="4c7f8-103">从 .NET Framework 4.7 开始，Windows 窗体包括常见高 DPI 和动态 DPI 方案的增强功能。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="4c7f8-104">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c7f8-104">These include:</span></span>

- <span data-ttu-id="4c7f8-105">改进了许多 Windows 窗体控件（如 <xref:System.Windows.Forms.MonthCalendar> 控件和 <xref:System.Windows.Forms.CheckedListBox> 控件）的缩放和布局。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="4c7f8-106">单步缩放。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-106">Single-pass scaling.</span></span>  <span data-ttu-id="4c7f8-107">在 .NET Framework 4.6 及更早版本中，缩放是通过多个走刀执行的，这会导致某些控件的缩放比例超出了必需。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="4c7f8-108">支持动态 DPI 方案，在此方案中，用户在启动 Windows 窗体应用程序后更改了 DPI 或缩放系数。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="4c7f8-109">从 .NET Framework 4.7 开始 .NET Framework 版本中，增强的高 DPI 支持是一项可选功能。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="4c7f8-110">您必须将应用程序配置为利用它。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="4c7f8-111">配置 Windows 窗体应用以实现高 DPI 支持</span><span class="sxs-lookup"><span data-stu-id="4c7f8-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="4c7f8-112">支持高 DPI 感知的新 Windows 窗体功能仅在面向 .NET Framework 4.7 的应用程序中提供，并且在从 Windows 10 创意者更新开始的 Windows 操作系统上运行。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="4c7f8-113">此外，若要在 Windows 窗体应用程序中配置高 DPI 支持，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4c7f8-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="4c7f8-114">声明与 Windows 10 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="4c7f8-115">为此，请将以下内容添加到清单文件中：</span><span class="sxs-lookup"><span data-stu-id="4c7f8-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="4c7f8-116">启用*app.config*文件中的按监视器 DPI 感知。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="4c7f8-117">Windows 窗体引入了新的[`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md)元素，以支持从 .NET Framework 4.7 开始添加的新功能和自定义项。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="4c7f8-118">若要利用支持高 DPI 的新功能，请将以下项添加到应用程序配置文件中。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="4c7f8-119">在以前版本的 .NET Framework 中，你使用了清单来添加高 DPI 支持。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="4c7f8-120">不再建议使用此方法，因为它会覆盖对 app.config 文件定义的设置。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="4c7f8-121">调用静态 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="4c7f8-122">这应该是应用程序入口点中的第一个方法调用。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="4c7f8-123">예를 들면 다음과 같습니다.:</span><span class="sxs-lookup"><span data-stu-id="4c7f8-123">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="4c7f8-124">退出单个高 DPI 功能</span><span class="sxs-lookup"><span data-stu-id="4c7f8-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="4c7f8-125">将 `DpiAwareness` 值设置为 "`PerMonitorV2` 将启用从 .NET Framework 4.7 开始 .NET Framework 版本支持的所有高 DPI 感知功能。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="4c7f8-126">通常，这适用于大多数 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="4c7f8-127">但是，你可能想要选择不提供一个或多个单独的功能。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="4c7f8-128">执行此操作的最重要的原因是您的现有应用程序代码已经处理了该功能。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="4c7f8-129">例如，如果你的应用程序处理自动缩放，则你可能想要禁用自动调整大小功能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c7f8-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="4c7f8-130">有关各个键及其值的列表，请参阅[Windows 窗体添加配置元素](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="4c7f8-131">新的 DPI 更改事件</span><span class="sxs-lookup"><span data-stu-id="4c7f8-131">New DPI change events</span></span>

<span data-ttu-id="4c7f8-132">从 .NET Framework 4.7 开始，三个新事件允许以编程方式处理动态 DPI 更改：</span><span class="sxs-lookup"><span data-stu-id="4c7f8-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="4c7f8-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>，当控件的 DPI 设置在其父控件或窗体的 DPI 更改事件发生后以编程方式发生更改时，将激发此事件。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="4c7f8-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>，当控件的 DPI 设置在其父控件或窗体的 DPI 更改事件发生之前以编程方式进行更改时，将激发此事件。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="4c7f8-135"><xref:System.Windows.Forms.Form.DpiChanged>，在当前显示窗体的显示设备上的 DPI 设置更改时激发。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="4c7f8-136">新的帮助器方法和属性</span><span class="sxs-lookup"><span data-stu-id="4c7f8-136">New helper methods and properties</span></span>

<span data-ttu-id="4c7f8-137">.NET Framework 4.7 还添加了一些新的帮助器方法和属性，这些方法和属性提供了有关 DPI 缩放的信息，并允许您执行 DPI 缩放。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="4c7f8-138">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c7f8-138">These include:</span></span>

- <span data-ttu-id="4c7f8-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>，它将值从逻辑到设备像素转换。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="4c7f8-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>，它将位图图像缩放为设备的逻辑 DPI。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="4c7f8-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>，它返回当前设备的 DPI。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="4c7f8-142">版本控制注意事项</span><span class="sxs-lookup"><span data-stu-id="4c7f8-142">Versioning considerations</span></span>

<span data-ttu-id="4c7f8-143">除了在 .NET Framework 4.7 和 Windows 10 创意者更新上运行以外，应用程序还可以在与高 DPI 改进不兼容的环境中运行。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="4c7f8-144">在这种情况下，需要为应用程序开发回退。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="4c7f8-145">你可以执行此操作来执行[自定义绘图](./controls/user-drawn-controls.md)来处理缩放。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="4c7f8-146">为此，还需要确定运行应用的操作系统。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="4c7f8-147">可以用如下代码来实现：</span><span class="sxs-lookup"><span data-stu-id="4c7f8-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="4c7f8-148">请注意，如果 Windows 10 未在应用程序清单中列出为受支持的操作系统，则你的应用程序不会成功检测到它。</span><span class="sxs-lookup"><span data-stu-id="4c7f8-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="4c7f8-149">你还可以查看生成应用程序所针对的 .NET Framework 的版本：</span><span class="sxs-lookup"><span data-stu-id="4c7f8-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="4c7f8-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c7f8-150">See also</span></span>

- [<span data-ttu-id="4c7f8-151">Windows 窗体添加配置元素</span><span class="sxs-lookup"><span data-stu-id="4c7f8-151">Windows Forms Add Configuration Element</span></span>](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="4c7f8-152">Windows Forms의 크기 및 배율 조정</span><span class="sxs-lookup"><span data-stu-id="4c7f8-152">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
