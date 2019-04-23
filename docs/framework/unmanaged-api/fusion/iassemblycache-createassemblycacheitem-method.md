---
title: IAssemblyCache::CreateAssemblyCacheItem 方法
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 648b641cbd2ec97305674451df06ce5be6a93a49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183685"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="921b4-102">IAssemblyCache::CreateAssemblyCacheItem 方法</span><span class="sxs-lookup"><span data-stu-id="921b4-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="921b4-103">获取一个新的引用[IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="921b4-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="921b4-104">语法</span><span class="sxs-lookup"><span data-stu-id="921b4-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="921b4-105">参数</span><span class="sxs-lookup"><span data-stu-id="921b4-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="921b4-106">[in]包括的标志。</span><span class="sxs-lookup"><span data-stu-id="921b4-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="921b4-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="921b4-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="921b4-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="921b4-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="921b4-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="921b4-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="921b4-110">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="921b4-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="921b4-111">`pvReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="921b4-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="921b4-112">[out]返回`IAssemblyCacheItem`指针。</span><span class="sxs-lookup"><span data-stu-id="921b4-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="921b4-113">[in，可选]Uncanonicalized、 以逗号分隔`name=value`对。</span><span class="sxs-lookup"><span data-stu-id="921b4-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="921b4-114">要求</span><span class="sxs-lookup"><span data-stu-id="921b4-114">Requirements</span></span>  
 <span data-ttu-id="921b4-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="921b4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="921b4-116">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="921b4-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="921b4-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="921b4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="921b4-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="921b4-118">See also</span></span>

- [<span data-ttu-id="921b4-119">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="921b4-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="921b4-120">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="921b4-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
