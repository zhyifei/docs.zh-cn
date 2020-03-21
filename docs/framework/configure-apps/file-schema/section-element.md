---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153720"
---
# <a name="section-element"></a><span data-ttu-id="0b246-102">\<节>元素</span><span class="sxs-lookup"><span data-stu-id="0b246-102">\<section> element</span></span>

<span data-ttu-id="0b246-103">包含配置部分声明。</span><span class="sxs-lookup"><span data-stu-id="0b246-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="0b246-104">[**\<配置>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b246-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="0b246-105">&nbsp;&nbsp;[**\<配置部分>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="0b246-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="0b246-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<第>节**</span><span class="sxs-lookup"><span data-stu-id="0b246-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="0b246-107">[**\<配置>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b246-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="0b246-108">&nbsp;&nbsp;[**\<配置部分>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="0b246-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="0b246-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<部分组>**](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="0b246-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="0b246-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<第>节**</span><span class="sxs-lookup"><span data-stu-id="0b246-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0b246-111">语法</span><span class="sxs-lookup"><span data-stu-id="0b246-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="0b246-112">必需属性</span><span class="sxs-lookup"><span data-stu-id="0b246-112">Required attributes</span></span>

|           | <span data-ttu-id="0b246-113">说明</span><span class="sxs-lookup"><span data-stu-id="0b246-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="0b246-114">**name**</span><span class="sxs-lookup"><span data-stu-id="0b246-114">**name**</span></span>  | <span data-ttu-id="0b246-115">指定配置部分的名称。</span><span class="sxs-lookup"><span data-stu-id="0b246-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="0b246-116">**type**</span><span class="sxs-lookup"><span data-stu-id="0b246-116">**type**</span></span>  | <span data-ttu-id="0b246-117">指定从配置文件读取节的配置节处理程序类的名称。</span><span class="sxs-lookup"><span data-stu-id="0b246-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="0b246-118">类型值具有语法"完全限定的截面处理程序-类名称，简单程序集名称"。</span><span class="sxs-lookup"><span data-stu-id="0b246-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="0b246-119">简单的程序集名称是没有 *.dll*文件扩展名的根文件名。</span><span class="sxs-lookup"><span data-stu-id="0b246-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="0b246-120">可选属性</span><span class="sxs-lookup"><span data-stu-id="0b246-120">Optional attributes</span></span>

<span data-ttu-id="0b246-121">以下属性仅适用于ASP.NET应用程序。</span><span class="sxs-lookup"><span data-stu-id="0b246-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="0b246-122">配置系统忽略这些属性的其他应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="0b246-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="0b246-123">说明</span><span class="sxs-lookup"><span data-stu-id="0b246-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="0b246-124">**允许定义**</span><span class="sxs-lookup"><span data-stu-id="0b246-124">**allowDefinition**</span></span> | <span data-ttu-id="0b246-125">指定该节可以使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="0b246-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="0b246-126">使用以下值之一：</span><span class="sxs-lookup"><span data-stu-id="0b246-126">Use one of the following values:</span></span><br><br><span data-ttu-id="0b246-127">**无处不在**</span><span class="sxs-lookup"><span data-stu-id="0b246-127">**Everywhere**</span></span><br><span data-ttu-id="0b246-128">允许在任何配置文件中使用该节。</span><span class="sxs-lookup"><span data-stu-id="0b246-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="0b246-129">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="0b246-129">This is the default.</span></span><br><span data-ttu-id="0b246-130">**仅限机器**</span><span class="sxs-lookup"><span data-stu-id="0b246-130">**MachineOnly**</span></span><br><span data-ttu-id="0b246-131">允许仅在机器配置文件 （*机器.config）* 中使用该部分。</span><span class="sxs-lookup"><span data-stu-id="0b246-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="0b246-132">**机器应用**</span><span class="sxs-lookup"><span data-stu-id="0b246-132">**MachineToApplication**</span></span><br><span data-ttu-id="0b246-133">允许在计算机配置文件或应用程序配置文件中使用节。</span><span class="sxs-lookup"><span data-stu-id="0b246-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="0b246-134">**允许定位**</span><span class="sxs-lookup"><span data-stu-id="0b246-134">**allowLocation**</span></span>   | <span data-ttu-id="0b246-135">确定是否可以在**\<位置>** 元素中使用节。</span><span class="sxs-lookup"><span data-stu-id="0b246-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="0b246-136">使用以下值之一：</span><span class="sxs-lookup"><span data-stu-id="0b246-136">Use one of the following values:</span></span><br><br><span data-ttu-id="0b246-137">**true**</span><span class="sxs-lookup"><span data-stu-id="0b246-137">**true**</span></span><br><span data-ttu-id="0b246-138">允许在**\<位置>** 元素中使用节。</span><span class="sxs-lookup"><span data-stu-id="0b246-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="0b246-139">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="0b246-139">This is the default.</span></span><br><span data-ttu-id="0b246-140">**false**</span><span class="sxs-lookup"><span data-stu-id="0b246-140">**false**</span></span><br><span data-ttu-id="0b246-141">不允许在**\<位置>** 元素中使用节。</span><span class="sxs-lookup"><span data-stu-id="0b246-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="0b246-142">父元素</span><span class="sxs-lookup"><span data-stu-id="0b246-142">Parent elements</span></span>

|     | <span data-ttu-id="0b246-143">说明</span><span class="sxs-lookup"><span data-stu-id="0b246-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0b246-144">**\<配置部分>** 元素</span><span class="sxs-lookup"><span data-stu-id="0b246-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="0b246-145">包含配置部分和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="0b246-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="0b246-146">第>节组**\<** 元素</span><span class="sxs-lookup"><span data-stu-id="0b246-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="0b246-147">为配置部分定义命名空间。</span><span class="sxs-lookup"><span data-stu-id="0b246-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="0b246-148">\*\* \<>元素的节**是**\<配置">"\*\* 或**\<"组组">** 的子元素，但不能同时提供两者。</span><span class="sxs-lookup"><span data-stu-id="0b246-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="0b246-149">子元素</span><span class="sxs-lookup"><span data-stu-id="0b246-149">Child elements</span></span>

<span data-ttu-id="0b246-150">无</span><span class="sxs-lookup"><span data-stu-id="0b246-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="0b246-151">备注</span><span class="sxs-lookup"><span data-stu-id="0b246-151">Remarks</span></span>

<span data-ttu-id="0b246-152">声明配置部分实质上定义配置文件的新元素。</span><span class="sxs-lookup"><span data-stu-id="0b246-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="0b246-153">新元素包含配置节处理程序（即实现接口的类）读取的<xref:System.Configuration.IConfigurationSectionHandler>设置。</span><span class="sxs-lookup"><span data-stu-id="0b246-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="0b246-154">定义的节的属性和子元素取决于用于读取设置的节处理程序。</span><span class="sxs-lookup"><span data-stu-id="0b246-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="0b246-155">在*Machine.config 文件中*声明配置部分处理程序使您能够在该计算机上的任何应用程序配置文件中使用配置节，除非**allowDefinition**属性另有指定。</span><span class="sxs-lookup"><span data-stu-id="0b246-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="0b246-156">示例</span><span class="sxs-lookup"><span data-stu-id="0b246-156">Example</span></span>

<span data-ttu-id="0b246-157">下面的示例演示如何定义配置部分并定义该部分的设置：</span><span class="sxs-lookup"><span data-stu-id="0b246-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="0b246-158">配置文件</span><span class="sxs-lookup"><span data-stu-id="0b246-158">Configuration file</span></span>

<span data-ttu-id="0b246-159">此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。</span><span class="sxs-lookup"><span data-stu-id="0b246-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b246-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b246-160">See also</span></span>

- [<span data-ttu-id="0b246-161">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="0b246-161">Configuration file schema for the .NET Framework</span></span>](index.md)
