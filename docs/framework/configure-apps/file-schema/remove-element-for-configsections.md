---
title: <remove> 的 <configSections> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 99d67bd621390789993caa4862e5ce379135eb92
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215392"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="88d5a-102">\<删除 \<configSections > 元素 ></span><span class="sxs-lookup"><span data-stu-id="88d5a-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="88d5a-103">删除预定义的节或节组。</span><span class="sxs-lookup"><span data-stu-id="88d5a-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="88d5a-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="88d5a-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="88d5a-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="88d5a-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="88d5a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="88d5a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="88d5a-107">语法</span><span class="sxs-lookup"><span data-stu-id="88d5a-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="88d5a-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="88d5a-108">Attribute</span></span>

|           | <span data-ttu-id="88d5a-109">说明</span><span class="sxs-lookup"><span data-stu-id="88d5a-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="88d5a-110">name</span><span class="sxs-lookup"><span data-stu-id="88d5a-110">**name**</span></span>  | <span data-ttu-id="88d5a-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="88d5a-111">Required attribute.</span></span><br><br><span data-ttu-id="88d5a-112">指定要删除的节或节组的名称。</span><span class="sxs-lookup"><span data-stu-id="88d5a-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="88d5a-113">父元素</span><span class="sxs-lookup"><span data-stu-id="88d5a-113">Parent element</span></span>

|     | <span data-ttu-id="88d5a-114">说明</span><span class="sxs-lookup"><span data-stu-id="88d5a-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="88d5a-115"> **\<configSections >** Element</span><span class="sxs-lookup"><span data-stu-id="88d5a-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="88d5a-116">包含配置节和命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="88d5a-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="88d5a-117">子元素</span><span class="sxs-lookup"><span data-stu-id="88d5a-117">Child elements</span></span>

<span data-ttu-id="88d5a-118">无</span><span class="sxs-lookup"><span data-stu-id="88d5a-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="88d5a-119">备注</span><span class="sxs-lookup"><span data-stu-id="88d5a-119">Remarks</span></span>

<span data-ttu-id="88d5a-120">你可以使用 **\<remove >** 元素从你的应用程序中删除在配置文件层次结构中较高级别上定义的部分和节组。</span><span class="sxs-lookup"><span data-stu-id="88d5a-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="88d5a-121">示例</span><span class="sxs-lookup"><span data-stu-id="88d5a-121">Example</span></span>

<span data-ttu-id="88d5a-122">下面的示例演示如何使用应用程序配置文件中的 **\<remove >** 元素删除之前在计算机配置文件中定义的部分。</span><span class="sxs-lookup"><span data-stu-id="88d5a-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="88d5a-123">以下计算机配置文件代码声明 **\<sampleSection >** 部分：</span><span class="sxs-lookup"><span data-stu-id="88d5a-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="88d5a-124">以下应用程序配置文件代码将删除 **\<sampleSection >** 部分。</span><span class="sxs-lookup"><span data-stu-id="88d5a-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="88d5a-125">删除后，应用程序无法检索 **\<sampleSection >** 中的设置。</span><span class="sxs-lookup"><span data-stu-id="88d5a-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="88d5a-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="88d5a-126">Configuration file</span></span>

<span data-ttu-id="88d5a-127">此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*</span><span class="sxs-lookup"><span data-stu-id="88d5a-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="88d5a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88d5a-128">See also</span></span>

- [<span data-ttu-id="88d5a-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="88d5a-129">Configuration file schema for the .NET Framework</span></span>](index.md)
