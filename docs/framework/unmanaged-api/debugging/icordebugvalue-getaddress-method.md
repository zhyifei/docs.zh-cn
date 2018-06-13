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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c0fa19841580c7cfe8902577c3f756712a35893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420649"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="8ff01-102">ICorDebugValue::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="8ff01-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="8ff01-103">获取此"ICorDebugValue"对象，它是正在调试的过程中的地址。</span><span class="sxs-lookup"><span data-stu-id="8ff01-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff01-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ff01-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ff01-105">参数</span><span class="sxs-lookup"><span data-stu-id="8ff01-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="8ff01-106">[out]指向`CORDB_ADDRESS`对象，它指定此值对象的地址。</span><span class="sxs-lookup"><span data-stu-id="8ff01-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ff01-107">备注</span><span class="sxs-lookup"><span data-stu-id="8ff01-107">Remarks</span></span>  
 <span data-ttu-id="8ff01-108">如果值为不可用，则返回 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="8ff01-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="8ff01-109">此值是寄存器中至少一部分时可能发生或存储在垃圾回收器句柄 (`GCHandle`)。</span><span class="sxs-lookup"><span data-stu-id="8ff01-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ff01-110">要求</span><span class="sxs-lookup"><span data-stu-id="8ff01-110">Requirements</span></span>  
 <span data-ttu-id="8ff01-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ff01-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ff01-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ff01-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ff01-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ff01-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ff01-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ff01-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff01-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ff01-115">See Also</span></span>  
 
