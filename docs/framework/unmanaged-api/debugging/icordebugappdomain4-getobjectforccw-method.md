---
title: ICorDebugAppDomain4::GetObjectForCCW 方法
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1089668aa19747f5f694360ebb87098e2df9ad4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405546"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="43a2b-102">ICorDebugAppDomain4::GetObjectForCCW 方法</span><span class="sxs-lookup"><span data-stu-id="43a2b-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="43a2b-103">从 COM 可调用包装器 (CCW) 指针获取托管对象。</span><span class="sxs-lookup"><span data-stu-id="43a2b-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43a2b-104">语法</span><span class="sxs-lookup"><span data-stu-id="43a2b-104">Syntax</span></span>  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43a2b-105">参数</span><span class="sxs-lookup"><span data-stu-id="43a2b-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="43a2b-106">[in] COM 可调用包装器 (CCW) 指针。</span><span class="sxs-lookup"><span data-stu-id="43a2b-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="43a2b-107">[out]指向表示给定 CCW 指针相对应的托管的对象的"ICorDebugValue"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="43a2b-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43a2b-108">备注</span><span class="sxs-lookup"><span data-stu-id="43a2b-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43a2b-109">要求</span><span class="sxs-lookup"><span data-stu-id="43a2b-109">Requirements</span></span>  
 <span data-ttu-id="43a2b-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43a2b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43a2b-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43a2b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43a2b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43a2b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43a2b-113">**.NET framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43a2b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43a2b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="43a2b-114">See Also</span></span>  
 [<span data-ttu-id="43a2b-115">ICorDebugAppDomain4 接口</span><span class="sxs-lookup"><span data-stu-id="43a2b-115">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [<span data-ttu-id="43a2b-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="43a2b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
