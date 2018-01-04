---
title: "ICorDebugProcess5::GetTypeForTypeID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeForTypeID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4678575dba6210dc8c97f8ed18d5ded208a5c74e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="9f8d9-102">ICorDebugProcess5::GetTypeForTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="9f8d9-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="9f8d9-103">将转换为 ICorDebugType 值类型标识符。</span><span class="sxs-lookup"><span data-stu-id="9f8d9-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f8d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f8d9-104">Syntax</span></span>  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f8d9-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f8d9-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="9f8d9-106">[in]类型标识符中。</span><span class="sxs-lookup"><span data-stu-id="9f8d9-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="9f8d9-107">[out]指向 ICorDebugType 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="9f8d9-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f8d9-108">备注</span><span class="sxs-lookup"><span data-stu-id="9f8d9-108">Remarks</span></span>  
 <span data-ttu-id="9f8d9-109">在某些情况下，返回类型标识符的方法可能返回 null`COR_TYPEID`值。</span><span class="sxs-lookup"><span data-stu-id="9f8d9-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="9f8d9-110">如果此值作为传递`id`自变量，`GetTypeForTypeID`方法将失败并返回`E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="9f8d9-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f8d9-111">惠?</span><span class="sxs-lookup"><span data-stu-id="9f8d9-111">Requirements</span></span>  
 <span data-ttu-id="9f8d9-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f8d9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f8d9-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f8d9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f8d9-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f8d9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f8d9-115">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f8d9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8d9-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f8d9-116">See Also</span></span>  
 [<span data-ttu-id="9f8d9-117">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="9f8d9-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="9f8d9-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="9f8d9-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
