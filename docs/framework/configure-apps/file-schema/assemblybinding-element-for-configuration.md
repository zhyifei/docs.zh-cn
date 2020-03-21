---
title: <configuration> 的 <assemblyBinding> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155474"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="dfa39-102">\<用于\<配置>的程序集绑定>元素</span><span class="sxs-lookup"><span data-stu-id="dfa39-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="dfa39-103">指定配置级的程序集绑定策略。</span><span class="sxs-lookup"><span data-stu-id="dfa39-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="dfa39-104">&nbsp;[**\<配置>**](configuration-element.md)&nbsp;**程序集绑定>\<**</span><span class="sxs-lookup"><span data-stu-id="dfa39-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="dfa39-105">语法</span><span class="sxs-lookup"><span data-stu-id="dfa39-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="dfa39-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="dfa39-106">Attribute</span></span>

|           | <span data-ttu-id="dfa39-107">说明</span><span class="sxs-lookup"><span data-stu-id="dfa39-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="dfa39-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="dfa39-108">**xmlns**</span></span> | <span data-ttu-id="dfa39-109">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="dfa39-109">Required attribute.</span></span><br><br><span data-ttu-id="dfa39-110">指定程序集绑定所需的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="dfa39-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="dfa39-111">使用字符串“urn: 架构-microsoft-com:asm.v1”作为值。</span><span class="sxs-lookup"><span data-stu-id="dfa39-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="dfa39-112">父元素</span><span class="sxs-lookup"><span data-stu-id="dfa39-112">Parent element</span></span>

|     | <span data-ttu-id="dfa39-113">说明</span><span class="sxs-lookup"><span data-stu-id="dfa39-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="dfa39-114">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="dfa39-114">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="dfa39-115">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="dfa39-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="dfa39-116">子元素</span><span class="sxs-lookup"><span data-stu-id="dfa39-116">Child element</span></span>

|     | <span data-ttu-id="dfa39-117">说明</span><span class="sxs-lookup"><span data-stu-id="dfa39-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="dfa39-118">**\<链接配置>**</span><span class="sxs-lookup"><span data-stu-id="dfa39-118">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="dfa39-119">指定要包含的配置文件。</span><span class="sxs-lookup"><span data-stu-id="dfa39-119">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="dfa39-120">备注</span><span class="sxs-lookup"><span data-stu-id="dfa39-120">Remarks</span></span>

<span data-ttu-id="dfa39-121">[**\<链接配置>**](linkedconfiguration-element.md)元素允许应用程序配置文件在已知位置包含程序集配置文件，而不是复制程序集配置设置，从而简化了组件程序集的管理。</span><span class="sxs-lookup"><span data-stu-id="dfa39-121">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="dfa39-122">对于具有 Windows 并行清单的应用程序，不支持**\<链接的配置>** 元素。</span><span class="sxs-lookup"><span data-stu-id="dfa39-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="dfa39-123">示例</span><span class="sxs-lookup"><span data-stu-id="dfa39-123">Example</span></span>

<span data-ttu-id="dfa39-124">下面的示例演示如何在本地硬盘上包含配置文件：</span><span class="sxs-lookup"><span data-stu-id="dfa39-124">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="dfa39-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfa39-125">See also</span></span>

- [<span data-ttu-id="dfa39-126">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="dfa39-126">Configuration file schema for the .NET Framework</span></span>](index.md)
