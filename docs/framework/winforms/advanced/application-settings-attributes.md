---
title: "应用程序设置特性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], attributes
- attributes [Windows Forms], application settings
- wrapper classes [Windows Forms], application settings
ms.assetid: 53caa66c-a9fb-43a5-953c-ad092590098d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2ed0a0393f505d0126508e574b1cd9abe138866
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="application-settings-attributes"></a><span data-ttu-id="af60f-102">应用程序设置特性</span><span class="sxs-lookup"><span data-stu-id="af60f-102">Application Settings Attributes</span></span>
<span data-ttu-id="af60f-103">应用程序设置体系结构提供了许多特性，它们可以应用于应用程序设置包装类或其各个属性。</span><span class="sxs-lookup"><span data-stu-id="af60f-103">The Application Settings architecture provides many attributes that can be applied either to the applications settings wrapper class or its individual properties.</span></span> <span data-ttu-id="af60f-104">这些属性是在运行时通过检查应用程序设置基础结构通常专门设置提供程序，以便定制的自定义包装规定的需求的功能。</span><span class="sxs-lookup"><span data-stu-id="af60f-104">These attributes are examined at run time by the application settings infrastructure, often specifically the settings provider, in order to tailor its functioning to the stated needs of the custom wrapper.</span></span>  
  
 <span data-ttu-id="af60f-105">下表列出可以应用于应用程序设置包装类和 / 或此类的个别属性的属性。</span><span class="sxs-lookup"><span data-stu-id="af60f-105">The following table lists the attributes that can be applied to the application settings wrapper class, this class's individual properties, or both.</span></span> <span data-ttu-id="af60f-106">根据定义，仅单个作用域属性-**UserScopedSettingAttribute**或**ApplicationScopedSettingAttribute**-必须将应用到每个设置属性。</span><span class="sxs-lookup"><span data-stu-id="af60f-106">By definition, only a single scope attribute—**UserScopedSettingAttribute** or **ApplicationScopedSettingAttribute**—must be applied to each and every settings property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af60f-107">自定义设置提供程序，派生自<xref:System.Configuration.SettingsProvider>类中，只需识别的以下三个特性： **ApplicationScopedSettingAttribute**， **UserScopedSettingAttribute**，和**DefaultSettingValueAttribute**。</span><span class="sxs-lookup"><span data-stu-id="af60f-107">A custom settings provider, derived from the <xref:System.Configuration.SettingsProvider> class, is only required to recognize the following three attributes: **ApplicationScopedSettingAttribute**, **UserScopedSettingAttribute**, and **DefaultSettingValueAttribute**.</span></span>  
  
