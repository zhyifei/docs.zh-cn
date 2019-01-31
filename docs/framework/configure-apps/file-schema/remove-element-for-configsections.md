---
title: <remove> 的 <configSections> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 9ceffd3194c7df41f12ac6cd6b589602965b4920
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279092"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="2f058-102">\<删除 > 元素\<configSections ></span><span class="sxs-lookup"><span data-stu-id="2f058-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="2f058-103">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="2f058-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="2f058-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2f058-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="2f058-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="2f058-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="2f058-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="2f058-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2f058-107">语法</span><span class="sxs-lookup"><span data-stu-id="2f058-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="2f058-108">特性</span><span class="sxs-lookup"><span data-stu-id="2f058-108">Attribute</span></span>

|           | <span data-ttu-id="2f058-109">描述</span><span class="sxs-lookup"><span data-stu-id="2f058-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="2f058-110">**name**</span><span class="sxs-lookup"><span data-stu-id="2f058-110">**name**</span></span>  | <span data-ttu-id="2f058-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="2f058-111">Required attribute.</span></span><br><br><span data-ttu-id="2f058-112">指定的节或要删除的节组的名称。</span><span class="sxs-lookup"><span data-stu-id="2f058-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="2f058-113">父元素</span><span class="sxs-lookup"><span data-stu-id="2f058-113">Parent element</span></span>

|     | <span data-ttu-id="2f058-114">描述</span><span class="sxs-lookup"><span data-stu-id="2f058-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2f058-115">**\<configSections >** 元素</span><span class="sxs-lookup"><span data-stu-id="2f058-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="2f058-116">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="2f058-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2f058-117">子元素</span><span class="sxs-lookup"><span data-stu-id="2f058-117">Child elements</span></span>

<span data-ttu-id="2f058-118">无</span><span class="sxs-lookup"><span data-stu-id="2f058-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="2f058-119">备注</span><span class="sxs-lookup"><span data-stu-id="2f058-119">Remarks</span></span>

<span data-ttu-id="2f058-120">可以使用**\<删除 >** 元素从你在配置文件层次结构中较高级别定义的应用程序中删除节和节组。</span><span class="sxs-lookup"><span data-stu-id="2f058-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="2f058-121">示例</span><span class="sxs-lookup"><span data-stu-id="2f058-121">Example</span></span>

<span data-ttu-id="2f058-122">下面的示例演示如何使用**\<删除 >** 应用程序配置文件以删除以前在计算机配置文件中定义的节中的元素。</span><span class="sxs-lookup"><span data-stu-id="2f058-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="2f058-123">下面的计算机配置文件代码声明部分 **\<sampleSection >**:</span><span class="sxs-lookup"><span data-stu-id="2f058-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="2f058-124">下面的应用程序配置文件代码中删除 **\<sampleSection >** 部分。</span><span class="sxs-lookup"><span data-stu-id="2f058-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="2f058-125">删除后，应用程序不能检索中的设置 **\<sampleSection >**。</span><span class="sxs-lookup"><span data-stu-id="2f058-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="2f058-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="2f058-126">Configuration file</span></span>

<span data-ttu-id="2f058-127">在应用程序配置文件中，计算机配置文件可以使用此元素 (*Machine.config*)，并*Web.config*不在应用程序目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="2f058-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f058-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f058-128">See also</span></span>

- [<span data-ttu-id="2f058-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="2f058-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
