---
title: 程序集位置
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: 0b84aba749625f0f86027cd9d09a5e9a2229a3f2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733124"
---
# <a name="assembly-location"></a><span data-ttu-id="82d5e-102">程序集位置</span><span class="sxs-lookup"><span data-stu-id="82d5e-102">Assembly location</span></span>
<span data-ttu-id="82d5e-103">程序集的位置决定公共语言运行时是否可以在引用该程序集时找到它，也可以决定是否可与其他程序集共享该程序集。</span><span class="sxs-lookup"><span data-stu-id="82d5e-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="82d5e-104">可以在以下位置部署程序集：</span><span class="sxs-lookup"><span data-stu-id="82d5e-104">You can deploy an assembly in the following locations:</span></span>

- <span data-ttu-id="82d5e-105">应用程序的目录或子目录。</span><span class="sxs-lookup"><span data-stu-id="82d5e-105">The application's directory or subdirectories.</span></span>

     <span data-ttu-id="82d5e-106">这是部署程序集最常用的位置。</span><span class="sxs-lookup"><span data-stu-id="82d5e-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="82d5e-107">应用程序根目录的子目录可以基于语言或区域性。</span><span class="sxs-lookup"><span data-stu-id="82d5e-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="82d5e-108">如果程序集具有 culture 特性中的信息，则它必须位于带有该区域性名称的应用程序目录下的子目录中。</span><span class="sxs-lookup"><span data-stu-id="82d5e-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>

- <span data-ttu-id="82d5e-109">全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="82d5e-109">The global assembly cache.</span></span>

     <span data-ttu-id="82d5e-110">这是安装于公共语言运行时安装位置的计算机范围内的代码缓存。</span><span class="sxs-lookup"><span data-stu-id="82d5e-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="82d5e-111">大多数情况下，如果要与多个应用程序共享程序集，应将程序集部署到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="82d5e-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>

- <span data-ttu-id="82d5e-112">在 HTTP 服务器上。</span><span class="sxs-lookup"><span data-stu-id="82d5e-112">On an HTTP server.</span></span>

     <span data-ttu-id="82d5e-113">部署在 HTTP 服务器上的程序集必须具有强名称，请在应用程序配置文件的基本代码节中指向此程序集。</span><span class="sxs-lookup"><span data-stu-id="82d5e-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="82d5e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="82d5e-114">See also</span></span>

- [<span data-ttu-id="82d5e-115">创建程序集</span><span class="sxs-lookup"><span data-stu-id="82d5e-115">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="82d5e-116">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="82d5e-116">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="82d5e-117">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="82d5e-117">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
