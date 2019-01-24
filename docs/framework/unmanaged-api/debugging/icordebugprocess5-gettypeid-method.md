---
title: ICorDebugProcess5::GetTypeID 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cf72d0f41ee916db0e65cc6799217d19893628b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597094"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="dcba4-102">ICorDebugProcess5::GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="dcba4-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="dcba4-103">将转换的对象地址[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标识符。</span><span class="sxs-lookup"><span data-stu-id="dcba4-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcba4-104">语法</span><span class="sxs-lookup"><span data-stu-id="dcba4-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dcba4-105">参数</span><span class="sxs-lookup"><span data-stu-id="dcba4-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="dcba4-106">[in]对象的地址。</span><span class="sxs-lookup"><span data-stu-id="dcba4-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="dcba4-107">一个指向[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标识的对象的值。</span><span class="sxs-lookup"><span data-stu-id="dcba4-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcba4-108">备注</span><span class="sxs-lookup"><span data-stu-id="dcba4-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcba4-109">要求</span><span class="sxs-lookup"><span data-stu-id="dcba4-109">Requirements</span></span>  
 <span data-ttu-id="dcba4-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dcba4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcba4-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcba4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcba4-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcba4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcba4-113">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcba4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcba4-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcba4-114">See also</span></span>
- [<span data-ttu-id="dcba4-115">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="dcba4-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="dcba4-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="dcba4-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
