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
ms.openlocfilehash: d6f8a9c62a1be682d3f0259c27f311e2dcbb2f11
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492720"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="1a593-102">ICorDebugValue::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="1a593-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="1a593-103">获取此"ICorDebugValue"对象，它是正在调试的过程中的地址。</span><span class="sxs-lookup"><span data-stu-id="1a593-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a593-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a593-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a593-105">参数</span><span class="sxs-lookup"><span data-stu-id="1a593-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="1a593-106">[out]指向`CORDB_ADDRESS`对象，它指定此值对象的地址。</span><span class="sxs-lookup"><span data-stu-id="1a593-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a593-107">备注</span><span class="sxs-lookup"><span data-stu-id="1a593-107">Remarks</span></span>  
 <span data-ttu-id="1a593-108">如果值为不可用，则返回 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="1a593-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="1a593-109">这可能是如果值为至少一部分在寄存器中或存储在垃圾回收器句柄 (`GCHandle`)。</span><span class="sxs-lookup"><span data-stu-id="1a593-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a593-110">要求</span><span class="sxs-lookup"><span data-stu-id="1a593-110">Requirements</span></span>  
 <span data-ttu-id="1a593-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a593-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a593-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a593-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a593-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a593-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a593-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a593-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a593-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a593-115">See also</span></span>

