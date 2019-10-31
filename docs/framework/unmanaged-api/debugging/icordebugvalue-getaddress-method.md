---
title: ICorDebugValue::GetAddress 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: 906ca2540e421953b3ce39300aa7b2376f789929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137100"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="0bae7-102">ICorDebugValue::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="0bae7-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="0bae7-103">获取此 "ICorDebugValue" 对象的地址，该对象处于调试过程中。</span><span class="sxs-lookup"><span data-stu-id="0bae7-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bae7-104">语法</span><span class="sxs-lookup"><span data-stu-id="0bae7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bae7-105">参数</span><span class="sxs-lookup"><span data-stu-id="0bae7-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="0bae7-106">弄指向 `CORDB_ADDRESS` 对象的指针，该对象指定此值对象的地址。</span><span class="sxs-lookup"><span data-stu-id="0bae7-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bae7-107">备注</span><span class="sxs-lookup"><span data-stu-id="0bae7-107">Remarks</span></span>  
 <span data-ttu-id="0bae7-108">如果值不可用，则返回0（零）。</span><span class="sxs-lookup"><span data-stu-id="0bae7-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="0bae7-109">如果值至少部分位于寄存器中或存储在垃圾回收器句柄（`GCHandle`）中，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="0bae7-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bae7-110">要求</span><span class="sxs-lookup"><span data-stu-id="0bae7-110">Requirements</span></span>  
 <span data-ttu-id="0bae7-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0bae7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bae7-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bae7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bae7-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bae7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bae7-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bae7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bae7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bae7-115">See also</span></span>
