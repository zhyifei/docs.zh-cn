---
title: ICorPublishProcessEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 169716d1a6d0dd633821cc832de96c9a02958d76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183093"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="cded0-102">ICorPublishProcessEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="cded0-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="cded0-103">从集合中，从当前光标位置开始获取指定的进程数。</span><span class="sxs-lookup"><span data-stu-id="cded0-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cded0-104">语法</span><span class="sxs-lookup"><span data-stu-id="cded0-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cded0-105">参数</span><span class="sxs-lookup"><span data-stu-id="cded0-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cded0-106">[in]要检索的进程数。</span><span class="sxs-lookup"><span data-stu-id="cded0-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="cded0-107">[out]检索到的数组的指针[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)对象，其中每个表示的进程。</span><span class="sxs-lookup"><span data-stu-id="cded0-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="cded0-108">[out]指向实际返回的进程数。</span><span class="sxs-lookup"><span data-stu-id="cded0-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="cded0-109">此值可能为 null 如果`celt`是其中一个。</span><span class="sxs-lookup"><span data-stu-id="cded0-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cded0-110">要求</span><span class="sxs-lookup"><span data-stu-id="cded0-110">Requirements</span></span>  
 <span data-ttu-id="cded0-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cded0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cded0-112">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="cded0-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cded0-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cded0-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cded0-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="cded0-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cded0-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="cded0-115">See also</span></span>

- [<span data-ttu-id="cded0-116">ICorPublishProcessEnum 接口</span><span class="sxs-lookup"><span data-stu-id="cded0-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
