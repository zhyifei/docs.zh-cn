---
title: IAssemblyCache 接口
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157cc9f5f520f376c0c055ab49b116bc7961f421
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641065"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="33ef7-102">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="33ef7-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="33ef7-103">合成技术表示全局程序集缓存中的供使用。</span><span class="sxs-lookup"><span data-stu-id="33ef7-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33ef7-104">方法</span><span class="sxs-lookup"><span data-stu-id="33ef7-104">Methods</span></span>  
  
|<span data-ttu-id="33ef7-105">方法</span><span class="sxs-lookup"><span data-stu-id="33ef7-105">Method</span></span>|<span data-ttu-id="33ef7-106">描述</span><span class="sxs-lookup"><span data-stu-id="33ef7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33ef7-107">CreateAssemblyCacheItem 方法</span><span class="sxs-lookup"><span data-stu-id="33ef7-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="33ef7-108">获取一个新的引用[IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="33ef7-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="33ef7-109">CreateAssemblyScavenger 方法</span><span class="sxs-lookup"><span data-stu-id="33ef7-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="33ef7-110">合成技术，保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="33ef7-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="33ef7-111">InstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="33ef7-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="33ef7-112">将指定的程序集安装在全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="33ef7-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="33ef7-113">QueryAssemblyInfo 方法</span><span class="sxs-lookup"><span data-stu-id="33ef7-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="33ef7-114">获取有关指定的程序集的请求的数据。</span><span class="sxs-lookup"><span data-stu-id="33ef7-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="33ef7-115">UninstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="33ef7-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="33ef7-116">从全局程序集缓存中卸载指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="33ef7-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33ef7-117">要求</span><span class="sxs-lookup"><span data-stu-id="33ef7-117">Requirements</span></span>  
 <span data-ttu-id="33ef7-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33ef7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33ef7-119">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="33ef7-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="33ef7-120">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33ef7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ef7-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="33ef7-121">See also</span></span>
- [<span data-ttu-id="33ef7-122">合成接口</span><span class="sxs-lookup"><span data-stu-id="33ef7-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="33ef7-123">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="33ef7-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