|<span data-ttu-id="af60f-108">特性</span><span class="sxs-lookup"><span data-stu-id="af60f-108">Attribute</span></span>|<span data-ttu-id="af60f-109">目标</span><span class="sxs-lookup"><span data-stu-id="af60f-109">Target</span></span>|<span data-ttu-id="af60f-110">描述</span><span class="sxs-lookup"><span data-stu-id="af60f-110">Description</span></span>|  
|---------------|------------|-----------------|  
|<xref:System.Configuration.SettingsProviderAttribute>|<span data-ttu-id="af60f-111">消息和传送</span><span class="sxs-lookup"><span data-stu-id="af60f-111">Both</span></span>|<span data-ttu-id="af60f-112">指定要用于持久性设置提供程序的短名称。</span><span class="sxs-lookup"><span data-stu-id="af60f-112">Specifies the short name of the settings provider to use for persistence.</span></span><br /><br /> <span data-ttu-id="af60f-113">如果未提供此属性，默认的提供程序， <xref:System.Configuration.LocalFileSettingsProvider>，假定。</span><span class="sxs-lookup"><span data-stu-id="af60f-113">If this attribute is not supplied, the default provider, <xref:System.Configuration.LocalFileSettingsProvider>, is assumed.</span></span>|  
|<xref:System.Configuration.UserScopedSettingAttribute>|<span data-ttu-id="af60f-114">消息和传送</span><span class="sxs-lookup"><span data-stu-id="af60f-114">Both</span></span>|<span data-ttu-id="af60f-115">作为用户范围的应用程序设置中定义的属性。</span><span class="sxs-lookup"><span data-stu-id="af60f-115">Defines a property as a user-scoped application setting.</span></span>|  
|<xref:System.Configuration.ApplicationScopedSettingAttribute>|<span data-ttu-id="af60f-116">消息和传送</span><span class="sxs-lookup"><span data-stu-id="af60f-116">Both</span></span>|<span data-ttu-id="af60f-117">为应用程序范围的应用程序设置中定义的属性。</span><span class="sxs-lookup"><span data-stu-id="af60f-117">Defines a property as an application-scoped application setting.</span></span>|  
|<xref:System.Configuration.DefaultSettingValueAttribute>|<span data-ttu-id="af60f-118">属性</span><span class="sxs-lookup"><span data-stu-id="af60f-118">Property</span></span>|<span data-ttu-id="af60f-119">指定可以反序列化提供程序为此属性的硬编码的默认值的字符串。</span><span class="sxs-lookup"><span data-stu-id="af60f-119">Specifies a string that can be deserialized by the provider into the hard-coded default value for this property.</span></span><br /><br /> <span data-ttu-id="af60f-120"><xref:System.Configuration.LocalFileSettingsProvider>不需要此属性，并将重写任何值，提供此属性如果没有已保留某个值。</span><span class="sxs-lookup"><span data-stu-id="af60f-120">The <xref:System.Configuration.LocalFileSettingsProvider> does not require this attribute, and will override any value provided by this attribute if there is a value already persisted.</span></span>|  
|<xref:System.Configuration.SettingsDescriptionAttribute>|<span data-ttu-id="af60f-121">属性</span><span class="sxs-lookup"><span data-stu-id="af60f-121">Property</span></span>|<span data-ttu-id="af60f-122">提供一个单独的设置，主要由运行时和设计时工具使用描述性的测试。</span><span class="sxs-lookup"><span data-stu-id="af60f-122">Provides the descriptive test for an individual setting, used primarily by run-time and design-time tools.</span></span>|  
|<xref:System.Configuration.SettingsGroupNameAttribute>|<span data-ttu-id="af60f-123">类</span><span class="sxs-lookup"><span data-stu-id="af60f-123">Class</span></span>|<span data-ttu-id="af60f-124">提供设置组的显式名称。</span><span class="sxs-lookup"><span data-stu-id="af60f-124">Provides an explicit name for a settings group.</span></span> <span data-ttu-id="af60f-125">如果没有此特性，<xref:System.Configuration.ApplicationSettingsBase>使用包装类名称。</span><span class="sxs-lookup"><span data-stu-id="af60f-125">If this attribute is missing, <xref:System.Configuration.ApplicationSettingsBase> uses the wrapper class name.</span></span>|  
|<xref:System.Configuration.SettingsGroupDescriptionAttribute>|<span data-ttu-id="af60f-126">类</span><span class="sxs-lookup"><span data-stu-id="af60f-126">Class</span></span>|<span data-ttu-id="af60f-127">提供设置组中，主要由运行时和设计时工具使用描述性的测试。</span><span class="sxs-lookup"><span data-stu-id="af60f-127">Provides the descriptive test for a settings group, used primarily by run-time and design-time tools.</span></span>|  
|<xref:System.Configuration.SettingsManageabilityAttribute>|<span data-ttu-id="af60f-128">消息和传送</span><span class="sxs-lookup"><span data-stu-id="af60f-128">Both</span></span>|<span data-ttu-id="af60f-129">指定应将提供给设置组或属性的零个或多个可管理性服务。</span><span class="sxs-lookup"><span data-stu-id="af60f-129">Specifies zero or more manageability services that should be provided to the settings group or property.</span></span> <span data-ttu-id="af60f-130">可用的服务由描述<xref:System.Configuration.SettingsManageability>枚举。</span><span class="sxs-lookup"><span data-stu-id="af60f-130">The available services are described by the <xref:System.Configuration.SettingsManageability> enumeration.</span></span>|  
|<xref:System.Configuration.SpecialSettingAttribute>|<span data-ttu-id="af60f-131">属性</span><span class="sxs-lookup"><span data-stu-id="af60f-131">Property</span></span>|<span data-ttu-id="af60f-132">指示设置属于一个特殊的预定义的类别，如连接字符串，建议通过设置提供程序的特殊处理。</span><span class="sxs-lookup"><span data-stu-id="af60f-132">Indicates that a setting belongs to a special, predefined category, such as a connection string, that suggests special processing by the settings provider.</span></span> <span data-ttu-id="af60f-133">此属性的预定义的类别定义的<xref:System.Configuration.SpecialSetting>枚举。</span><span class="sxs-lookup"><span data-stu-id="af60f-133">The predefined categories for this attribute are defined by the <xref:System.Configuration.SpecialSetting> enumeration.</span></span>|  
|<xref:System.Configuration.SettingsSerializeAsAttribute>|<span data-ttu-id="af60f-134">消息和传送</span><span class="sxs-lookup"><span data-stu-id="af60f-134">Both</span></span>|<span data-ttu-id="af60f-135">指定的设置组或属性的首选序列化机制。</span><span class="sxs-lookup"><span data-stu-id="af60f-135">Specifies a preferred serialization mechanism for a settings group or property.</span></span> <span data-ttu-id="af60f-136">通过定义可序列化机制<xref:System.Configuration.SettingsSerializeAs>枚举。</span><span class="sxs-lookup"><span data-stu-id="af60f-136">The available serialization mechanisms are defined by the <xref:System.Configuration.SettingsSerializeAs> enumeration.</span></span>|  
|<xref:System.Configuration.NoSettingsVersionUpgradeAttribute>|<span data-ttu-id="af60f-137">属性</span><span class="sxs-lookup"><span data-stu-id="af60f-137">Property</span></span>|<span data-ttu-id="af60f-138">指定设置提供程序，应禁用所有应用程序升级功能标记的属性。</span><span class="sxs-lookup"><span data-stu-id="af60f-138">Specifies that a settings provider should disable all application upgrade functionality for the marked property.</span></span>|  
  
 <span data-ttu-id="af60f-139">*类*指示该属性，可以应用到应用程序设置包装类。</span><span class="sxs-lookup"><span data-stu-id="af60f-139">*Class* indicates that the attribute can be applied only to an application settings wrapper class.</span></span> <span data-ttu-id="af60f-140">*属性*指示该属性可以是应用到仅设置属性。</span><span class="sxs-lookup"><span data-stu-id="af60f-140">*Property* indicates that the attribute can be applied only settings properties.</span></span> <span data-ttu-id="af60f-141">*同时*指示该属性可以应用到任何一级。</span><span class="sxs-lookup"><span data-stu-id="af60f-141">*Both* indicates that the attribute can be applied at either level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af60f-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="af60f-142">See Also</span></span>  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.SettingsProvider>  
 [<span data-ttu-id="af60f-143">应用程序设置体系结构</span><span class="sxs-lookup"><span data-stu-id="af60f-143">Application Settings Architecture</span></span>](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)  
 [<span data-ttu-id="af60f-144">如何：创建应用程序设置</span><span class="sxs-lookup"><span data-stu-id="af60f-144">How to: Create Application Settings</span></span>](http://msdn.microsoft.com/library/53b3af80-1c02-4e35-99c6-787663148945)
