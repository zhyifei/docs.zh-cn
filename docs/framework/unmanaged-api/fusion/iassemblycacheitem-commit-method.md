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
ms.openlocfilehash: f840438e175790a2b4c97302963b910f98dffb7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176560"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="343c2-102">IAssemblyCacheItem::Commit 方法</span><span class="sxs-lookup"><span data-stu-id="343c2-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="343c2-103">将缓存的程序集引用提交到内存。</span><span class="sxs-lookup"><span data-stu-id="343c2-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="343c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="343c2-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="343c2-105">parameters</span><span class="sxs-lookup"><span data-stu-id="343c2-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="343c2-106">[在]在 Fusion.idl 中定义的标志。</span><span class="sxs-lookup"><span data-stu-id="343c2-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="343c2-107">[退出，可选]指示操作结果的值。</span><span class="sxs-lookup"><span data-stu-id="343c2-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="343c2-108">要求</span><span class="sxs-lookup"><span data-stu-id="343c2-108">Requirements</span></span>  
 <span data-ttu-id="343c2-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="343c2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="343c2-110">**标题：** 融合.h</span><span class="sxs-lookup"><span data-stu-id="343c2-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="343c2-111">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="343c2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="343c2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="343c2-112">See also</span></span>

- [<span data-ttu-id="343c2-113">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="343c2-113">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
