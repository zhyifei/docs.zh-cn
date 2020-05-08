---
title: ICorDebugAppDomain4::GetObjectForCCW 方法
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: a175a6b6c91c284348580e1d9dc9ef0c5f5fc5df
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895122"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="655ff-102">ICorDebugAppDomain4::GetObjectForCCW 方法</span><span class="sxs-lookup"><span data-stu-id="655ff-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="655ff-103">从 COM 可调用包装器 (CCW) 指针获取托管对象。</span><span class="sxs-lookup"><span data-stu-id="655ff-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="655ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="655ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="655ff-105">参数</span><span class="sxs-lookup"><span data-stu-id="655ff-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="655ff-106">[in] COM 可调用包装器 (CCW) 指针。</span><span class="sxs-lookup"><span data-stu-id="655ff-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="655ff-107">弄一个指向 "ICorDebugValue" 对象地址的指针，该对象表示与给定的 CCW 指针相对应的托管对象。</span><span class="sxs-lookup"><span data-stu-id="655ff-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="655ff-108">备注</span><span class="sxs-lookup"><span data-stu-id="655ff-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="655ff-109">要求</span><span class="sxs-lookup"><span data-stu-id="655ff-109">Requirements</span></span>  
 <span data-ttu-id="655ff-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="655ff-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="655ff-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="655ff-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="655ff-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="655ff-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="655ff-113">**.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="655ff-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655ff-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="655ff-114">See also</span></span>

- [<span data-ttu-id="655ff-115">ICorDebugAppDomain4 接口</span><span class="sxs-lookup"><span data-stu-id="655ff-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="655ff-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="655ff-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
