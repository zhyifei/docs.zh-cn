---
title: 应用程序设置特性
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
ms.openlocfilehash: d52549546bc838d8d38da33b9bb9931488795064
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="application-settings-attributes"></a>应用程序设置特性
应用程序设置体系结构提供了许多特性，它们可以应用于应用程序设置包装类或其各个属性。 这些属性是在运行时通过检查应用程序设置基础结构通常专门设置提供程序，以便定制的自定义包装规定的需求的功能。  
  
 下表列出可以应用于应用程序设置包装类和 / 或此类的个别属性的属性。 根据定义，仅单个作用域属性-**UserScopedSettingAttribute**或**ApplicationScopedSettingAttribute**-必须将应用到每个设置属性。  
  
> [!NOTE]
>  自定义设置提供程序，派生自<xref:System.Configuration.SettingsProvider>类中，只需识别的以下三个特性： **ApplicationScopedSettingAttribute**， **UserScopedSettingAttribute**，和**DefaultSettingValueAttribute**。  
  
|特性|目标|描述|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|消息和传送|指定要用于持久性设置提供程序的短名称。<br /><br /> 如果未提供此属性，默认的提供程序， <xref:System.Configuration.LocalFileSettingsProvider>，假定。|  
|<xref:System.Configuration.UserScopedSettingAttribute>|消息和传送|作为用户范围的应用程序设置中定义的属性。|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|消息和传送|为应用程序范围的应用程序设置中定义的属性。|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|属性|指定可以反序列化提供程序为此属性的硬编码的默认值的字符串。<br /><br /> <xref:System.Configuration.LocalFileSettingsProvider>不需要此属性，并将重写任何值，提供此属性如果没有已保留某个值。|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|属性|提供一个单独的设置，主要由运行时和设计时工具使用描述性的测试。|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|类|提供设置组的显式名称。 如果没有此特性，<xref:System.Configuration.ApplicationSettingsBase>使用包装类名称。|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|类|提供设置组中，主要由运行时和设计时工具使用描述性的测试。|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|消息和传送|指定应将提供给设置组或属性的零个或多个可管理性服务。 可用的服务由描述<xref:System.Configuration.SettingsManageability>枚举。|  
|<xref:System.Configuration.SpecialSettingAttribute>|属性|指示设置属于一个特殊的预定义的类别，如连接字符串，建议通过设置提供程序的特殊处理。 此属性的预定义的类别定义的<xref:System.Configuration.SpecialSetting>枚举。|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|消息和传送|指定的设置组或属性的首选序列化机制。 通过定义可序列化机制<xref:System.Configuration.SettingsSerializeAs>枚举。|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|属性|指定设置提供程序，应禁用所有应用程序升级功能标记的属性。|  
  
 *类*指示该属性，可以应用到应用程序设置包装类。 *属性*指示该属性可以是应用到仅设置属性。 *同时*指示该属性可以应用到任何一级。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 [应用程序设置体系结构](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [如何：创建应用程序设置](http://msdn.microsoft.com/library/53b3af80-1c02-4e35-99c6-787663148945)
