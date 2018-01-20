---
title: "启动设置架构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f344139fd7d7c84aa75ab5e17b6312f3b0c3e031
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="startup-settings-schema"></a><span data-ttu-id="58f60-102">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="58f60-102">Startup Settings Schema</span></span>
<span data-ttu-id="58f60-103">启动设置会指定应运行应用程序的公共语言运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="58f60-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="58f60-104">元素</span><span class="sxs-lookup"><span data-stu-id="58f60-104">Element</span></span>|<span data-ttu-id="58f60-105">描述</span><span class="sxs-lookup"><span data-stu-id="58f60-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58f60-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="58f60-106">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="58f60-107">指定应用程序仅支持 1.0 版本的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="58f60-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="58f60-108">使用 1.1 版运行时生成的应用程序应使用 **\<supportedRuntime>** 元素。</span><span class="sxs-lookup"><span data-stu-id="58f60-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="58f60-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="58f60-109">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="58f60-110">指定应用程序支持的公共语言运行时版本。</span><span class="sxs-lookup"><span data-stu-id="58f60-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="58f60-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="58f60-111">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)|<span data-ttu-id="58f60-112">包含 **\<requiredRuntime>** 和 **\<supportedRuntime>** 元素。</span><span class="sxs-lookup"><span data-stu-id="58f60-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58f60-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="58f60-113">See Also</span></span>  
 [<span data-ttu-id="58f60-114">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="58f60-114">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="58f60-115">\<PaveOver> 指定要使用的运行时版本</span><span class="sxs-lookup"><span data-stu-id="58f60-115">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
