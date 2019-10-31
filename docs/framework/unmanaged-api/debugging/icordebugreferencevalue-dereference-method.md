---
title: ICorDebugReferenceValue::Dereference 方法
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: 6bb2a6b68a3c6e981a2d6c833d3f44d4c836bd23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123999"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="30690-102">ICorDebugReferenceValue::Dereference 方法</span><span class="sxs-lookup"><span data-stu-id="30690-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="30690-103">获取所引用的对象。</span><span class="sxs-lookup"><span data-stu-id="30690-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30690-104">语法</span><span class="sxs-lookup"><span data-stu-id="30690-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30690-105">参数</span><span class="sxs-lookup"><span data-stu-id="30690-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="30690-106">弄一个指针，指向表示此 ICorDebugReferenceValue 对象指向的对象的 ICorDebugValue 的地址。</span><span class="sxs-lookup"><span data-stu-id="30690-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30690-107">备注</span><span class="sxs-lookup"><span data-stu-id="30690-107">Remarks</span></span>  
 <span data-ttu-id="30690-108">仅当 `ICorDebugValue` 对象的引用尚未禁用时，它才有效。</span><span class="sxs-lookup"><span data-stu-id="30690-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30690-109">要求</span><span class="sxs-lookup"><span data-stu-id="30690-109">Requirements</span></span>  
 <span data-ttu-id="30690-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30690-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30690-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30690-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30690-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30690-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30690-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30690-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
