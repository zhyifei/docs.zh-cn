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
ms.openlocfilehash: 120733873a7ea29303fe7f82c4c324d411532897
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921205"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="b3ddb-102">配置节架构</span><span class="sxs-lookup"><span data-stu-id="b3ddb-102">Configuration sections schema</span></span>

<span data-ttu-id="b3ddb-103">配置节架构包含用于在配置文件中定义自定义设置的元素。</span><span class="sxs-lookup"><span data-stu-id="b3ddb-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="b3ddb-104">有关配置文件和架构的一般信息, 请参阅[.NET Framework 的配置文件架构](index.md)。</span><span class="sxs-lookup"><span data-stu-id="b3ddb-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="b3ddb-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b3ddb-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="b3ddb-106">[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b3ddb-106">[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="b3ddb-107">[ **\<clear>** ](clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="b3ddb-107">[**\<clear>**](clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="b3ddb-108">[ **\<remove>** ](remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="b3ddb-108">[**\<remove>**](remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="b3ddb-109">[ **\<section>** ](section-element.md) </span><span class="sxs-lookup"><span data-stu-id="b3ddb-109">[**\<section>**](section-element.md) </span></span>  
[<span data-ttu-id="b3ddb-110"> **\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="b3ddb-110">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="b3ddb-111">描述</span><span class="sxs-lookup"><span data-stu-id="b3ddb-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b3ddb-112"> **\<clear>** for **\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="b3ddb-112">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="b3ddb-113">清除所有之前定义的部分和节组。</span><span class="sxs-lookup"><span data-stu-id="b3ddb-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="b3ddb-114"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="b3ddb-114">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="b3ddb-115">清除所有之前定义的部分和节组。</span><span class="sxs-lookup"><span data-stu-id="b3ddb-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="b3ddb-116"> **\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="b3ddb-116">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="b3ddb-117">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="b3ddb-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="b3ddb-118"> **\<remove>** for **\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="b3ddb-118">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="b3ddb-119">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="b3ddb-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="b3ddb-120">**configSections > \<** **和sectionGroup的节>\<>**  **\<** </span><span class="sxs-lookup"><span data-stu-id="b3ddb-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="b3ddb-121">包含配置节声明。</span><span class="sxs-lookup"><span data-stu-id="b3ddb-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="b3ddb-122"> **\<sectionGroup>** for **\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="b3ddb-122">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="b3ddb-123">定义配置节的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b3ddb-123">Defines a namespace for configuration sections.</span></span> |
