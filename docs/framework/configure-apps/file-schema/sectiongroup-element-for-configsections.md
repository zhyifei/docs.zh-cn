---
title: <configSections> 的 <sectionGroup> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9113811557ded3a580a0bbacb24f2fe7e8d05ccf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114783"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="d3589-102">\<configSections \<sectionGroup > 元素 ></span><span class="sxs-lookup"><span data-stu-id="d3589-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="d3589-103">定义配置节的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d3589-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="d3589-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d3589-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="d3589-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d3589-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="d3589-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="d3589-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d3589-107">语法</span><span class="sxs-lookup"><span data-stu-id="d3589-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="d3589-108">特性</span><span class="sxs-lookup"><span data-stu-id="d3589-108">Attribute</span></span>

|           | <span data-ttu-id="d3589-109">描述</span><span class="sxs-lookup"><span data-stu-id="d3589-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d3589-110">**name**</span><span class="sxs-lookup"><span data-stu-id="d3589-110">**name**</span></span>  | <span data-ttu-id="d3589-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d3589-111">Required attribute.</span></span><br><br><span data-ttu-id="d3589-112">指定正在定义的节组的名称。</span><span class="sxs-lookup"><span data-stu-id="d3589-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d3589-113">父元素</span><span class="sxs-lookup"><span data-stu-id="d3589-113">Parent element</span></span>

|     | <span data-ttu-id="d3589-114">描述</span><span class="sxs-lookup"><span data-stu-id="d3589-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d3589-115"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="d3589-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="d3589-116">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="d3589-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d3589-117">子元素</span><span class="sxs-lookup"><span data-stu-id="d3589-117">Child elements</span></span>

|     | <span data-ttu-id="d3589-118">描述</span><span class="sxs-lookup"><span data-stu-id="d3589-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d3589-119"> **\<部分 >** </span><span class="sxs-lookup"><span data-stu-id="d3589-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="d3589-120">包含配置节声明。</span><span class="sxs-lookup"><span data-stu-id="d3589-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d3589-121">备注</span><span class="sxs-lookup"><span data-stu-id="d3589-121">Remarks</span></span>

<span data-ttu-id="d3589-122">声明节组将为配置节创建容器标记，并确保与其他人定义的配置节之间没有命名冲突。</span><span class="sxs-lookup"><span data-stu-id="d3589-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="d3589-123">可以将 **\<sectionGroup >** 元素嵌套在一起。</span><span class="sxs-lookup"><span data-stu-id="d3589-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="d3589-124">示例</span><span class="sxs-lookup"><span data-stu-id="d3589-124">Example</span></span>

<span data-ttu-id="d3589-125">下面的示例演示如何声明一个节组，并在节组中声明部分：</span><span class="sxs-lookup"><span data-stu-id="d3589-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="d3589-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="d3589-126">Configuration file</span></span>

<span data-ttu-id="d3589-127">此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*</span><span class="sxs-lookup"><span data-stu-id="d3589-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3589-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3589-128">See also</span></span>

- [<span data-ttu-id="d3589-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d3589-129">Configuration file schema for the .NET Framework</span></span>](index.md)
