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
ms.openlocfilehash: ed5b39ed4b2a14c071bf23fb04efbad6834e8a9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783976"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="a9ec9-102">ICorDebugComObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="a9ec9-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="a9ec9-103">提供用于检索与运行时可调用包装（RCW）关联的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="a9ec9-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9ec9-104">方法</span><span class="sxs-lookup"><span data-stu-id="a9ec9-104">Methods</span></span>  
  
|<span data-ttu-id="a9ec9-105">方法</span><span class="sxs-lookup"><span data-stu-id="a9ec9-105">Method</span></span>|<span data-ttu-id="a9ec9-106">描述</span><span class="sxs-lookup"><span data-stu-id="a9ec9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9ec9-107">GetCachedInterfacePointers 方法</span><span class="sxs-lookup"><span data-stu-id="a9ec9-107">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="a9ec9-108">获取缓存在当前 RCW 上的原始接口指针。</span><span class="sxs-lookup"><span data-stu-id="a9ec9-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="a9ec9-109">GetCachedInterfaceTypes 方法</span><span class="sxs-lookup"><span data-stu-id="a9ec9-109">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="a9ec9-110">为当前对象的大小写或用作的接口类型提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="a9ec9-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9ec9-111">备注</span><span class="sxs-lookup"><span data-stu-id="a9ec9-111">Remarks</span></span>  
 <span data-ttu-id="a9ec9-112">若要检查 "ICorDebugValue" 接口的实例是否表示 RCW，调试程序会使用 `IID_ICorDebugComObjectValue`调用 "ICorDebugValue" 上的 `QueryInterface`。</span><span class="sxs-lookup"><span data-stu-id="a9ec9-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9ec9-113">需求</span><span class="sxs-lookup"><span data-stu-id="a9ec9-113">Requirements</span></span>  
 <span data-ttu-id="a9ec9-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9ec9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9ec9-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9ec9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9ec9-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9ec9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9ec9-117">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9ec9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ec9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9ec9-118">See also</span></span>

- [<span data-ttu-id="a9ec9-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="a9ec9-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a9ec9-120">调试</span><span class="sxs-lookup"><span data-stu-id="a9ec9-120">Debugging</span></span>](index.md)
