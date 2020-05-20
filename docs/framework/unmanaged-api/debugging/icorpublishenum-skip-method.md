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
ms.openlocfilehash: b68a9ec1e8fee4fdecd2114af28c75c4a236cb3a
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421136"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="90728-102">ICorPublishEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="90728-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="90728-103">按指定的项数在枚举中向前移动光标。</span><span class="sxs-lookup"><span data-stu-id="90728-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90728-104">语法</span><span class="sxs-lookup"><span data-stu-id="90728-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90728-105">参数</span><span class="sxs-lookup"><span data-stu-id="90728-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="90728-106">中游标向前移动的项数。</span><span class="sxs-lookup"><span data-stu-id="90728-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90728-107">要求</span><span class="sxs-lookup"><span data-stu-id="90728-107">Requirements</span></span>  
 <span data-ttu-id="90728-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90728-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90728-109">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="90728-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="90728-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90728-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90728-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90728-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90728-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90728-112">See also</span></span>

- [<span data-ttu-id="90728-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="90728-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
