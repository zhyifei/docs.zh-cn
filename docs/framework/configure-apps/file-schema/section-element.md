---
title: <section> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 94f7709f4bd273515d9fcdd727354ec579c46207
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927232"
---
# <a name="section-element"></a><span data-ttu-id="c6cae-102">\<节 > 元素</span><span class="sxs-lookup"><span data-stu-id="c6cae-102">\<section> element</span></span>

<span data-ttu-id="c6cae-103">包含配置节声明。</span><span class="sxs-lookup"><span data-stu-id="c6cae-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="c6cae-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="c6cae-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="c6cae-105">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="c6cae-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="c6cae-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<section>**</span><span class="sxs-lookup"><span data-stu-id="c6cae-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="c6cae-107">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="c6cae-107">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="c6cae-108">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="c6cae-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="c6cae-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup>** ](sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="c6cae-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="c6cae-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<section>**</span><span class="sxs-lookup"><span data-stu-id="c6cae-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c6cae-111">语法</span><span class="sxs-lookup"><span data-stu-id="c6cae-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="c6cae-112">必需的特性</span><span class="sxs-lookup"><span data-stu-id="c6cae-112">Required attributes</span></span>

|           | <span data-ttu-id="c6cae-113">描述</span><span class="sxs-lookup"><span data-stu-id="c6cae-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="c6cae-114">**名称**</span><span class="sxs-lookup"><span data-stu-id="c6cae-114">**name**</span></span>  | <span data-ttu-id="c6cae-115">指定配置节的名称。</span><span class="sxs-lookup"><span data-stu-id="c6cae-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="c6cae-116">**type**</span><span class="sxs-lookup"><span data-stu-id="c6cae-116">**type**</span></span>  | <span data-ttu-id="c6cae-117">指定从配置文件读取节的配置节处理程序类的名称。</span><span class="sxs-lookup"><span data-stu-id="c6cae-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="c6cae-118">类型值具有语法 "完全限定的节-名称、简单程序集名称"。</span><span class="sxs-lookup"><span data-stu-id="c6cae-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="c6cae-119">简单程序集名称是没有 *.dll*文件扩展名的根文件名。</span><span class="sxs-lookup"><span data-stu-id="c6cae-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="c6cae-120">可选属性</span><span class="sxs-lookup"><span data-stu-id="c6cae-120">Optional attributes</span></span>

<span data-ttu-id="c6cae-121">以下属性仅适用于 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6cae-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="c6cae-122">对于其他应用程序类型, 配置系统将忽略这些属性。</span><span class="sxs-lookup"><span data-stu-id="c6cae-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="c6cae-123">描述</span><span class="sxs-lookup"><span data-stu-id="c6cae-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="c6cae-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="c6cae-124">**allowDefinition**</span></span> | <span data-ttu-id="c6cae-125">指定可在其中使用节的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c6cae-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="c6cae-126">使用下列值之一：</span><span class="sxs-lookup"><span data-stu-id="c6cae-126">Use one of the following values:</span></span><br><br><span data-ttu-id="c6cae-127">**Everywhere**</span><span class="sxs-lookup"><span data-stu-id="c6cae-127">**Everywhere**</span></span><br><span data-ttu-id="c6cae-128">允许在任何配置文件中使用节。</span><span class="sxs-lookup"><span data-stu-id="c6cae-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="c6cae-129">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c6cae-129">This is the default.</span></span><br><span data-ttu-id="c6cae-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="c6cae-130">**MachineOnly**</span></span><br><span data-ttu-id="c6cae-131">允许部分仅在计算机配置文件 (*machine.config*) 中使用。</span><span class="sxs-lookup"><span data-stu-id="c6cae-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="c6cae-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="c6cae-132">**MachineToApplication**</span></span><br><span data-ttu-id="c6cae-133">允许在计算机配置文件或应用程序配置文件中使用部分。</span><span class="sxs-lookup"><span data-stu-id="c6cae-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="c6cae-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="c6cae-134">**allowLocation**</span></span>   | <span data-ttu-id="c6cae-135">确定是否可以在 **\<位置 >** 元素内使用部分。</span><span class="sxs-lookup"><span data-stu-id="c6cae-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="c6cae-136">使用下列值之一：</span><span class="sxs-lookup"><span data-stu-id="c6cae-136">Use one of the following values:</span></span><br><br><span data-ttu-id="c6cae-137">**true**</span><span class="sxs-lookup"><span data-stu-id="c6cae-137">**true**</span></span><br><span data-ttu-id="c6cae-138">允许在 **\<位置 >** 元素中使用部分。</span><span class="sxs-lookup"><span data-stu-id="c6cae-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="c6cae-139">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c6cae-139">This is the default.</span></span><br><span data-ttu-id="c6cae-140">**false**</span><span class="sxs-lookup"><span data-stu-id="c6cae-140">**false**</span></span><br><span data-ttu-id="c6cae-141">不允许在 **\<位置 >** 元素中使用节。</span><span class="sxs-lookup"><span data-stu-id="c6cae-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="c6cae-142">父元素</span><span class="sxs-lookup"><span data-stu-id="c6cae-142">Parent elements</span></span>

|     | <span data-ttu-id="c6cae-143">描述</span><span class="sxs-lookup"><span data-stu-id="c6cae-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c6cae-144"> **configSections>\<** 元素</span><span class="sxs-lookup"><span data-stu-id="c6cae-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="c6cae-145">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="c6cae-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="c6cae-146"> **sectionGroup>\<** 元素</span><span class="sxs-lookup"><span data-stu-id="c6cae-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="c6cae-147">定义配置节的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c6cae-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="c6cae-148">节 > 元素是 **\<configSections >** 或 **\<sectionGroup >** 的子元素, 但不能同时为两者。  **\<**</span><span class="sxs-lookup"><span data-stu-id="c6cae-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="c6cae-149">子元素</span><span class="sxs-lookup"><span data-stu-id="c6cae-149">Child elements</span></span>

<span data-ttu-id="c6cae-150">无</span><span class="sxs-lookup"><span data-stu-id="c6cae-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="c6cae-151">备注</span><span class="sxs-lookup"><span data-stu-id="c6cae-151">Remarks</span></span>

<span data-ttu-id="c6cae-152">声明配置节本质上定义了配置文件的新元素。</span><span class="sxs-lookup"><span data-stu-id="c6cae-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="c6cae-153">新元素包含配置节处理程序 (即实现<xref:System.Configuration.IConfigurationSectionHandler>接口的类) 的设置。</span><span class="sxs-lookup"><span data-stu-id="c6cae-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="c6cae-154">你定义的节的特性和子元素取决于用于读取设置的部分处理程序。</span><span class="sxs-lookup"><span data-stu-id="c6cae-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="c6cae-155">通过在*machine.config*文件中声明配置节处理程序, 你可以使用该计算机上任何应用程序配置文件中的配置节, 除非**allowDefinition**属性指定了其他内容。</span><span class="sxs-lookup"><span data-stu-id="c6cae-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="c6cae-156">示例</span><span class="sxs-lookup"><span data-stu-id="c6cae-156">Example</span></span>

<span data-ttu-id="c6cae-157">下面的示例演示如何定义配置节并定义该部分的设置:</span><span class="sxs-lookup"><span data-stu-id="c6cae-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="c6cae-158">配置文件</span><span class="sxs-lookup"><span data-stu-id="c6cae-158">Configuration file</span></span>

<span data-ttu-id="c6cae-159">此元素可用于应用程序配置文件、计算机配置文件 (*machine.config*) 和不在应用程序目录级别的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="c6cae-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6cae-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6cae-160">See also</span></span>

- [<span data-ttu-id="c6cae-161">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="c6cae-161">Configuration file schema for the .NET Framework</span></span>](index.md)
