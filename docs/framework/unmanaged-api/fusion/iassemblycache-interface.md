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
ms.openlocfilehash: 6244e6c3b0cc88c50cda050a480f5af5b3996b47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="40e2b-102">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="40e2b-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="40e2b-103">合成技术表示使用全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="40e2b-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40e2b-104">方法</span><span class="sxs-lookup"><span data-stu-id="40e2b-104">Methods</span></span>  
  
|<span data-ttu-id="40e2b-105">方法</span><span class="sxs-lookup"><span data-stu-id="40e2b-105">Method</span></span>|<span data-ttu-id="40e2b-106">描述</span><span class="sxs-lookup"><span data-stu-id="40e2b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40e2b-107">CreateAssemblyCacheItem 方法</span><span class="sxs-lookup"><span data-stu-id="40e2b-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="40e2b-108">获取一个新的引用[IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="40e2b-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="40e2b-109">CreateAssemblyScavenger 方法</span><span class="sxs-lookup"><span data-stu-id="40e2b-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="40e2b-110">保留供内部使用合成技术。</span><span class="sxs-lookup"><span data-stu-id="40e2b-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="40e2b-111">InstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="40e2b-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="40e2b-112">将指定的程序集安装在全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="40e2b-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="40e2b-113">QueryAssemblyInfo 方法</span><span class="sxs-lookup"><span data-stu-id="40e2b-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="40e2b-114">获取有关指定的程序集的请求的数据。</span><span class="sxs-lookup"><span data-stu-id="40e2b-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="40e2b-115">UninstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="40e2b-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="40e2b-116">从全局程序集缓存中卸载指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="40e2b-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40e2b-117">要求</span><span class="sxs-lookup"><span data-stu-id="40e2b-117">Requirements</span></span>  
 <span data-ttu-id="40e2b-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40e2b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e2b-119">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="40e2b-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="40e2b-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40e2b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e2b-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40e2b-121">See Also</span></span>  
 [<span data-ttu-id="40e2b-122">合成接口</span><span class="sxs-lookup"><span data-stu-id="40e2b-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="40e2b-123">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="40e2b-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
