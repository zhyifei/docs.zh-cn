---
title: "IAssemblyCache 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache
helpviewer_keywords: IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21ebc29a6c442625f7a532f7b1e6a47e7dc4cb69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="f2a31-102">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="f2a31-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="f2a31-103">合成技术表示使用全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="f2a31-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2a31-104">方法</span><span class="sxs-lookup"><span data-stu-id="f2a31-104">Methods</span></span>  
  
|<span data-ttu-id="f2a31-105">方法</span><span class="sxs-lookup"><span data-stu-id="f2a31-105">Method</span></span>|<span data-ttu-id="f2a31-106">描述</span><span class="sxs-lookup"><span data-stu-id="f2a31-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2a31-107">CreateAssemblyCacheItem 方法</span><span class="sxs-lookup"><span data-stu-id="f2a31-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="f2a31-108">获取一个新的引用[IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a31-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="f2a31-109">CreateAssemblyScavenger 方法</span><span class="sxs-lookup"><span data-stu-id="f2a31-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="f2a31-110">保留供内部使用合成技术。</span><span class="sxs-lookup"><span data-stu-id="f2a31-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="f2a31-111">InstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="f2a31-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="f2a31-112">将指定的程序集安装在全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="f2a31-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="f2a31-113">QueryAssemblyInfo 方法</span><span class="sxs-lookup"><span data-stu-id="f2a31-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="f2a31-114">获取有关指定的程序集的请求的数据。</span><span class="sxs-lookup"><span data-stu-id="f2a31-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="f2a31-115">UninstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="f2a31-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="f2a31-116">从全局程序集缓存中卸载指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="f2a31-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2a31-117">惠?</span><span class="sxs-lookup"><span data-stu-id="f2a31-117">Requirements</span></span>  
 <span data-ttu-id="f2a31-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a31-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2a31-119">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f2a31-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f2a31-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2a31-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a31-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2a31-121">See Also</span></span>  
 [<span data-ttu-id="f2a31-122">合成接口</span><span class="sxs-lookup"><span data-stu-id="f2a31-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="f2a31-123">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="f2a31-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
