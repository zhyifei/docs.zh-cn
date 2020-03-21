---
title: 配置部分架构
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
ms.openlocfilehash: 28f936e6fd7c9e7f6f895396df8e8b8d36ab9139
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155318"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="5d2a3-102">配置部分架构</span><span class="sxs-lookup"><span data-stu-id="5d2a3-102">Configuration sections schema</span></span>

<span data-ttu-id="5d2a3-103">配置部分架构包含在配置文件中定义自定义设置的元素。</span><span class="sxs-lookup"><span data-stu-id="5d2a3-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="5d2a3-104">有关配置文件和架构的一般信息，请参阅[.NET 框架的配置文件架构](index.md)。</span><span class="sxs-lookup"><span data-stu-id="5d2a3-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="5d2a3-105">[**\<配置>**](configuration-element.md)

[**配置\<>**](configsections-element-for-configuration.md)

[**清除>\<删除**](remove-element-for-configsections.md)[**>\<节**](section-element.md)>
[**部分\<组>**](sectiongroup-element-for-configsections.md) [\*\* \< \*\*](clear-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="5d2a3-105">[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<clear>**](clear-element-for-configsections.md)
[**\<remove>**](remove-element-for-configsections.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>

|     | <span data-ttu-id="5d2a3-106">说明</span><span class="sxs-lookup"><span data-stu-id="5d2a3-106">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5d2a3-107">用于配置>的透明>\*\* \<\*\* \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="5d2a3-107">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="5d2a3-108">清除以前定义的所有节和节组。</span><span class="sxs-lookup"><span data-stu-id="5d2a3-108">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="5d2a3-109">**\<明确>**</span><span class="sxs-lookup"><span data-stu-id="5d2a3-109">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="5d2a3-110">清除以前定义的所有节和节组。</span><span class="sxs-lookup"><span data-stu-id="5d2a3-110">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="5d2a3-111">**\<配置部分>**</span><span class="sxs-lookup"><span data-stu-id="5d2a3-111">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="5d2a3-112">包含配置部分和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="5d2a3-112">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="5d2a3-113">**\<删除\*\*\*\*配置\<>>**</span><span class="sxs-lookup"><span data-stu-id="5d2a3-113">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="5d2a3-114">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="5d2a3-114">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="5d2a3-115">>**和\<部分组**>**\<的配置部分**>\*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="5d2a3-115">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="5d2a3-116">包含配置部分声明。</span><span class="sxs-lookup"><span data-stu-id="5d2a3-116">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="5d2a3-117">部分组>，用于**\<\*\*\*\*\<配置>**</span><span class="sxs-lookup"><span data-stu-id="5d2a3-117">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="5d2a3-118">为配置部分定义命名空间。</span><span class="sxs-lookup"><span data-stu-id="5d2a3-118">Defines a namespace for configuration sections.</span></span> |
