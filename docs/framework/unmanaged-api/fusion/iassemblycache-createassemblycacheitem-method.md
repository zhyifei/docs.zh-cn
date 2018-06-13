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
ms.openlocfilehash: c45257a76127adf2bcf9ab356639d4754d151bf6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430679"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="0263f-102">IAssemblyCache::CreateAssemblyCacheItem 方法</span><span class="sxs-lookup"><span data-stu-id="0263f-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="0263f-103">获取一个新的引用[IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="0263f-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0263f-104">语法</span><span class="sxs-lookup"><span data-stu-id="0263f-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0263f-105">参数</span><span class="sxs-lookup"><span data-stu-id="0263f-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="0263f-106">[in]在包括中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="0263f-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="0263f-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="0263f-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="0263f-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="0263f-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="0263f-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="0263f-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="0263f-110">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="0263f-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="0263f-111">`pvReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="0263f-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="0263f-112">[out]返回`IAssemblyCacheItem`指针。</span><span class="sxs-lookup"><span data-stu-id="0263f-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="0263f-113">[in，可选]Uncanonicalized、 以逗号分隔`name=value`对。</span><span class="sxs-lookup"><span data-stu-id="0263f-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0263f-114">要求</span><span class="sxs-lookup"><span data-stu-id="0263f-114">Requirements</span></span>  
 <span data-ttu-id="0263f-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0263f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0263f-116">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0263f-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0263f-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0263f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0263f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="0263f-118">See Also</span></span>  
 [<span data-ttu-id="0263f-119">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="0263f-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="0263f-120">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="0263f-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
