---
title: 应用程序设置架构
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242824"
---
# <a name="application-settings-schema"></a>应用程序设置架构

应用程序设置允许 Windows 窗体或ASP.NET应用程序存储和检索应用程序范围和用户范围的设置。 在此上下文中，*设置*是可能特定于应用程序或特定于当前用户的任何信息 - 从数据库连接字符串到用户首选默认窗口大小的任何信息。

默认情况下，Windows 窗体应用程序中的应用程序设置使用<xref:System.Configuration.LocalFileSettingsProvider>类，该类使用 .NET 配置系统在 XML 配置文件中存储设置。 有关应用程序设置使用的文件的详细信息，请参阅[应用程序设置体系结构](../../winforms/advanced/application-settings-architecture.md)。

应用程序设置将以下元素定义为它使用的配置文件的一部分。

| 元素                    | 描述                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<应用程序设置>** | 包含特定于应用程序**\<的所有设置>** 标记。                         |
| **\<用户设置>**        | 包含特定于当前用户**\<的所有设置>** 标记。                        |
| **\<设置>**             | 定义设置。 **\<应用程序>或****\<用户设置的子项>。 ** |
| **\<值>**               | 定义设置的值。 **\<设置>** 的子项。                                   |

## <a name="applicationsettings-element"></a>\<应用程序设置>元素

此元素包含特定于客户端计算机上的应用程序实例的所有**\<设置>** 标记。 未定义任何属性。

## <a name="usersettings-element"></a>\<用户设置>元素

此元素包含特定于当前使用该应用程序的用户的所有**\<设置>** 标记。 未定义任何属性。

## <a name="setting-element"></a>\<设置>元素

此元素定义设置。 它具有以下属性。

| 特性        | 说明 |
| ---------------- | ----------- |
| name          | 必需。 设置的唯一 ID。 通过可视化工作室创建的设置将保存与名称`ProjectName.Properties.Settings`。 |
| **序列化** | 必需。 用于序列化文本值的格式。 有效值是：<br><br>- `string`. 该值使用 序列化为字符串。 <xref:System.ComponentModel.TypeConverter><br>- `xml`. 该值使用 XML 序列化进行序列化。<br>- `binary`. 该值使用二进制序列化将该值序列化为文本编码二进制。<br />- `custom`. 设置提供程序对此设置有固有的知识，并序列化并取消序列化。 |

## <a name="value-element"></a>\<值>元素

此元素包含设置的值。

## <a name="example"></a>示例

下面的示例显示了一个应用程序设置文件，该文件定义了两个应用程序范围设置和两个用户范围设置：

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a>另请参阅

- [应用程序设置概述](../../winforms/advanced/application-settings-overview.md)
- [应用程序设置体系结构](../../winforms/advanced/application-settings-architecture.md)
