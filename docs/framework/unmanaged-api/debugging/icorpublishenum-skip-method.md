---
title: ICorPublishEnum::Skip 方法
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a691f61fcd25b7aaaae90e6adcc3c2ee0c421cf0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424253"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="ff959-102">ICorPublishEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="ff959-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="ff959-103">将光标向前移动在枚举中指定数目的项。</span><span class="sxs-lookup"><span data-stu-id="ff959-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff959-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff959-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff959-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff959-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ff959-106">[in]向前移动光标所依据的项的数目。</span><span class="sxs-lookup"><span data-stu-id="ff959-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff959-107">要求</span><span class="sxs-lookup"><span data-stu-id="ff959-107">Requirements</span></span>  
 <span data-ttu-id="ff959-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff959-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff959-109">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ff959-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ff959-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff959-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff959-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff959-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff959-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff959-112">See Also</span></span>  
 [<span data-ttu-id="ff959-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="ff959-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
