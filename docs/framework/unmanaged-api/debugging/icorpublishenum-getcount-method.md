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
ms.openlocfilehash: a03b06143c0bd92425c7bfc13af6e374dc629f10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140476"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="13df6-102">ICorPublishEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="13df6-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="13df6-103">获取枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="13df6-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13df6-104">语法</span><span class="sxs-lookup"><span data-stu-id="13df6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13df6-105">参数</span><span class="sxs-lookup"><span data-stu-id="13df6-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="13df6-106">弄一个指针，指向枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="13df6-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13df6-107">要求</span><span class="sxs-lookup"><span data-stu-id="13df6-107">Requirements</span></span>  
 <span data-ttu-id="13df6-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13df6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13df6-109">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="13df6-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="13df6-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13df6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13df6-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13df6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13df6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="13df6-112">See also</span></span>

- [<span data-ttu-id="13df6-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="13df6-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
