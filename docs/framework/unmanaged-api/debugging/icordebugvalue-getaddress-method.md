---
title: "ICorDebugValue::GetAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetAddress
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7018dcb41f46d5407549f5c3d3029716781014e3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="fc13a-102">ICorDebugValue::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="fc13a-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="fc13a-103">获取此"ICorDebugValue"对象，它是正在调试的过程中的地址。</span><span class="sxs-lookup"><span data-stu-id="fc13a-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc13a-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc13a-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc13a-105">参数</span><span class="sxs-lookup"><span data-stu-id="fc13a-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="fc13a-106">[out]指向`CORDB_ADDRESS`对象，它指定此值对象的地址。</span><span class="sxs-lookup"><span data-stu-id="fc13a-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc13a-107">备注</span><span class="sxs-lookup"><span data-stu-id="fc13a-107">Remarks</span></span>  
 <span data-ttu-id="fc13a-108">如果值为不可用，则返回 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="fc13a-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="fc13a-109">此值是寄存器中至少一部分时可能发生或存储在垃圾回收器句柄 (`GCHandle`)。</span><span class="sxs-lookup"><span data-stu-id="fc13a-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc13a-110">要求</span><span class="sxs-lookup"><span data-stu-id="fc13a-110">Requirements</span></span>  
 <span data-ttu-id="fc13a-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc13a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc13a-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc13a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc13a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc13a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc13a-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc13a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc13a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc13a-115">See Also</span></span>  
 
