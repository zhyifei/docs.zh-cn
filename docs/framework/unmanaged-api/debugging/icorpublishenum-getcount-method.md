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
ms.openlocfilehash: 7ed4236187fab1c1e81be9ddcdff1f1852e38f70
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421184"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="a75a2-102">ICorPublishEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="a75a2-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="a75a2-103">获取枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="a75a2-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a75a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="a75a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a75a2-105">参数</span><span class="sxs-lookup"><span data-stu-id="a75a2-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="a75a2-106">弄一个指针，指向枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="a75a2-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a75a2-107">要求</span><span class="sxs-lookup"><span data-stu-id="a75a2-107">Requirements</span></span>  
 <span data-ttu-id="a75a2-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a75a2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a75a2-109">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="a75a2-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a75a2-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a75a2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a75a2-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a75a2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a75a2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a75a2-112">See also</span></span>

- [<span data-ttu-id="a75a2-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="a75a2-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
