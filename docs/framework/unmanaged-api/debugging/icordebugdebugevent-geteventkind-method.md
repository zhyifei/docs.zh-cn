---
title: ICorDebugDebugEvent::GetEventKind 方法
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62eede48eea01563dbc3e170720694a24343d0a5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150522"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="a4c97-102">ICorDebugDebugEvent::GetEventKind 方法</span><span class="sxs-lookup"><span data-stu-id="a4c97-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="a4c97-103">指出该 `ICorDebugDebugEvent` 对象代表的事件类型。</span><span class="sxs-lookup"><span data-stu-id="a4c97-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4c97-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4c97-104">Syntax</span></span>  
  
```  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4c97-105">参数</span><span class="sxs-lookup"><span data-stu-id="a4c97-105">Parameters</span></span>  
 <span data-ttu-id="a4c97-106">p调试事件类型</span><span class="sxs-lookup"><span data-stu-id="a4c97-106">pDebugEventKind</span></span>  
 <span data-ttu-id="a4c97-107">一个指向[CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)枚举成员，用于指示事件的类型。</span><span class="sxs-lookup"><span data-stu-id="a4c97-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4c97-108">备注</span><span class="sxs-lookup"><span data-stu-id="a4c97-108">Remarks</span></span>  
 <span data-ttu-id="a4c97-109">基于 `pDebugEventKind` 值，可调用 `QueryInterface` 以获取包含其他数据的精确度更高的调试事件接口。</span><span class="sxs-lookup"><span data-stu-id="a4c97-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4c97-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a4c97-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4c97-111">要求</span><span class="sxs-lookup"><span data-stu-id="a4c97-111">Requirements</span></span>  
 <span data-ttu-id="a4c97-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4c97-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4c97-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4c97-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4c97-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4c97-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a4c97-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a4c97-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4c97-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4c97-116">See also</span></span>

- [<span data-ttu-id="a4c97-117">“ICor调试调试事件”接口</span><span class="sxs-lookup"><span data-stu-id="a4c97-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="a4c97-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="a4c97-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
