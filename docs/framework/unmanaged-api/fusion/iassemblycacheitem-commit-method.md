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
ms.openlocfilehash: 3757eee4c013ccf4f0f6d21ef64a92a5ffd70f19
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074308"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="c11fa-102">IAssemblyCacheItem::Commit 方法</span><span class="sxs-lookup"><span data-stu-id="c11fa-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="c11fa-103">提交对内存的缓存程序集引用。</span><span class="sxs-lookup"><span data-stu-id="c11fa-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c11fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="c11fa-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c11fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="c11fa-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="c11fa-106">[in]包括的标志。</span><span class="sxs-lookup"><span data-stu-id="c11fa-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="c11fa-107">[out，optional]一个值，指示操作的结果。</span><span class="sxs-lookup"><span data-stu-id="c11fa-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c11fa-108">要求</span><span class="sxs-lookup"><span data-stu-id="c11fa-108">Requirements</span></span>  
 <span data-ttu-id="c11fa-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c11fa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c11fa-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c11fa-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c11fa-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c11fa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c11fa-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c11fa-112">See also</span></span>

- [<span data-ttu-id="c11fa-113">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="c11fa-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
