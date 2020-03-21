---
title: <configSections> 的 <remove> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154525"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="2971e-102">\<删除>元素以\<进行配置></span><span class="sxs-lookup"><span data-stu-id="2971e-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="2971e-103">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="2971e-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="2971e-104">[**\<配置>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2971e-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="2971e-105">&nbsp;&nbsp;[**\<配置部分>**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="2971e-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="2971e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<删除>**</span><span class="sxs-lookup"><span data-stu-id="2971e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2971e-107">语法</span><span class="sxs-lookup"><span data-stu-id="2971e-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="2971e-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="2971e-108">Attribute</span></span>

|           | <span data-ttu-id="2971e-109">说明</span><span class="sxs-lookup"><span data-stu-id="2971e-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="2971e-110">**name**</span><span class="sxs-lookup"><span data-stu-id="2971e-110">**name**</span></span>  | <span data-ttu-id="2971e-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="2971e-111">Required attribute.</span></span><br><br><span data-ttu-id="2971e-112">指定要删除的节或节组的名称。</span><span class="sxs-lookup"><span data-stu-id="2971e-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="2971e-113">父元素</span><span class="sxs-lookup"><span data-stu-id="2971e-113">Parent element</span></span>

|     | <span data-ttu-id="2971e-114">说明</span><span class="sxs-lookup"><span data-stu-id="2971e-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2971e-115">**\<配置部分>** 元素</span><span class="sxs-lookup"><span data-stu-id="2971e-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="2971e-116">包含配置部分和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="2971e-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2971e-117">子元素</span><span class="sxs-lookup"><span data-stu-id="2971e-117">Child elements</span></span>

<span data-ttu-id="2971e-118">无</span><span class="sxs-lookup"><span data-stu-id="2971e-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="2971e-119">备注</span><span class="sxs-lookup"><span data-stu-id="2971e-119">Remarks</span></span>

<span data-ttu-id="2971e-120">可以使用**\<删除>** 元素从应用程序中从配置文件层次结构中较高级别定义的节和节组中删除。</span><span class="sxs-lookup"><span data-stu-id="2971e-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="2971e-121">示例</span><span class="sxs-lookup"><span data-stu-id="2971e-121">Example</span></span>

<span data-ttu-id="2971e-122">下面的示例演示如何使用应用程序配置文件中的**\<删除>** 元素来删除以前在计算机配置文件中定义的部分。</span><span class="sxs-lookup"><span data-stu-id="2971e-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="2971e-123">以下计算机配置文件代码声明节**\<示例节>**：</span><span class="sxs-lookup"><span data-stu-id="2971e-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="2971e-124">以下应用程序配置文件代码将删除**\<示例节>** 部分。</span><span class="sxs-lookup"><span data-stu-id="2971e-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="2971e-125">删除后，应用程序无法检索**\<示例节>** 中的设置。</span><span class="sxs-lookup"><span data-stu-id="2971e-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="2971e-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="2971e-126">Configuration file</span></span>

<span data-ttu-id="2971e-127">此元素可用于应用程序配置文件、计算机配置文件 *（Machine.config*） 和*Web.config*文件，这些文件不在应用程序目录级别。</span><span class="sxs-lookup"><span data-stu-id="2971e-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2971e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2971e-128">See also</span></span>

- [<span data-ttu-id="2971e-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="2971e-129">Configuration file schema for the .NET Framework</span></span>](index.md)
