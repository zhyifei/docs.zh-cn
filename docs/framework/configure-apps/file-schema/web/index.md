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
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47401480"
---
# <a name="web-settings-schema"></a><span data-ttu-id="cbd76-102">Web 设置架构</span><span class="sxs-lookup"><span data-stu-id="cbd76-102">Web Settings Schema</span></span>
<span data-ttu-id="cbd76-103">Web 设置指定 CPU 和执行级别 ASP.NET 设置，后者应用于由 ASP.NET 承载层托管的进程范围行为。</span><span class="sxs-lookup"><span data-stu-id="cbd76-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="cbd76-104">这些设置与 ASP.NET 应用程序的 Web.config 文件中指定的应用程序域类型设置不同。</span><span class="sxs-lookup"><span data-stu-id="cbd76-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
 <span data-ttu-id="cbd76-105">Web 设置包含在 Aspnet.config 文件中，该文件位于各版本 .NET Framework 的安装文件夹内。</span><span class="sxs-lookup"><span data-stu-id="cbd76-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="cbd76-106">例如，[!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] 的 Aspnet.config 文件位于以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="cbd76-106">For example, the Aspnet.config file for [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] is in the following folder:</span></span>  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 <span data-ttu-id="cbd76-107">其他任何配置文件（如 machine.config 文件、根 Web.config 或应用程序级别的 Web.config 文件）中都不使用 Web 设置。</span><span class="sxs-lookup"><span data-stu-id="cbd76-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
 [<span data-ttu-id="cbd76-108">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="cbd76-108">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="cbd76-109">\<system.web> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="cbd76-109">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [<span data-ttu-id="cbd76-110">\<applicationPool> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="cbd76-110">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|<span data-ttu-id="cbd76-111">元素</span><span class="sxs-lookup"><span data-stu-id="cbd76-111">Element</span></span>|<span data-ttu-id="cbd76-112">描述</span><span class="sxs-lookup"><span data-stu-id="cbd76-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbd76-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="cbd76-113">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="cbd76-114">包含 ASP.NET 承载层使用的信息。</span><span class="sxs-lookup"><span data-stu-id="cbd76-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="cbd76-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="cbd76-115">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="cbd76-116">指定 CPU 和执行级别 ASP.NET 设置，后者应用于由 ASP.NET 承载层托管的进程范围行为。</span><span class="sxs-lookup"><span data-stu-id="cbd76-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cbd76-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="cbd76-117">See Also</span></span>  
 [<span data-ttu-id="cbd76-118">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="cbd76-118">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
