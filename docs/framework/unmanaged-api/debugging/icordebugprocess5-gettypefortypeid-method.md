---
title: ICorDebugProcess5::GetTypeForTypeID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9827d1c3f6e50172ad4f07137e9de0ff16564aab
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477955"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="90c51-102">ICorDebugProcess5::GetTypeForTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="90c51-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="90c51-103">转换为 ICorDebugType 值的类型标识符。</span><span class="sxs-lookup"><span data-stu-id="90c51-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c51-104">语法</span><span class="sxs-lookup"><span data-stu-id="90c51-104">Syntax</span></span>  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90c51-105">参数</span><span class="sxs-lookup"><span data-stu-id="90c51-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="90c51-106">[in]类型标识符。</span><span class="sxs-lookup"><span data-stu-id="90c51-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="90c51-107">[out]指向 ICorDebugType 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="90c51-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90c51-108">备注</span><span class="sxs-lookup"><span data-stu-id="90c51-108">Remarks</span></span>  
 <span data-ttu-id="90c51-109">在某些情况下，返回类型标识符的方法可能返回 null`COR_TYPEID`值。</span><span class="sxs-lookup"><span data-stu-id="90c51-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="90c51-110">如果此值将作为传递`id`参数，`GetTypeForTypeID`方法将失败并且返回`E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="90c51-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90c51-111">要求</span><span class="sxs-lookup"><span data-stu-id="90c51-111">Requirements</span></span>  
 <span data-ttu-id="90c51-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90c51-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90c51-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90c51-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90c51-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90c51-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90c51-115">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90c51-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c51-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="90c51-116">See also</span></span>
- [<span data-ttu-id="90c51-117">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="90c51-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="90c51-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="90c51-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
