---
title: Windows 窗体中的高 DPI 支持
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbf2d7b61b34a2cd4641a77ee1f2fcdff7f3c3fe
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2018
---
# <a name="high-dpi-support-in-windows-forms"></a>Windows 窗体中的高 DPI 支持

从.NET Framework 4.7 开始，Windows 窗体包括增强功能的常见高 DPI 和动态 DPI 方案。 这些方法包括： 

- 缩放和多个 Windows 窗体的布局中的改进控件，如<xref:System.Windows.Forms.MonthCalendar>控件和<xref:System.Windows.Forms.CheckedListBox>控件。 

- 缩放的单个传递。  在.NET Framework 4.6 和早期版本中，通过多个通过，这导致某些控件可按比例超过时需要执行缩放。

- 动态 Windows 窗体应用程序已启动后用户更改的 DPI 或缩放系数的 DPI 方案的支持。

在从.NET Framework 4.7 的.NET framework 的版本，增强高 DPI 支持是一项可以选择使用的功能。 你必须配置应用程序以充分利用它。

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>配置 Windows 窗体应用程序以高 DPI 支持

支持高 DPI 感知的新 Windows 窗体功能是仅在面向.NET Framework 4.7 和从 Windows 10 创建者更新开始的 Windows 操作系统上运行的应用程序中可用。 

此外，若要在 Windows 窗体应用程序中配置高 DPI 支持，你必须执行以下操作：

- 声明与 Windows 10 的兼容性。

  为此，请将以下添加到你的清单文件：

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- 启用中的每个监视器 DPI 感知*app.config*文件。

  Windows 窗体引入了新[ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md)元素以支持新功能和自定义项添加从.NET Framework 4.7 开始。 若要利用支持高 DPI 的新功能，请将以下添加到应用程序配置文件。   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > 在以前版本的.NET Framework 中，你可以使用清单来添加高 DPI 支持。 不再建议使用此方法，因为它会替代在 app.config 文件中定义的设置。
   
- 调用静态<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>方法。
   
  这应该是你的应用程序入口点中的第一个方法调用。 例如：
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>选择退出各个高 DPI 功能

设置`DpiAwareness`值赋给`PerMonitorV2`使支持的.NET Framework 4.7 开头的.NET Framework 版本的所有高 DPI 感知功能。 通常情况下，这足以满足大多数 Windows 窗体应用程序。 但是，你可能想要选择取消一个或多个各项功能。 执行此操作的最重要原因是现有的应用程序代码已经处理该功能。  例如，如果你的应用程序处理自动缩放，你可能想要禁用自动调整大小功能，如下所示：

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

有关各个键及其值的列表，请参阅[Windows 窗体添加配置元素](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)。

## <a name="new-dpi-change-events"></a>新的 DPI 更改事件

从.NET Framework 4.7 开始，三个新事件允许你以编程方式处理动态 DPI 更改：

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>这在父控件的 DPI 更改事件后已以编程方式更改控件的 DPI 设置或窗体发生时激发。
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>其中在控件的 DPI 设置已在其父控件的 DPI 更改事件之前以编程方式更改，或窗体发生时被激发。
- <xref:System.Windows.Forms.Form.DpiChanged>其中 DPI 设置更改，则当前显示的格式显示设备上时激发。

## <a name="new-helper-methods-and-properties"></a>新的帮助器方法和属性

.NET Framework 4.7 还添加了大量新的帮助器方法和属性，提供有关 DPI 缩放信息，并允许你执行 DPI 缩放比例。 这些方法包括：

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>它将值从逻辑转换为设备像素为单位。

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>其缩放到设备的逻辑 DPI 位图图像。

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>它返回有关当前设备 DPI。

## <a name="versioning-considerations"></a>版本控制注意事项

除了在.NET Framework 4.7 和 Windows 10 创建者更新上运行，你的应用程序可能还在环境中运行它不与高 DPI 改进兼容。 在这种情况下，你将需要开发的应用程序的回退。 你可以这样做来执行[自定义绘制](./controls/user-drawn-controls.md)来处理缩放。

若要执行此操作，还需要确定你的应用程序正在其运行的操作系统。 你可以实现与代码如下所示：

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

请注意，是否它未被列出为应用程序清单中受支持的操作系统，你的应用程序不会成功检测 Windows 10。

你还可以检查生成应用程序所针对的.NET framework 版本：

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>请参阅

[Windows 窗体添加配置元素](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)  
[调整 Windows 窗体的大小和比例](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
