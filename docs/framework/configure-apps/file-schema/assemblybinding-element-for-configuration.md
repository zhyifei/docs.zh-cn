---
title: <assemblyBinding> 的 <configuration> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: f5992a6085c32d37f56319cf8b2c361542c441e7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257322"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="19b57-102">\<assemblyBinding > 元素\<配置 ></span><span class="sxs-lookup"><span data-stu-id="19b57-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="19b57-103">指定配置级的程序集绑定策略。</span><span class="sxs-lookup"><span data-stu-id="19b57-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="19b57-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="19b57-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="19b57-105">&nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="19b57-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="19b57-106">语法</span><span class="sxs-lookup"><span data-stu-id="19b57-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="19b57-107">特性</span><span class="sxs-lookup"><span data-stu-id="19b57-107">Attribute</span></span>

|           | <span data-ttu-id="19b57-108">描述</span><span class="sxs-lookup"><span data-stu-id="19b57-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="19b57-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="19b57-109">**xmlns**</span></span> | <span data-ttu-id="19b57-110">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="19b57-110">Required attribute.</span></span><br><br><span data-ttu-id="19b57-111">指定程序集绑定所需的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="19b57-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="19b57-112">使用字符串“urn: 架构-microsoft-com:asm.v1”作为值。</span><span class="sxs-lookup"><span data-stu-id="19b57-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="19b57-113">父元素</span><span class="sxs-lookup"><span data-stu-id="19b57-113">Parent element</span></span>

|     | <span data-ttu-id="19b57-114">描述</span><span class="sxs-lookup"><span data-stu-id="19b57-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="19b57-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="19b57-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="19b57-116">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="19b57-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="19b57-117">子元素</span><span class="sxs-lookup"><span data-stu-id="19b57-117">Child element</span></span>

|     | <span data-ttu-id="19b57-118">描述</span><span class="sxs-lookup"><span data-stu-id="19b57-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="19b57-119">**\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="19b57-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="19b57-120">指定要包含的配置文件。</span><span class="sxs-lookup"><span data-stu-id="19b57-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="19b57-121">备注</span><span class="sxs-lookup"><span data-stu-id="19b57-121">Remarks</span></span>

<span data-ttu-id="19b57-122">[  **\<LinkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)元素中的配置文件允许应用程序配置文件包含程序集，从而简化管理的组件程序集已知位置，而不是复制的程序集配置设置。</span><span class="sxs-lookup"><span data-stu-id="19b57-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="19b57-123"> *\*\<LinkedConfiguration >** 元素不支持使用 Windows 通过并行清单的应用程序。</span><span class="sxs-lookup"><span data-stu-id="19b57-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="19b57-124">示例</span><span class="sxs-lookup"><span data-stu-id="19b57-124">Example</span></span>

<span data-ttu-id="19b57-125">下面的示例演示如何包含本地硬盘上的配置文件：</span><span class="sxs-lookup"><span data-stu-id="19b57-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="19b57-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="19b57-126">See also</span></span>

- [<span data-ttu-id="19b57-127">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="19b57-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
