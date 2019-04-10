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
ms.openlocfilehash: 07c23a32037e83a878bb3136c48176f19249b207
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173182"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="2dc7f-102">ICorDebugProcess5::GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="2dc7f-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="2dc7f-103">将转换的对象地址[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标识符。</span><span class="sxs-lookup"><span data-stu-id="2dc7f-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dc7f-104">语法</span><span class="sxs-lookup"><span data-stu-id="2dc7f-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dc7f-105">参数</span><span class="sxs-lookup"><span data-stu-id="2dc7f-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="2dc7f-106">[in]对象的地址。</span><span class="sxs-lookup"><span data-stu-id="2dc7f-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="2dc7f-107">一个指向[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标识的对象的值。</span><span class="sxs-lookup"><span data-stu-id="2dc7f-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dc7f-108">备注</span><span class="sxs-lookup"><span data-stu-id="2dc7f-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dc7f-109">要求</span><span class="sxs-lookup"><span data-stu-id="2dc7f-109">Requirements</span></span>  
 <span data-ttu-id="2dc7f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2dc7f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dc7f-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2dc7f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2dc7f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dc7f-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2dc7f-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="2dc7f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2dc7f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2dc7f-114">See also</span></span>

- [<span data-ttu-id="2dc7f-115">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="2dc7f-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="2dc7f-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="2dc7f-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
