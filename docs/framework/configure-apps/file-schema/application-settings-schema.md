---
title: 应用程序设置架构
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 89a08434332b0242fe57e9dcaa3b3ebcc5692d06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927765"
---
# <a name="application-settings-schema"></a>应用程序设置架构

应用程序设置允许 Windows 窗体或 ASP.NET 应用程序存储和检索应用程序范围的设置和用户范围的设置。 在此上下文中,*设置*是指特定于应用程序或特定于当前用户的任何信息, 包括从数据库连接字符串到用户首选默认窗口大小的任何信息。

默认情况下, Windows 窗体应用程序中的应用程序<xref:System.Configuration.LocalFileSettingsProvider>设置使用类, 该类使用 .net 配置系统将设置存储在 XML 配置文件中。 有关应用程序设置使用的文件的详细信息, 请参阅[应用程序设置体系结构](../../winforms/advanced/application-settings-architecture.md)。

应用程序设置将以下元素定义为它所使用的配置文件的一部分。

| 元素                    | 描述                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | 包含所有 **\<设置>** 标记特定于应用程序。                         |
| **\<userSettings>**        | 包含所有 **\<设置>** 特定于当前用户的标记。                        |
| **\<setting>**             | 定义设置。 ApplicationSettings 的 **\<子级 >** 或 **\<userSettings >** 。 |
| **\<value>**               | 定义设置的值。 子级 **\<设置>** 。                                   |

## <a name="applicationsettings-element"></a>\<applicationSettings > 元素

此元素包含所有 **\<设置>** 特定于客户端计算机上的应用程序的实例的标记。 未定义任何属性。

## <a name="usersettings-element"></a>\<userSettings > 元素

此元素包含所有 **\<设置>** 特定于当前正在使用该应用程序的用户的标记。 未定义任何属性。

## <a name="setting-element"></a>\<设置 > 元素

此元素定义一个设置。 它具有以下属性。

| 特性        | 描述 |
| ---------------- | ----------- |
| **名称**         | 必需。 设置的唯一 ID。 使用名称`ProjectName.Properties.Settings`保存通过 Visual Studio 创建的设置。 |
| **serializedAs** | 必需。 将值序列化为文本时要使用的格式。 有效值包括：<br><br>- `string`. 该值使用<xref:System.ComponentModel.TypeConverter>来序列化为字符串。<br>- `xml`. 使用 XML 序列化对值进行序列化。<br>- `binary`. 使用二进制序列化将值作为文本编码的二进制序列化。<br />- `custom`. 设置提供程序具有此设置的固有知识, 并对其进行序列化和反序列化。 |

## <a name="value-element"></a>\<值 > 元素

此元素包含设置的值。

## <a name="example"></a>示例

以下示例显示了一个应用程序设置文件, 该文件定义了两个应用程序范围的设置和两个用户范围的设置:

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

## <a name="see-also"></a>请参阅

- [应用程序设置概述](../../winforms/advanced/application-settings-overview.md)
- [应用程序设置体系结构](../../winforms/advanced/application-settings-architecture.md)
