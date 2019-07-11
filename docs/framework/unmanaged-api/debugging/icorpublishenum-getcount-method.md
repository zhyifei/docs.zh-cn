---
title: ICorPublishEnum::GetCount 方法
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1465a667763c12593c4bc89148d70f85371fcc67
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775555"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="58a1e-102">ICorPublishEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="58a1e-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="58a1e-103">枚举中获取项的数目。</span><span class="sxs-lookup"><span data-stu-id="58a1e-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58a1e-104">语法</span><span class="sxs-lookup"><span data-stu-id="58a1e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58a1e-105">参数</span><span class="sxs-lookup"><span data-stu-id="58a1e-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="58a1e-106">[out]一个指向枚举中的项的数目。</span><span class="sxs-lookup"><span data-stu-id="58a1e-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58a1e-107">要求</span><span class="sxs-lookup"><span data-stu-id="58a1e-107">Requirements</span></span>  
 <span data-ttu-id="58a1e-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58a1e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58a1e-109">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="58a1e-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="58a1e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58a1e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58a1e-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58a1e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a1e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="58a1e-112">See also</span></span>

- [<span data-ttu-id="58a1e-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="58a1e-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
