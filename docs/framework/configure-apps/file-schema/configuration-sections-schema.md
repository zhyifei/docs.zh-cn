---
title: 配置节架构
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: c7559a95099608ea462c838591ddb43e18d8f80c
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301235"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="6a898-102">配置节架构</span><span class="sxs-lookup"><span data-stu-id="6a898-102">Configuration sections schema</span></span>

<span data-ttu-id="6a898-103">配置节架构包含配置文件中定义自定义设置的元素。</span><span class="sxs-lookup"><span data-stu-id="6a898-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="6a898-104">有关配置文件和架构的一般信息，请参阅[的.NET Framework 配置文件架构](~/docs/framework/configure-apps/file-schema/index.md)。</span><span class="sxs-lookup"><span data-stu-id="6a898-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](~/docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="6a898-105">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6a898-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6a898-106">[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6a898-106">[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="6a898-107">[ **\<clear>** ](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="6a898-107">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="6a898-108">[ **\<remove>** ](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="6a898-108">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="6a898-109">[ **\<section>** ](~/docs/framework/configure-apps/file-schema/section-element.md) </span><span class="sxs-lookup"><span data-stu-id="6a898-109">[**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) </span></span>  
[<span data-ttu-id="6a898-110"> *\*\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="6a898-110">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="6a898-111">描述</span><span class="sxs-lookup"><span data-stu-id="6a898-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6a898-112"> *\*\<clear>** for *\*\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="6a898-112">**\<clear>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="6a898-113">清除所有以前定义的节和节组。</span><span class="sxs-lookup"><span data-stu-id="6a898-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="6a898-114"> *\*\<clear>** </span><span class="sxs-lookup"><span data-stu-id="6a898-114">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="6a898-115">清除所有以前定义的节和节组。</span><span class="sxs-lookup"><span data-stu-id="6a898-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="6a898-116"> *\*\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="6a898-116">**\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="6a898-117">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="6a898-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="6a898-118"> *\*\<remove>** for *\*\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="6a898-118">**\<remove>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="6a898-119">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="6a898-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="6a898-120"> *\*\<section>** for *\*\<configSections>** and *\*\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="6a898-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="6a898-121">包含配置部分声明。</span><span class="sxs-lookup"><span data-stu-id="6a898-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="6a898-122"> *\*\<sectionGroup>** for *\*\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="6a898-122">**\<sectionGroup>** for **\<configSections>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="6a898-123">定义配置节的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6a898-123">Defines a namespace for configuration sections.</span></span> |
