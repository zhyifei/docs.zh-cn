---
title: ICorDebugComObjectValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
ms.openlocfilehash: 4ff5c0d470e6eb84eb8b526f5e8f74e5e1a8118a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125492"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="ab494-102">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="ab494-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="ab494-103">提供用于检索与运行时可调用包装（RCW）关联的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="ab494-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab494-104">方法</span><span class="sxs-lookup"><span data-stu-id="ab494-104">Methods</span></span>  
  
|<span data-ttu-id="ab494-105">方法</span><span class="sxs-lookup"><span data-stu-id="ab494-105">Method</span></span>|<span data-ttu-id="ab494-106">描述</span><span class="sxs-lookup"><span data-stu-id="ab494-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab494-107">GetCachedInterfacePointers 方法</span><span class="sxs-lookup"><span data-stu-id="ab494-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="ab494-108">获取缓存在当前 RCW 上的原始接口指针。</span><span class="sxs-lookup"><span data-stu-id="ab494-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="ab494-109">GetCachedInterfaceTypes 方法</span><span class="sxs-lookup"><span data-stu-id="ab494-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="ab494-110">为当前对象的大小写或用作的接口类型提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="ab494-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab494-111">备注</span><span class="sxs-lookup"><span data-stu-id="ab494-111">Remarks</span></span>  
 <span data-ttu-id="ab494-112">若要检查 "ICorDebugValue" 接口的实例是否表示 RCW，调试程序会使用 `IID_ICorDebugComObjectValue`调用 "ICorDebugValue" 上的 `QueryInterface`。</span><span class="sxs-lookup"><span data-stu-id="ab494-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab494-113">要求</span><span class="sxs-lookup"><span data-stu-id="ab494-113">Requirements</span></span>  
 <span data-ttu-id="ab494-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab494-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab494-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab494-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab494-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab494-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab494-117">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab494-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab494-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab494-118">See also</span></span>

- [<span data-ttu-id="ab494-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="ab494-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ab494-120">调试</span><span class="sxs-lookup"><span data-stu-id="ab494-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
