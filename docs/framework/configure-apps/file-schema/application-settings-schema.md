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
# <a name="application-settings-schema"></a><span data-ttu-id="5c3d3-102">应用程序设置架构</span><span class="sxs-lookup"><span data-stu-id="5c3d3-102">Application Settings schema</span></span>

<span data-ttu-id="5c3d3-103">应用程序设置允许 Windows 窗体或ASP.NET应用程序存储和检索应用程序范围和用户范围的设置。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="5c3d3-104">在此上下文中，*设置*是可能特定于应用程序或特定于当前用户的任何信息 - 从数据库连接字符串到用户首选默认窗口大小的任何信息。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="5c3d3-105">默认情况下，Windows 窗体应用程序中的应用程序设置使用<xref:System.Configuration.LocalFileSettingsProvider>类，该类使用 .NET 配置系统在 XML 配置文件中存储设置。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="5c3d3-106">有关应用程序设置使用的文件的详细信息，请参阅[应用程序设置体系结构](../../winforms/advanced/application-settings-architecture.md)。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="5c3d3-107">应用程序设置将以下元素定义为它使用的配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="5c3d3-108">元素</span><span class="sxs-lookup"><span data-stu-id="5c3d3-108">Element</span></span>                    | <span data-ttu-id="5c3d3-109">描述</span><span class="sxs-lookup"><span data-stu-id="5c3d3-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="5c3d3-110">**\<应用程序设置>**</span><span class="sxs-lookup"><span data-stu-id="5c3d3-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="5c3d3-111">包含特定于应用程序**\<的所有设置>** 标记。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="5c3d3-112">**\<用户设置>**</span><span class="sxs-lookup"><span data-stu-id="5c3d3-112">**\<userSettings>**</span></span>        | <span data-ttu-id="5c3d3-113">包含特定于当前用户**\<的所有设置>** 标记。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="5c3d3-114">**\<设置>**</span><span class="sxs-lookup"><span data-stu-id="5c3d3-114">**\<setting>**</span></span>             | <span data-ttu-id="5c3d3-115">定义设置。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-115">Defines a setting.</span></span> <span data-ttu-id="5c3d3-116">\*\*\<应用程序>或\*\*\*\*\<用户设置的子项>。 \*\*</span><span class="sxs-lookup"><span data-stu-id="5c3d3-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="5c3d3-117">**\<值>**</span><span class="sxs-lookup"><span data-stu-id="5c3d3-117">**\<value>**</span></span>               | <span data-ttu-id="5c3d3-118">定义设置的值。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-118">Defines a setting's value.</span></span> <span data-ttu-id="5c3d3-119">**\<设置>** 的子项。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="5c3d3-120">\<应用程序设置>元素</span><span class="sxs-lookup"><span data-stu-id="5c3d3-120">\<applicationSettings> element</span></span>

<span data-ttu-id="5c3d3-121">此元素包含特定于客户端计算机上的应用程序实例的所有**\<设置>** 标记。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="5c3d3-122">未定义任何属性。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="5c3d3-123">\<用户设置>元素</span><span class="sxs-lookup"><span data-stu-id="5c3d3-123">\<userSettings> element</span></span>

<span data-ttu-id="5c3d3-124">此元素包含特定于当前使用该应用程序的用户的所有**\<设置>** 标记。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="5c3d3-125">未定义任何属性。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="5c3d3-126">\<设置>元素</span><span class="sxs-lookup"><span data-stu-id="5c3d3-126">\<setting> element</span></span>

<span data-ttu-id="5c3d3-127">此元素定义设置。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-127">This element defines a setting.</span></span> <span data-ttu-id="5c3d3-128">它具有以下属性。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-128">It has the following attributes.</span></span>

| <span data-ttu-id="5c3d3-129">特性</span><span class="sxs-lookup"><span data-stu-id="5c3d3-129">Attribute</span></span>        | <span data-ttu-id="5c3d3-130">说明</span><span class="sxs-lookup"><span data-stu-id="5c3d3-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="5c3d3-131">name </span><span class="sxs-lookup"><span data-stu-id="5c3d3-131">**name**</span></span>         | <span data-ttu-id="5c3d3-132">必需。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-132">Required.</span></span> <span data-ttu-id="5c3d3-133">设置的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-133">The unique ID of the setting.</span></span> <span data-ttu-id="5c3d3-134">通过可视化工作室创建的设置将保存与名称`ProjectName.Properties.Settings`。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="5c3d3-135">**序列化**</span><span class="sxs-lookup"><span data-stu-id="5c3d3-135">**serializeAs**</span></span> | <span data-ttu-id="5c3d3-136">必需。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-136">Required.</span></span> <span data-ttu-id="5c3d3-137">用于序列化文本值的格式。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="5c3d3-138">有效值是：</span><span class="sxs-lookup"><span data-stu-id="5c3d3-138">Valid values are:</span></span><br><br><span data-ttu-id="5c3d3-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="5c3d3-139">- `string`.</span></span> <span data-ttu-id="5c3d3-140">该值使用 序列化为字符串。 <xref:System.ComponentModel.TypeConverter></span><span class="sxs-lookup"><span data-stu-id="5c3d3-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="5c3d3-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="5c3d3-141">- `xml`.</span></span> <span data-ttu-id="5c3d3-142">该值使用 XML 序列化进行序列化。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="5c3d3-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="5c3d3-143">- `binary`.</span></span> <span data-ttu-id="5c3d3-144">该值使用二进制序列化将该值序列化为文本编码二进制。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="5c3d3-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="5c3d3-145">- `custom`.</span></span> <span data-ttu-id="5c3d3-146">设置提供程序对此设置有固有的知识，并序列化并取消序列化。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="5c3d3-147">\<值>元素</span><span class="sxs-lookup"><span data-stu-id="5c3d3-147">\<value> element</span></span>

<span data-ttu-id="5c3d3-148">此元素包含设置的值。</span><span class="sxs-lookup"><span data-stu-id="5c3d3-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="5c3d3-149">示例</span><span class="sxs-lookup"><span data-stu-id="5c3d3-149">Example</span></span>

<span data-ttu-id="5c3d3-150">下面的示例显示了一个应用程序设置文件，该文件定义了两个应用程序范围设置和两个用户范围设置：</span><span class="sxs-lookup"><span data-stu-id="5c3d3-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5c3d3-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c3d3-151">See also</span></span>

- [<span data-ttu-id="5c3d3-152">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="5c3d3-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="5c3d3-153">应用程序设置体系结构</span><span class="sxs-lookup"><span data-stu-id="5c3d3-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
