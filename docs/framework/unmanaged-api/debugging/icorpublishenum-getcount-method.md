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
ms.openlocfilehash: 0b3754fbcca50b52039dc358aed7070b8a152ead
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790635"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="33cbc-102">ICorPublishEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="33cbc-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="33cbc-103">获取枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="33cbc-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33cbc-104">语法</span><span class="sxs-lookup"><span data-stu-id="33cbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33cbc-105">参数</span><span class="sxs-lookup"><span data-stu-id="33cbc-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="33cbc-106">弄一个指针，指向枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="33cbc-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33cbc-107">需求</span><span class="sxs-lookup"><span data-stu-id="33cbc-107">Requirements</span></span>  
 <span data-ttu-id="33cbc-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33cbc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33cbc-109">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="33cbc-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="33cbc-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33cbc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33cbc-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33cbc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33cbc-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33cbc-112">See also</span></span>

- [<span data-ttu-id="33cbc-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="33cbc-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
