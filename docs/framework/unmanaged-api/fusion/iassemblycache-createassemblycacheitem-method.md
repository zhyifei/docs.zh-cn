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
ms.openlocfilehash: e3e50538bde8fe3509b49e3dbcb031875e6863e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127123"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="e6181-102">IAssemblyCache::CreateAssemblyCacheItem 方法</span><span class="sxs-lookup"><span data-stu-id="e6181-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="e6181-103">获取对新的[IAssemblyCacheItem](iassemblycacheitem-interface.md)对象的引用。</span><span class="sxs-lookup"><span data-stu-id="e6181-103">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6181-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6181-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6181-105">参数</span><span class="sxs-lookup"><span data-stu-id="e6181-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="e6181-106">中在合成 .idl 中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="e6181-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="e6181-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="e6181-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="e6181-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH （0x00000001）</span><span class="sxs-lookup"><span data-stu-id="e6181-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="e6181-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH （0x00000002）</span><span class="sxs-lookup"><span data-stu-id="e6181-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e6181-110">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="e6181-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e6181-111">`pvReserved` 必须为空引用。</span><span class="sxs-lookup"><span data-stu-id="e6181-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="e6181-112">弄返回的 `IAssemblyCacheItem` 指针。</span><span class="sxs-lookup"><span data-stu-id="e6181-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="e6181-113">[in，可选]以逗号分隔 `name=value` 对的 Uncanonicalized。</span><span class="sxs-lookup"><span data-stu-id="e6181-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6181-114">要求</span><span class="sxs-lookup"><span data-stu-id="e6181-114">Requirements</span></span>  
 <span data-ttu-id="e6181-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6181-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6181-116">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="e6181-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e6181-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6181-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6181-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6181-118">See also</span></span>

- [<span data-ttu-id="e6181-119">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="e6181-119">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="e6181-120">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="e6181-120">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
