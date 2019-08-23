---
title: <configuration> 的 <assemblyBinding> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: e0b83c4b3573ab6819654e72cac1bf3e4a0ba637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921278"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="568ce-102">\<用于配置 > 的\<assemblyBinding > 元素</span><span class="sxs-lookup"><span data-stu-id="568ce-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="568ce-103">指定配置级的程序集绑定策略。</span><span class="sxs-lookup"><span data-stu-id="568ce-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="568ce-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="568ce-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="568ce-105">&nbsp;&nbsp; **\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="568ce-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="568ce-106">语法</span><span class="sxs-lookup"><span data-stu-id="568ce-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="568ce-107">特性</span><span class="sxs-lookup"><span data-stu-id="568ce-107">Attribute</span></span>

|           | <span data-ttu-id="568ce-108">描述</span><span class="sxs-lookup"><span data-stu-id="568ce-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="568ce-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="568ce-109">**xmlns**</span></span> | <span data-ttu-id="568ce-110">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="568ce-110">Required attribute.</span></span><br><br><span data-ttu-id="568ce-111">指定程序集绑定所需的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="568ce-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="568ce-112">使用字符串“urn: 架构-microsoft-com:asm.v1”作为值。</span><span class="sxs-lookup"><span data-stu-id="568ce-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="568ce-113">父元素</span><span class="sxs-lookup"><span data-stu-id="568ce-113">Parent element</span></span>

|     | <span data-ttu-id="568ce-114">描述</span><span class="sxs-lookup"><span data-stu-id="568ce-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="568ce-115"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="568ce-115">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="568ce-116">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="568ce-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="568ce-117">子元素</span><span class="sxs-lookup"><span data-stu-id="568ce-117">Child element</span></span>

|     | <span data-ttu-id="568ce-118">描述</span><span class="sxs-lookup"><span data-stu-id="568ce-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="568ce-119"> **\<linkedConfiguration>** </span><span class="sxs-lookup"><span data-stu-id="568ce-119">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="568ce-120">指定要包含的配置文件。</span><span class="sxs-lookup"><span data-stu-id="568ce-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="568ce-121">备注</span><span class="sxs-lookup"><span data-stu-id="568ce-121">Remarks</span></span>

<span data-ttu-id="568ce-122">LinkedConfiguration > 元素通过允许应用程序配置文件在已知位置中包含程序集配置文件来简化组件程序集的管理, 而不是复制程序集[ **\<** ](linkedconfiguration-element.md)配置设置。</span><span class="sxs-lookup"><span data-stu-id="568ce-122">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="568ce-123">对于具有 Windows 并行清单的应用程序, 不支持 **linkedConfiguration>元素。\<**</span><span class="sxs-lookup"><span data-stu-id="568ce-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="568ce-124">示例</span><span class="sxs-lookup"><span data-stu-id="568ce-124">Example</span></span>

<span data-ttu-id="568ce-125">下面的示例演示如何在本地硬盘上包含配置文件:</span><span class="sxs-lookup"><span data-stu-id="568ce-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="568ce-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="568ce-126">See also</span></span>

- [<span data-ttu-id="568ce-127">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="568ce-127">Configuration file schema for the .NET Framework</span></span>](index.md)
