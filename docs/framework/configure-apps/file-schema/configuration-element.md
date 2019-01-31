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
ms.openlocfilehash: 980eb93a66de51250ac190cd44cfd32769ef5b8e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284695"
---
# <a name="configuration-element"></a><span data-ttu-id="1ef92-102">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="1ef92-102">\<configuration> element</span></span>

<span data-ttu-id="1ef92-103">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="1ef92-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="1ef92-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1ef92-105">语法</span><span class="sxs-lookup"><span data-stu-id="1ef92-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="1ef92-106">特性</span><span class="sxs-lookup"><span data-stu-id="1ef92-106">Attributes</span></span>

<span data-ttu-id="1ef92-107">无</span><span class="sxs-lookup"><span data-stu-id="1ef92-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="1ef92-108">父元素</span><span class="sxs-lookup"><span data-stu-id="1ef92-108">Parent element</span></span>

<span data-ttu-id="1ef92-109">无</span><span class="sxs-lookup"><span data-stu-id="1ef92-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="1ef92-110">子元素</span><span class="sxs-lookup"><span data-stu-id="1ef92-110">Child elements</span></span>

|     | <span data-ttu-id="1ef92-111">描述</span><span class="sxs-lookup"><span data-stu-id="1ef92-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1ef92-112">**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="1ef92-112">**\<assemblyBinding>**</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="1ef92-113">指定配置级的程序集绑定策略。</span><span class="sxs-lookup"><span data-stu-id="1ef92-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="1ef92-114">**\<启动 >** 设置架构</span><span class="sxs-lookup"><span data-stu-id="1ef92-114">**\<startup>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/startup/index.md) | <span data-ttu-id="1ef92-115">启动设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="1ef92-116">**\<运行时 >** 设置架构</span><span class="sxs-lookup"><span data-stu-id="1ef92-116">**\<runtime>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/runtime/index.md) | <span data-ttu-id="1ef92-117">在运行时设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-117">All elements in the runtime settings schema.</span></span> |
| [<span data-ttu-id="1ef92-118">**\<system.runtime.remoting >** 设置架构</span><span class="sxs-lookup"><span data-stu-id="1ef92-118">**\<system.runtime.remoting>** Settings Schema</span></span>](https://msdn.microsoft.com/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) | <span data-ttu-id="1ef92-119">远程处理设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="1ef92-120">**\<system.Net >** 设置架构</span><span class="sxs-lookup"><span data-stu-id="1ef92-120">**\<system.Net>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/network/index.md) | <span data-ttu-id="1ef92-121">网络设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="1ef92-122">**\<cryptographySettings >** 设置架构</span><span class="sxs-lookup"><span data-stu-id="1ef92-122">**\<cryptographySettings>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | <span data-ttu-id="1ef92-123">加密设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="1ef92-124">**\<配置 >** 节架构</span><span class="sxs-lookup"><span data-stu-id="1ef92-124">**\<configuration>** Sections Schema</span></span>](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | <span data-ttu-id="1ef92-125">配置部分设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="1ef92-126">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="1ef92-126">Trace and Debug Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | <span data-ttu-id="1ef92-127">跟踪和调试设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="1ef92-128">[ASP.NET 配置设置架构](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="1ef92-128">[ASP.NET Configuration Settings Schema](https://msdn.microsoft.com/library/b5ysx397(v=vs.100).aspx)</span></span> | <span data-ttu-id="1ef92-129">在 ASP.NET 配置架构中，其中包括用于配置 ASP.NET 网站和应用程序的元素的所有元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="1ef92-130">在中使用*Web.config*文件。</span><span class="sxs-lookup"><span data-stu-id="1ef92-130">Used in *Web.config* files.</span></span> |
| [<span data-ttu-id="1ef92-131">**\<webServices>** Settings Schema</span><span class="sxs-lookup"><span data-stu-id="1ef92-131">**\<webServices>** Settings Schema</span></span>](https://msdn.microsoft.com/f84d6d55-1add-4eb7-ae46-33df5833ea2e) | <span data-ttu-id="1ef92-132">Web 服务设置架构中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="1ef92-133">Web 设置架构</span><span class="sxs-lookup"><span data-stu-id="1ef92-133">Web Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/web/index.md) | <span data-ttu-id="1ef92-134">Web 设置架构中的所有元素，包括用于配置 ASP.NET 如何与主机应用程序（如 IIS）一起工作的元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="1ef92-135">在中使用*aspnet.config*文件。</span><span class="sxs-lookup"><span data-stu-id="1ef92-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1ef92-136">备注</span><span class="sxs-lookup"><span data-stu-id="1ef92-136">Remarks</span></span>

<span data-ttu-id="1ef92-137">每个配置文件必须包含一个**\<配置 >** 元素。</span><span class="sxs-lookup"><span data-stu-id="1ef92-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ef92-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ef92-138">See also</span></span>

- [<span data-ttu-id="1ef92-139">.NET Framework 的配置文件架构</span><span class="sxs-lookup"><span data-stu-id="1ef92-139">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
