---
title: IAssemblyCacheItem::Commit 方法
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f5cbb7c0b4e3ce6d66d30e812008fc3419d7d7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429087"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="ff741-102">IAssemblyCacheItem::Commit 方法</span><span class="sxs-lookup"><span data-stu-id="ff741-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="ff741-103">提交对内存的缓存的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="ff741-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff741-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff741-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff741-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff741-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="ff741-106">[in]在包括中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="ff741-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="ff741-107">[out，optional]一个值，指示该操作的结果。</span><span class="sxs-lookup"><span data-stu-id="ff741-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff741-108">要求</span><span class="sxs-lookup"><span data-stu-id="ff741-108">Requirements</span></span>  
 <span data-ttu-id="ff741-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff741-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff741-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ff741-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ff741-111">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff741-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff741-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff741-112">See Also</span></span>  
 [<span data-ttu-id="ff741-113">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="ff741-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
