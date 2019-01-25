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
ms.openlocfilehash: 9b39cdec6d5cc10256c2911c98f94b7565295408
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537993"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="1a43b-102">IAssemblyCacheItem::Commit 方法</span><span class="sxs-lookup"><span data-stu-id="1a43b-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="1a43b-103">提交对内存的缓存程序集引用。</span><span class="sxs-lookup"><span data-stu-id="1a43b-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a43b-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a43b-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a43b-105">参数</span><span class="sxs-lookup"><span data-stu-id="1a43b-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="1a43b-106">[in]包括的标志。</span><span class="sxs-lookup"><span data-stu-id="1a43b-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="1a43b-107">[out，optional]一个值，指示操作的结果。</span><span class="sxs-lookup"><span data-stu-id="1a43b-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a43b-108">要求</span><span class="sxs-lookup"><span data-stu-id="1a43b-108">Requirements</span></span>  
 <span data-ttu-id="1a43b-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a43b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a43b-110">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1a43b-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1a43b-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a43b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a43b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a43b-112">See also</span></span>
- [<span data-ttu-id="1a43b-113">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="1a43b-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
