---
title: ICorPublishEnum::Clone 方法
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12d9e468027e88cc74900364459f83d7e5125a9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423801"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="1d483-102">ICorPublishEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="1d483-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="1d483-103">创建一份[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="1d483-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d483-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d483-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d483-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d483-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="1d483-106">[out]指向的地址的指针`ICorPublishEnum`对象，它是一份`ICorPublishEnum`对象。</span><span class="sxs-lookup"><span data-stu-id="1d483-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d483-107">要求</span><span class="sxs-lookup"><span data-stu-id="1d483-107">Requirements</span></span>  
 <span data-ttu-id="1d483-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d483-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d483-109">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1d483-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1d483-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d483-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d483-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d483-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d483-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d483-112">See Also</span></span>  
 [<span data-ttu-id="1d483-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="1d483-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
