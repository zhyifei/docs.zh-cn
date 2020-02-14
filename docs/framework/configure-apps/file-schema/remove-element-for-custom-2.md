---
title: NameValueSectionHandler 和 DictionarySectionHandler 的 <remove> 元素
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214760"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="f02ba-102">\<删除 NameValueSectionHandler 和 DictionarySectionHandler 的 > 元素</span><span class="sxs-lookup"><span data-stu-id="f02ba-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="f02ba-103">删除以前定义的设置。</span><span class="sxs-lookup"><span data-stu-id="f02ba-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="f02ba-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f02ba-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="f02ba-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="f02ba-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="f02ba-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="f02ba-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f02ba-107">语法</span><span class="sxs-lookup"><span data-stu-id="f02ba-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="f02ba-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="f02ba-108">Attribute</span></span>

|           | <span data-ttu-id="f02ba-109">说明</span><span class="sxs-lookup"><span data-stu-id="f02ba-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f02ba-110">**键**</span><span class="sxs-lookup"><span data-stu-id="f02ba-110">**key**</span></span>   | <span data-ttu-id="f02ba-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="f02ba-111">Required attribute.</span></span><br><br><span data-ttu-id="f02ba-112">指定要删除的设置的名称。</span><span class="sxs-lookup"><span data-stu-id="f02ba-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f02ba-113">父元素</span><span class="sxs-lookup"><span data-stu-id="f02ba-113">Parent element</span></span>

| <span data-ttu-id="f02ba-114">元素</span><span class="sxs-lookup"><span data-stu-id="f02ba-114">Element</span></span> | <span data-ttu-id="f02ba-115">说明</span><span class="sxs-lookup"><span data-stu-id="f02ba-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="f02ba-116"> **\<sectionName >** Element</span><span class="sxs-lookup"><span data-stu-id="f02ba-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="f02ba-117">定义使用 <xref:System.Configuration.NameValueSectionHandler> 和 <xref:System.Configuration.DictionarySectionHandler> 类的自定义配置节的设置。</span><span class="sxs-lookup"><span data-stu-id="f02ba-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f02ba-118">子元素</span><span class="sxs-lookup"><span data-stu-id="f02ba-118">Child elements</span></span>

<span data-ttu-id="f02ba-119">无</span><span class="sxs-lookup"><span data-stu-id="f02ba-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="f02ba-120">备注</span><span class="sxs-lookup"><span data-stu-id="f02ba-120">Remarks</span></span>

<span data-ttu-id="f02ba-121">你可以使用 **\<remove >** 元素从你的应用程序中删除在配置文件层次结构中较高级别上定义的设置。</span><span class="sxs-lookup"><span data-stu-id="f02ba-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="f02ba-122">示例</span><span class="sxs-lookup"><span data-stu-id="f02ba-122">Example</span></span>

<span data-ttu-id="f02ba-123">下面的示例演示如何使用应用程序配置文件中的 **\<remove >** 元素删除以前在计算机配置文件中定义的设置。</span><span class="sxs-lookup"><span data-stu-id="f02ba-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="f02ba-124">以下计算机配置文件代码声明 **\<mySection >** 部分，并将两个设置（`key1` 和 `key2`）添加到其中：</span><span class="sxs-lookup"><span data-stu-id="f02ba-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="f02ba-125">以下应用程序配置文件代码将从 **\<mySection >** 中删除 `key2` 设置：</span><span class="sxs-lookup"><span data-stu-id="f02ba-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="f02ba-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="f02ba-126">Configuration file</span></span>

<span data-ttu-id="f02ba-127">此元素可用于应用程序配置文件、计算机配置文件（*machine.config*）和不在应用程序目录级别的*web.config 文件。*</span><span class="sxs-lookup"><span data-stu-id="f02ba-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f02ba-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f02ba-128">See also</span></span>

- [<span data-ttu-id="f02ba-129">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="f02ba-129">Configuration file schema for the .NET Framework</span></span>](index.md)
