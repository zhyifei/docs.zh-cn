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
ms.openlocfilehash: b63c6ca8ead2a401f907ea6569e966c6470aca13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421946"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="4a226-102">ICorDebugProcess5::GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="4a226-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="4a226-103">将转换到的对象地址[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标识符。</span><span class="sxs-lookup"><span data-stu-id="4a226-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a226-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a226-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a226-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a226-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="4a226-106">[in]对象的地址。</span><span class="sxs-lookup"><span data-stu-id="4a226-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="4a226-107">指向的指针[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标识对象的值。</span><span class="sxs-lookup"><span data-stu-id="4a226-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a226-108">备注</span><span class="sxs-lookup"><span data-stu-id="4a226-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a226-109">要求</span><span class="sxs-lookup"><span data-stu-id="4a226-109">Requirements</span></span>  
 <span data-ttu-id="4a226-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a226-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a226-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a226-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a226-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a226-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a226-113">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a226-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a226-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a226-114">See Also</span></span>  
 [<span data-ttu-id="4a226-115">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="4a226-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="4a226-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="4a226-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
