---
title: 程序集位置
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: d44fb44db35b60f99583c20432c5998573298044
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107215"
---
# <a name="assembly-location"></a><span data-ttu-id="bfe58-102">程序集位置</span><span class="sxs-lookup"><span data-stu-id="bfe58-102">Assembly location</span></span>
<span data-ttu-id="bfe58-103">程序集的位置决定公共语言运行时是否可以在引用该程序集时找到它，也可以决定是否可与其他程序集共享该程序集。</span><span class="sxs-lookup"><span data-stu-id="bfe58-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="bfe58-104">可以在以下位置部署程序集：</span><span class="sxs-lookup"><span data-stu-id="bfe58-104">You can deploy an assembly in the following locations:</span></span>  
  
- <span data-ttu-id="bfe58-105">应用程序的目录或子目录。</span><span class="sxs-lookup"><span data-stu-id="bfe58-105">The application's directory or subdirectories.</span></span>  
  
     <span data-ttu-id="bfe58-106">这是部署程序集最常用的位置。</span><span class="sxs-lookup"><span data-stu-id="bfe58-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="bfe58-107">应用程序根目录的子目录可以基于语言或区域性。</span><span class="sxs-lookup"><span data-stu-id="bfe58-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="bfe58-108">如果程序集具有 culture 特性中的信息，则它必须位于带有该区域性名称的应用程序目录下的子目录中。</span><span class="sxs-lookup"><span data-stu-id="bfe58-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>  
  
- <span data-ttu-id="bfe58-109">全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="bfe58-109">The global assembly cache.</span></span>  
  
     <span data-ttu-id="bfe58-110">这是安装于公共语言运行时安装位置的计算机范围内的代码缓存。</span><span class="sxs-lookup"><span data-stu-id="bfe58-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="bfe58-111">大多数情况下，如果要与多个应用程序共享程序集，应将程序集部署到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="bfe58-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>  
  
- <span data-ttu-id="bfe58-112">在 HTTP 服务器上。</span><span class="sxs-lookup"><span data-stu-id="bfe58-112">On an HTTP server.</span></span>  
  
     <span data-ttu-id="bfe58-113">部署在 HTTP 服务器上的程序集必须具有强名称，请在应用程序配置文件的基本代码节中指向此程序集。</span><span class="sxs-lookup"><span data-stu-id="bfe58-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe58-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfe58-114">See also</span></span>

- [<span data-ttu-id="bfe58-115">创建程序集</span><span class="sxs-lookup"><span data-stu-id="bfe58-115">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="bfe58-116">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="bfe58-116">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="bfe58-117">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="bfe58-117">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="bfe58-118">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="bfe58-118">Program with assemblies</span></span>](program.md)
