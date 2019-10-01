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
ms.openlocfilehash: 71b9e46a8c2d60c853af63ee78e2ed5dbe6e98f4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699137"
---
# <a name="web-settings-schema"></a><span data-ttu-id="1f618-102">Web 设置架构</span><span class="sxs-lookup"><span data-stu-id="1f618-102">Web Settings Schema</span></span>
<span data-ttu-id="1f618-103">Web 设置指定 CPU 和执行级别 ASP.NET 设置，后者应用于由 ASP.NET 承载层托管的进程范围行为。</span><span class="sxs-lookup"><span data-stu-id="1f618-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="1f618-104">这些设置与 ASP.NET 应用程序的 Web.config 文件中指定的应用程序域类型设置不同。</span><span class="sxs-lookup"><span data-stu-id="1f618-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="1f618-105">Web 设置包含在 Aspnet.config 文件中，该文件位于各版本 .NET Framework 的安装文件夹内。</span><span class="sxs-lookup"><span data-stu-id="1f618-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="1f618-106">例如，.NET Framework 2.0 的 Aspnet .config 文件位于以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="1f618-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="1f618-107">其他任何配置文件（如 machine.config 文件、根 Web.config 或应用程序级别的 Web.config 文件）中都不使用 Web 设置。</span><span class="sxs-lookup"><span data-stu-id="1f618-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
[<span data-ttu-id="1f618-108"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1f618-108">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1f618-109">&nbsp; @ no__t[ **\<system >** ](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1f618-109">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="1f618-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<applicationPool >** ](applicationpool-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1f618-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)</span></span>  
  
|<span data-ttu-id="1f618-111">元素</span><span class="sxs-lookup"><span data-stu-id="1f618-111">Element</span></span>|<span data-ttu-id="1f618-112">描述</span><span class="sxs-lookup"><span data-stu-id="1f618-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f618-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="1f618-113">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="1f618-114">包含 ASP.NET 承载层使用的信息。</span><span class="sxs-lookup"><span data-stu-id="1f618-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="1f618-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="1f618-115">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="1f618-116">指定 CPU 和执行级别 ASP.NET 设置，后者应用于由 ASP.NET 承载层托管的进程范围行为。</span><span class="sxs-lookup"><span data-stu-id="1f618-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1f618-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f618-117">See also</span></span>

- [<span data-ttu-id="1f618-118">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="1f618-118">Configuration File Schema</span></span>](../index.md)
