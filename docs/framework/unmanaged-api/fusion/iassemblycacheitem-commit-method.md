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
ms.openlocfilehash: 5de522c00da76e7c01369c706cb7f9e2bdad4b3b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134519"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="d8ce7-102">IAssemblyCacheItem::Commit 方法</span><span class="sxs-lookup"><span data-stu-id="d8ce7-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="d8ce7-103">将缓存的程序集引用提交到内存。</span><span class="sxs-lookup"><span data-stu-id="d8ce7-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ce7-104">语法</span><span class="sxs-lookup"><span data-stu-id="d8ce7-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8ce7-105">参数</span><span class="sxs-lookup"><span data-stu-id="d8ce7-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="d8ce7-106">中在合成 .idl 中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="d8ce7-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="d8ce7-107">[out，optional]一个指示操作结果的值。</span><span class="sxs-lookup"><span data-stu-id="d8ce7-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8ce7-108">要求</span><span class="sxs-lookup"><span data-stu-id="d8ce7-108">Requirements</span></span>  
 <span data-ttu-id="d8ce7-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8ce7-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8ce7-110">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="d8ce7-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d8ce7-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8ce7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ce7-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8ce7-112">See also</span></span>

- [<span data-ttu-id="d8ce7-113">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="d8ce7-113">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
