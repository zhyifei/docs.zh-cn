---
title: '&lt;assemblyBinding&gt;元素&lt;配置&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 12065d8bc484f7bbf77ae18c67df1de0845167b2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083894"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="2d270-102">\<assemblyBinding > 元素\<配置 ></span><span class="sxs-lookup"><span data-stu-id="2d270-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="2d270-103">指定配置级的程序集绑定策略。</span><span class="sxs-lookup"><span data-stu-id="2d270-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="2d270-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2d270-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="2d270-105">&nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="2d270-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2d270-106">语法</span><span class="sxs-lookup"><span data-stu-id="2d270-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="2d270-107">特性</span><span class="sxs-lookup"><span data-stu-id="2d270-107">Attribute</span></span>

|           | <span data-ttu-id="2d270-108">描述</span><span class="sxs-lookup"><span data-stu-id="2d270-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="2d270-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="2d270-109">**xmlns**</span></span> | <span data-ttu-id="2d270-110">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="2d270-110">Required attribute.</span></span><br><br><span data-ttu-id="2d270-111">指定程序集绑定所需的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="2d270-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="2d270-112">使用字符串“urn: 架构-microsoft-com:asm.v1”作为值。</span><span class="sxs-lookup"><span data-stu-id="2d270-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="2d270-113">父元素</span><span class="sxs-lookup"><span data-stu-id="2d270-113">Parent element</span></span>

|     | <span data-ttu-id="2d270-114">描述</span><span class="sxs-lookup"><span data-stu-id="2d270-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2d270-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="2d270-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="2d270-116">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="2d270-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="2d270-117">子元素</span><span class="sxs-lookup"><span data-stu-id="2d270-117">Child element</span></span>

|     | <span data-ttu-id="2d270-118">描述</span><span class="sxs-lookup"><span data-stu-id="2d270-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2d270-119">**\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="2d270-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="2d270-120">指定要包含的配置文件。</span><span class="sxs-lookup"><span data-stu-id="2d270-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2d270-121">备注</span><span class="sxs-lookup"><span data-stu-id="2d270-121">Remarks</span></span>

<span data-ttu-id="2d270-122">[  **\<LinkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)元素中的配置文件允许应用程序配置文件包含程序集，从而简化管理的组件程序集已知位置，而不是复制的程序集配置设置。</span><span class="sxs-lookup"><span data-stu-id="2d270-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="2d270-123"> *\*\<LinkedConfiguration >** 元素不支持使用 Windows 通过并行清单的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2d270-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="2d270-124">示例</span><span class="sxs-lookup"><span data-stu-id="2d270-124">Example</span></span>

<span data-ttu-id="2d270-125">下面的示例演示如何包含本地硬盘上的配置文件：</span><span class="sxs-lookup"><span data-stu-id="2d270-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2d270-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d270-126">See also</span></span>

- [<span data-ttu-id="2d270-127">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="2d270-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
