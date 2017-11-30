---
title: "&lt;部分&gt;元素"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8ed8b0211c8366d799fe158d91dcb42f92ad0cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="section-element"></a><span data-ttu-id="6c85d-102">\<部分 > 元素</span><span class="sxs-lookup"><span data-stu-id="6c85d-102">\<section> element</span></span>

<span data-ttu-id="6c85d-103">包含配置节声明。</span><span class="sxs-lookup"><span data-stu-id="6c85d-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="6c85d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6c85d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6c85d-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6c85d-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="6c85d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<部分 >**</span><span class="sxs-lookup"><span data-stu-id="6c85d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="6c85d-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6c85d-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6c85d-108">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6c85d-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="6c85d-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="6c85d-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="6c85d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<部分 >**</span><span class="sxs-lookup"><span data-stu-id="6c85d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6c85d-111">语法</span><span class="sxs-lookup"><span data-stu-id="6c85d-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="6c85d-112">必需的特性</span><span class="sxs-lookup"><span data-stu-id="6c85d-112">Required attributes</span></span>

|           | <span data-ttu-id="6c85d-113">描述</span><span class="sxs-lookup"><span data-stu-id="6c85d-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6c85d-114">**name**</span><span class="sxs-lookup"><span data-stu-id="6c85d-114">**name**</span></span>  | <span data-ttu-id="6c85d-115">指定的配置节的名称。</span><span class="sxs-lookup"><span data-stu-id="6c85d-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="6c85d-116">**type**</span><span class="sxs-lookup"><span data-stu-id="6c85d-116">**type**</span></span>  | <span data-ttu-id="6c85d-117">指定从配置文件中读取节的配置节处理程序类的名称。</span><span class="sxs-lookup"><span data-stu-id="6c85d-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="6c85d-118">类型值具有语法"fully-qualified-section-handler-class-name，简单程序集名称"。</span><span class="sxs-lookup"><span data-stu-id="6c85d-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="6c85d-119">简单程序集名称是根文件名无*.dll*文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="6c85d-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="6c85d-120">可选特性</span><span class="sxs-lookup"><span data-stu-id="6c85d-120">Optional attributes</span></span>

<span data-ttu-id="6c85d-121">以下属性是仅适用于 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6c85d-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="6c85d-122">配置系统会忽略这些属性对于其他应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="6c85d-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="6c85d-123">描述</span><span class="sxs-lookup"><span data-stu-id="6c85d-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="6c85d-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="6c85d-124">**allowDefinition**</span></span> | <span data-ttu-id="6c85d-125">指定可以在使用的节的配置文件。</span><span class="sxs-lookup"><span data-stu-id="6c85d-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="6c85d-126">使用下列值之一：</span><span class="sxs-lookup"><span data-stu-id="6c85d-126">Use one of the following values:</span></span><br><br><span data-ttu-id="6c85d-127">**无处不在**</span><span class="sxs-lookup"><span data-stu-id="6c85d-127">**Everywhere**</span></span><br><span data-ttu-id="6c85d-128">允许在任何配置文件中使用该节。</span><span class="sxs-lookup"><span data-stu-id="6c85d-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="6c85d-129">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="6c85d-129">This is the default.</span></span><br><span data-ttu-id="6c85d-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="6c85d-130">**MachineOnly**</span></span><br><span data-ttu-id="6c85d-131">允许仅在计算机配置文件中使用该节 (*Machine.config*)。</span><span class="sxs-lookup"><span data-stu-id="6c85d-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="6c85d-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="6c85d-132">**MachineToApplication**</span></span><br><span data-ttu-id="6c85d-133">允许要在计算机配置文件或应用程序配置文件中使用的部分。</span><span class="sxs-lookup"><span data-stu-id="6c85d-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="6c85d-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="6c85d-134">**allowLocation**</span></span>   | <span data-ttu-id="6c85d-135">确定是否可以在使用的部分**\<位置 >**元素。</span><span class="sxs-lookup"><span data-stu-id="6c85d-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="6c85d-136">使用下列值之一：</span><span class="sxs-lookup"><span data-stu-id="6c85d-136">Use one of the following values:</span></span><br><br><span data-ttu-id="6c85d-137">**true**</span><span class="sxs-lookup"><span data-stu-id="6c85d-137">**true**</span></span><br><span data-ttu-id="6c85d-138">允许要在中使用该节**\<位置 >**元素。</span><span class="sxs-lookup"><span data-stu-id="6c85d-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="6c85d-139">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="6c85d-139">This is the default.</span></span><br><span data-ttu-id="6c85d-140">**false**</span><span class="sxs-lookup"><span data-stu-id="6c85d-140">**false**</span></span><br><span data-ttu-id="6c85d-141">不允许在中使用的部分**\<位置 >**元素。</span><span class="sxs-lookup"><span data-stu-id="6c85d-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="6c85d-142">父元素</span><span class="sxs-lookup"><span data-stu-id="6c85d-142">Parent elements</span></span>

|     | <span data-ttu-id="6c85d-143">描述</span><span class="sxs-lookup"><span data-stu-id="6c85d-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6c85d-144">**\<configSections >**元素</span><span class="sxs-lookup"><span data-stu-id="6c85d-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="6c85d-145">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="6c85d-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="6c85d-146">**\<sectionGroup >**元素</span><span class="sxs-lookup"><span data-stu-id="6c85d-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="6c85d-147">定义配置节的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6c85d-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="6c85d-148">A **\<部分 >**元素是其中任何一个子元素 **\<configSections >**或 **\<sectionGroup >**但不是两者。</span><span class="sxs-lookup"><span data-stu-id="6c85d-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="6c85d-149">子元素</span><span class="sxs-lookup"><span data-stu-id="6c85d-149">Child elements</span></span>

<span data-ttu-id="6c85d-150">无</span><span class="sxs-lookup"><span data-stu-id="6c85d-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="6c85d-151">备注</span><span class="sxs-lookup"><span data-stu-id="6c85d-151">Remarks</span></span>

<span data-ttu-id="6c85d-152">实质上声明配置节定义配置文件的新元素。</span><span class="sxs-lookup"><span data-stu-id="6c85d-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="6c85d-153">新元素包含一个配置节处理程序的设置 (即，一个类以实现<xref:System.Configuration.IConfigurationSectionHandler>接口) 读取。</span><span class="sxs-lookup"><span data-stu-id="6c85d-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="6c85d-154">属性和你定义的节的子元素取决于你使用读取你的设置节处理程序。</span><span class="sxs-lookup"><span data-stu-id="6c85d-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="6c85d-155">声明中的配置节处理程序*Machine.config*文件，您可以在该计算机上任何应用程序配置文件中使用的配置部分除非**allowDefinition**属性指定，否则。</span><span class="sxs-lookup"><span data-stu-id="6c85d-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="6c85d-156">示例</span><span class="sxs-lookup"><span data-stu-id="6c85d-156">Example</span></span>

<span data-ttu-id="6c85d-157">下面的示例演示如何定义一个配置节和定义该部分的设置：</span><span class="sxs-lookup"><span data-stu-id="6c85d-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="6c85d-158">配置文件</span><span class="sxs-lookup"><span data-stu-id="6c85d-158">Configuration file</span></span>

<span data-ttu-id="6c85d-159">此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="6c85d-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c85d-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c85d-160">See also</span></span>

[<span data-ttu-id="6c85d-161">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="6c85d-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
