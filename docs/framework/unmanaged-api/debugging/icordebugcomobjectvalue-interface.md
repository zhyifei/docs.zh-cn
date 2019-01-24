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
ms.openlocfilehash: 4db005e1de043e60ffe958de732a5280fcccbea7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529942"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="a60ad-102">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="a60ad-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="a60ad-103">提供方法来检索与运行时可调用包装 (RCW) 关联的信息。</span><span class="sxs-lookup"><span data-stu-id="a60ad-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a60ad-104">方法</span><span class="sxs-lookup"><span data-stu-id="a60ad-104">Methods</span></span>  
  
|<span data-ttu-id="a60ad-105">方法</span><span class="sxs-lookup"><span data-stu-id="a60ad-105">Method</span></span>|<span data-ttu-id="a60ad-106">描述</span><span class="sxs-lookup"><span data-stu-id="a60ad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a60ad-107">GetCachedInterfacePointers 方法</span><span class="sxs-lookup"><span data-stu-id="a60ad-107">GetCachedInterfacePointers Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="a60ad-108">获取当前 RCW 上缓存的原始接口指针。</span><span class="sxs-lookup"><span data-stu-id="a60ad-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="a60ad-109">GetCachedInterfaceTypes 方法</span><span class="sxs-lookup"><span data-stu-id="a60ad-109">GetCachedInterfaceTypes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="a60ad-110">当前对象具有大小写转换为或用作接口类型提供的枚举器。</span><span class="sxs-lookup"><span data-stu-id="a60ad-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a60ad-111">备注</span><span class="sxs-lookup"><span data-stu-id="a60ad-111">Remarks</span></span>  
 <span data-ttu-id="a60ad-112">若要检查"ICorDebugValue"接口的实例是否表示一个 RCW，调试器将调用`QueryInterface`上与"ICorDebugValue" `IID_ICorDebugComObjectValue`。</span><span class="sxs-lookup"><span data-stu-id="a60ad-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a60ad-113">要求</span><span class="sxs-lookup"><span data-stu-id="a60ad-113">Requirements</span></span>  
 <span data-ttu-id="a60ad-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a60ad-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a60ad-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a60ad-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a60ad-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a60ad-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a60ad-117">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a60ad-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a60ad-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a60ad-118">See also</span></span>
- [<span data-ttu-id="a60ad-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="a60ad-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a60ad-120">调试</span><span class="sxs-lookup"><span data-stu-id="a60ad-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
