---
title: 启动设置架构
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: e5f9c9af64ff38e7c0f1f26ccab039261b052e30
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083413"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="4199d-102">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="4199d-102">Startup settings schema</span></span>

<span data-ttu-id="4199d-103">启动设置会指定应运行应用程序的公共语言运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="4199d-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="4199d-104">元素</span><span class="sxs-lookup"><span data-stu-id="4199d-104">Element</span></span>|<span data-ttu-id="4199d-105">描述</span><span class="sxs-lookup"><span data-stu-id="4199d-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4199d-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="4199d-106">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="4199d-107">指定应用程序仅支持 1.0 版本的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="4199d-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="4199d-108">使用 1.1 版运行时生成的应用程序应使用 **\<supportedRuntime>** 元素。</span><span class="sxs-lookup"><span data-stu-id="4199d-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="4199d-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="4199d-109">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="4199d-110">指定应用程序支持的公共语言运行时版本。</span><span class="sxs-lookup"><span data-stu-id="4199d-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="4199d-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="4199d-111">\<startup></span></span>](startup-element.md)|<span data-ttu-id="4199d-112">包含 **\<requiredRuntime>** 和 **\<supportedRuntime>** 元素。</span><span class="sxs-lookup"><span data-stu-id="4199d-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4199d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4199d-113">See also</span></span>

- [<span data-ttu-id="4199d-114">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="4199d-114">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4199d-115">如何：将应用配置为支持 .NET Framework 4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="4199d-115">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
