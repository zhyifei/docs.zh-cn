---
title: Web 设置架构
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 461043dbb57043c5c18ea703d45f8b3ae487d271
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47112278"
---
# <a name="web-settings-schema"></a><span data-ttu-id="e5a2b-102">Web 设置架构</span><span class="sxs-lookup"><span data-stu-id="e5a2b-102">Web Settings Schema</span></span>
<span data-ttu-id="e5a2b-103">Web 设置指定 CPU 和执行级别 ASP.NET 设置，后者应用于由 ASP.NET 承载层托管的进程范围行为。</span><span class="sxs-lookup"><span data-stu-id="e5a2b-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="e5a2b-104">这些设置与 ASP.NET 应用程序的 Web.config 文件中指定的应用程序域类型设置不同。</span><span class="sxs-lookup"><span data-stu-id="e5a2b-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
 <span data-ttu-id="e5a2b-105">Web 设置包含在 Aspnet.config 文件中，该文件位于各版本 .NET Framework 的安装文件夹内。</span><span class="sxs-lookup"><span data-stu-id="e5a2b-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="e5a2b-106">例如，[!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] 的 Aspnet.config 文件位于以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="e5a2b-106">For example, the Aspnet.config file for [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] is in the following folder:</span></span>  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 <span data-ttu-id="e5a2b-107">其他任何配置文件（如 machine.config 文件、根 Web.config 或应用程序级别的 Web.config 文件）中都不使用 Web 设置。</span><span class="sxs-lookup"><span data-stu-id="e5a2b-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
 [<span data-ttu-id="e5a2b-108">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="e5a2b-108">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="e5a2b-109">\<system.web> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="e5a2b-109">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [<span data-ttu-id="e5a2b-110">\<applicationPool> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="e5a2b-110">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|<span data-ttu-id="e5a2b-111">元素</span><span class="sxs-lookup"><span data-stu-id="e5a2b-111">Element</span></span>|<span data-ttu-id="e5a2b-112">描述</span><span class="sxs-lookup"><span data-stu-id="e5a2b-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5a2b-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="e5a2b-113">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="e5a2b-114">包含 ASP.NET 承载层使用的信息。</span><span class="sxs-lookup"><span data-stu-id="e5a2b-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="e5a2b-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="e5a2b-115">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="e5a2b-116">指定 CPU 和执行级别 ASP.NET 设置，后者应用于由 ASP.NET 承载层托管的进程范围行为。</span><span class="sxs-lookup"><span data-stu-id="e5a2b-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5a2b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5a2b-117">See Also</span></span>  
 [<span data-ttu-id="e5a2b-118">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="e5a2b-118">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
