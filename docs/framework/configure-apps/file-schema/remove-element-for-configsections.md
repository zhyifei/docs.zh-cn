---
title: "&lt;删除&gt;元素&lt;configSections&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf2cb49fbeb01ad176a1d24d711cebc97ba14004
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="27706-102">\<删除 > 元素\<configSections ></span><span class="sxs-lookup"><span data-stu-id="27706-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="27706-103">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="27706-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="27706-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="27706-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="27706-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="27706-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="27706-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="27706-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="27706-107">语法</span><span class="sxs-lookup"><span data-stu-id="27706-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="27706-108">特性</span><span class="sxs-lookup"><span data-stu-id="27706-108">Attribute</span></span>

|           | <span data-ttu-id="27706-109">描述</span><span class="sxs-lookup"><span data-stu-id="27706-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="27706-110">**name**</span><span class="sxs-lookup"><span data-stu-id="27706-110">**name**</span></span>  | <span data-ttu-id="27706-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="27706-111">Required attribute.</span></span><br><br><span data-ttu-id="27706-112">指定的节或要删除的部分组的名称。</span><span class="sxs-lookup"><span data-stu-id="27706-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="27706-113">父元素</span><span class="sxs-lookup"><span data-stu-id="27706-113">Parent element</span></span>

|     | <span data-ttu-id="27706-114">描述</span><span class="sxs-lookup"><span data-stu-id="27706-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="27706-115">**\<configSections >**元素</span><span class="sxs-lookup"><span data-stu-id="27706-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="27706-116">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="27706-116">Contains configuration section and namespace declarations.</span></span> |

# <a name="child-elements"></a><span data-ttu-id="27706-117">子元素</span><span class="sxs-lookup"><span data-stu-id="27706-117">Child elements</span></span>

<span data-ttu-id="27706-118">无</span><span class="sxs-lookup"><span data-stu-id="27706-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="27706-119">备注</span><span class="sxs-lookup"><span data-stu-id="27706-119">Remarks</span></span>

<span data-ttu-id="27706-120">你可以使用**\<删除 >**元素从你在配置文件层次结构中较高级别定义的应用程序中删除节和节组。</span><span class="sxs-lookup"><span data-stu-id="27706-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="27706-121">示例</span><span class="sxs-lookup"><span data-stu-id="27706-121">Example</span></span>

<span data-ttu-id="27706-122">下面的示例演示如何使用**\<删除 >**删除先前在计算机配置文件中定义的节的应用程序配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="27706-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="27706-123">下面的计算机配置文件代码声明部分 **\<sampleSection >**:</span><span class="sxs-lookup"><span data-stu-id="27706-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="27706-124">下面的应用程序配置文件代码移除 **\<sampleSection >**部分。</span><span class="sxs-lookup"><span data-stu-id="27706-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="27706-125">删除之后，应用程序无法检索中的设置 **\<sampleSection >**。</span><span class="sxs-lookup"><span data-stu-id="27706-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="27706-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="27706-126">Configuration file</span></span>

<span data-ttu-id="27706-127">此元素可在应用程序配置文件中，计算机配置文件 (*Machine.config*)，和*Web.config*不在应用程序的目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="27706-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="27706-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="27706-128">See also</span></span>

[<span data-ttu-id="27706-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="27706-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
