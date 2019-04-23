---
title: ICorDebugDebugEvent::GetEventKind 方法
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62eede48eea01563dbc3e170720694a24343d0a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150522"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="fcd91-102">ICorDebugDebugEvent::GetEventKind 方法</span><span class="sxs-lookup"><span data-stu-id="fcd91-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="fcd91-103">指出该 `ICorDebugDebugEvent` 对象代表的事件类型。</span><span class="sxs-lookup"><span data-stu-id="fcd91-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd91-104">语法</span><span class="sxs-lookup"><span data-stu-id="fcd91-104">Syntax</span></span>  
  
```  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcd91-105">参数</span><span class="sxs-lookup"><span data-stu-id="fcd91-105">Parameters</span></span>  
 <span data-ttu-id="fcd91-106">p调试事件类型</span><span class="sxs-lookup"><span data-stu-id="fcd91-106">pDebugEventKind</span></span>  
 <span data-ttu-id="fcd91-107">一个指向[CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)枚举成员，用于指示事件的类型。</span><span class="sxs-lookup"><span data-stu-id="fcd91-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcd91-108">备注</span><span class="sxs-lookup"><span data-stu-id="fcd91-108">Remarks</span></span>  
 <span data-ttu-id="fcd91-109">基于 `pDebugEventKind` 值，可调用 `QueryInterface` 以获取包含其他数据的精确度更高的调试事件接口。</span><span class="sxs-lookup"><span data-stu-id="fcd91-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcd91-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="fcd91-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcd91-111">要求</span><span class="sxs-lookup"><span data-stu-id="fcd91-111">Requirements</span></span>  
 <span data-ttu-id="fcd91-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fcd91-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd91-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcd91-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcd91-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcd91-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcd91-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd91-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd91-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fcd91-116">See also</span></span>

- [<span data-ttu-id="fcd91-117">ICorDebugDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="fcd91-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="fcd91-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="fcd91-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
