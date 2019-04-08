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
ms.openlocfilehash: 9fc5f3a3d5bc5699a596bcc648a7153190c130f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075623"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="15f8d-102">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="15f8d-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="15f8d-103">合成技术表示全局程序集缓存中的供使用。</span><span class="sxs-lookup"><span data-stu-id="15f8d-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15f8d-104">方法</span><span class="sxs-lookup"><span data-stu-id="15f8d-104">Methods</span></span>  
  
|<span data-ttu-id="15f8d-105">方法</span><span class="sxs-lookup"><span data-stu-id="15f8d-105">Method</span></span>|<span data-ttu-id="15f8d-106">描述</span><span class="sxs-lookup"><span data-stu-id="15f8d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15f8d-107">CreateAssemblyCacheItem 方法</span><span class="sxs-lookup"><span data-stu-id="15f8d-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="15f8d-108">获取一个新的引用[IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="15f8d-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="15f8d-109">CreateAssemblyScavenger 方法</span><span class="sxs-lookup"><span data-stu-id="15f8d-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="15f8d-110">合成技术，保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="15f8d-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="15f8d-111">InstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="15f8d-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="15f8d-112">将指定的程序集安装在全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="15f8d-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="15f8d-113">QueryAssemblyInfo 方法</span><span class="sxs-lookup"><span data-stu-id="15f8d-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="15f8d-114">获取有关指定的程序集的请求的数据。</span><span class="sxs-lookup"><span data-stu-id="15f8d-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="15f8d-115">UninstallAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="15f8d-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="15f8d-116">从全局程序集缓存中卸载指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="15f8d-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15f8d-117">要求</span><span class="sxs-lookup"><span data-stu-id="15f8d-117">Requirements</span></span>  
 <span data-ttu-id="15f8d-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15f8d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15f8d-119">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="15f8d-119">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="15f8d-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="15f8d-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15f8d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="15f8d-121">See also</span></span>

- [<span data-ttu-id="15f8d-122">合成接口</span><span class="sxs-lookup"><span data-stu-id="15f8d-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="15f8d-123">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="15f8d-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
