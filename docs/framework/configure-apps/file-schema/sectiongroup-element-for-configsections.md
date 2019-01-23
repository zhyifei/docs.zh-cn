---
title: '&lt;sectionGroup&gt;元素&lt;configSections&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 82f89e74d6a09b2c157ff9a273f078e606222f63
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523891"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="cffb9-102">\<sectionGroup > 元素\<configSections ></span><span class="sxs-lookup"><span data-stu-id="cffb9-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="cffb9-103">定义配置节的命名空间。</span><span class="sxs-lookup"><span data-stu-id="cffb9-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="cffb9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="cffb9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="cffb9-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="cffb9-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="cffb9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="cffb9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="cffb9-107">语法</span><span class="sxs-lookup"><span data-stu-id="cffb9-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="cffb9-108">特性</span><span class="sxs-lookup"><span data-stu-id="cffb9-108">Attribute</span></span>

|           | <span data-ttu-id="cffb9-109">描述</span><span class="sxs-lookup"><span data-stu-id="cffb9-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="cffb9-110">**name**</span><span class="sxs-lookup"><span data-stu-id="cffb9-110">**name**</span></span>  | <span data-ttu-id="cffb9-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="cffb9-111">Required attribute.</span></span><br><br><span data-ttu-id="cffb9-112">指定正在定义的节组的名称。</span><span class="sxs-lookup"><span data-stu-id="cffb9-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="cffb9-113">父元素</span><span class="sxs-lookup"><span data-stu-id="cffb9-113">Parent element</span></span>

|     | <span data-ttu-id="cffb9-114">描述</span><span class="sxs-lookup"><span data-stu-id="cffb9-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="cffb9-115">**\<configSections >** 元素</span><span class="sxs-lookup"><span data-stu-id="cffb9-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="cffb9-116">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="cffb9-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="cffb9-117">子元素</span><span class="sxs-lookup"><span data-stu-id="cffb9-117">Child elements</span></span>

|     | <span data-ttu-id="cffb9-118">描述</span><span class="sxs-lookup"><span data-stu-id="cffb9-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="cffb9-119">**\<section>**</span><span class="sxs-lookup"><span data-stu-id="cffb9-119">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="cffb9-120">包含配置部分声明。</span><span class="sxs-lookup"><span data-stu-id="cffb9-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="cffb9-121">备注</span><span class="sxs-lookup"><span data-stu-id="cffb9-121">Remarks</span></span>

<span data-ttu-id="cffb9-122">声明部分组创建的配置节的容器标记，并可确保不存在命名冲突与定义的其他人配置节。</span><span class="sxs-lookup"><span data-stu-id="cffb9-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="cffb9-123">可以嵌套 **\<sectionGroup >** 中每个其他元素。</span><span class="sxs-lookup"><span data-stu-id="cffb9-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="cffb9-124">示例</span><span class="sxs-lookup"><span data-stu-id="cffb9-124">Example</span></span>

<span data-ttu-id="cffb9-125">下面的示例演示如何声明节组和声明组内的节的节：</span><span class="sxs-lookup"><span data-stu-id="cffb9-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="cffb9-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="cffb9-126">Configuration file</span></span>

<span data-ttu-id="cffb9-127">在应用程序配置文件中，计算机配置文件可以使用此元素 (*Machine.config*)，并*Web.config*不在应用程序目录级别上的文件。</span><span class="sxs-lookup"><span data-stu-id="cffb9-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="cffb9-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="cffb9-128">See also</span></span>

- [<span data-ttu-id="cffb9-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="cffb9-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
