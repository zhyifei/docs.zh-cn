---
title: <configuration> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921252"
---
# <a name="configuration-element"></a><span data-ttu-id="8f55a-102">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="8f55a-102">\<configuration> element</span></span>

<span data-ttu-id="8f55a-103">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="8f55a-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="8f55a-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8f55a-105">语法</span><span class="sxs-lookup"><span data-stu-id="8f55a-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="8f55a-106">特性</span><span class="sxs-lookup"><span data-stu-id="8f55a-106">Attributes</span></span>

<span data-ttu-id="8f55a-107">无</span><span class="sxs-lookup"><span data-stu-id="8f55a-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="8f55a-108">父元素</span><span class="sxs-lookup"><span data-stu-id="8f55a-108">Parent element</span></span>

<span data-ttu-id="8f55a-109">无</span><span class="sxs-lookup"><span data-stu-id="8f55a-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="8f55a-110">子元素</span><span class="sxs-lookup"><span data-stu-id="8f55a-110">Child elements</span></span>

|     | <span data-ttu-id="8f55a-111">描述</span><span class="sxs-lookup"><span data-stu-id="8f55a-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8f55a-112"> **\<assemblyBinding>** </span><span class="sxs-lookup"><span data-stu-id="8f55a-112">**\<assemblyBinding>**</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="8f55a-113">指定配置级的程序集绑定策略。</span><span class="sxs-lookup"><span data-stu-id="8f55a-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="8f55a-114">启动 > 设置架构 **\<** </span><span class="sxs-lookup"><span data-stu-id="8f55a-114">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="8f55a-115">启动设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="8f55a-116">运行时 > 设置架构 **\<** </span><span class="sxs-lookup"><span data-stu-id="8f55a-116">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="8f55a-117">运行时设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="8f55a-118">[system.object > 设置架构 **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8f55a-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="8f55a-119">远程处理设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="8f55a-120">系统 .net > 设置架构 **\<** </span><span class="sxs-lookup"><span data-stu-id="8f55a-120">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="8f55a-121">网络设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="8f55a-122">g s > 设置架构 **\<** </span><span class="sxs-lookup"><span data-stu-id="8f55a-122">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="8f55a-123">加密设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="8f55a-124">配置 > 节架构 **\<** </span><span class="sxs-lookup"><span data-stu-id="8f55a-124">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="8f55a-125">配置节设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="8f55a-126">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="8f55a-126">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="8f55a-127">跟踪和调试设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="8f55a-128">[ASP.NET 配置设置架构](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8f55a-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="8f55a-129">ASP.NET 配置架构中的所有元素, 包括用于配置 ASP.NET 网站和应用程序的元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="8f55a-130">在 web.config文件中使用。</span><span class="sxs-lookup"><span data-stu-id="8f55a-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="8f55a-131">[webServices > 设置架构 **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8f55a-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="8f55a-132">Web 服务设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="8f55a-133">Web 设置架构</span><span class="sxs-lookup"><span data-stu-id="8f55a-133">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="8f55a-134">Web 设置架构中的所有元素，包括用于配置 ASP.NET 如何与主机应用程序（如 IIS）一起工作的元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="8f55a-135">用于*aspnet .config*文件中。</span><span class="sxs-lookup"><span data-stu-id="8f55a-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8f55a-136">备注</span><span class="sxs-lookup"><span data-stu-id="8f55a-136">Remarks</span></span>

<span data-ttu-id="8f55a-137">每个配置文件都必须只包含一个 **\<配置 >** 元素。</span><span class="sxs-lookup"><span data-stu-id="8f55a-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f55a-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f55a-138">See also</span></span>

- [<span data-ttu-id="8f55a-139">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="8f55a-139">Configuration file schema for the .NET Framework</span></span>](index.md)
