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
ms.openlocfilehash: 38f49e8fe632e9b38ede8815de6d8865278351f9
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421197"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="5c108-102">ICorPublishEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="5c108-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="5c108-103">创建此[ICorPublishEnum](icorpublishenum-interface.md)对象的副本。</span><span class="sxs-lookup"><span data-stu-id="5c108-103">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c108-104">语法</span><span class="sxs-lookup"><span data-stu-id="5c108-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c108-105">参数</span><span class="sxs-lookup"><span data-stu-id="5c108-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="5c108-106">弄指向作为 `ICorPublishEnum` 此对象副本的对象地址的指针 `ICorPublishEnum` 。</span><span class="sxs-lookup"><span data-stu-id="5c108-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c108-107">要求</span><span class="sxs-lookup"><span data-stu-id="5c108-107">Requirements</span></span>  
 <span data-ttu-id="5c108-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c108-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c108-109">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="5c108-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5c108-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c108-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c108-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c108-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c108-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c108-112">See also</span></span>

- [<span data-ttu-id="5c108-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="5c108-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
