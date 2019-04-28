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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3387985ebf6027b9cd9dee372190da65939dbae3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749691"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="3e280-102">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="3e280-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="3e280-103">提供方法来检索与运行时可调用包装 (RCW) 关联的信息。</span><span class="sxs-lookup"><span data-stu-id="3e280-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e280-104">方法</span><span class="sxs-lookup"><span data-stu-id="3e280-104">Methods</span></span>  
  
|<span data-ttu-id="3e280-105">方法</span><span class="sxs-lookup"><span data-stu-id="3e280-105">Method</span></span>|<span data-ttu-id="3e280-106">描述</span><span class="sxs-lookup"><span data-stu-id="3e280-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e280-107">GetCachedInterfacePointers 方法</span><span class="sxs-lookup"><span data-stu-id="3e280-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="3e280-108">获取当前 RCW 上缓存的原始接口指针。</span><span class="sxs-lookup"><span data-stu-id="3e280-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="3e280-109">GetCachedInterfaceTypes 方法</span><span class="sxs-lookup"><span data-stu-id="3e280-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="3e280-110">当前对象具有大小写转换为或用作接口类型提供的枚举器。</span><span class="sxs-lookup"><span data-stu-id="3e280-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e280-111">备注</span><span class="sxs-lookup"><span data-stu-id="3e280-111">Remarks</span></span>  
 <span data-ttu-id="3e280-112">若要检查"ICorDebugValue"接口的实例是否表示一个 RCW，调试器将调用`QueryInterface`上与"ICorDebugValue" `IID_ICorDebugComObjectValue`。</span><span class="sxs-lookup"><span data-stu-id="3e280-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e280-113">要求</span><span class="sxs-lookup"><span data-stu-id="3e280-113">Requirements</span></span>  
 <span data-ttu-id="3e280-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3e280-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e280-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e280-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e280-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e280-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e280-117">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e280-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e280-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e280-118">See also</span></span>

- [<span data-ttu-id="3e280-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="3e280-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3e280-120">调试</span><span class="sxs-lookup"><span data-stu-id="3e280-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
