---
title: “Cor调试调试事件类型”枚举
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
ms.openlocfilehash: de4ac1f39ea9cfb4b616bd4e2c85e5de530dbb0b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132221"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="36d8e-102">“Cor调试调试事件类型”枚举</span><span class="sxs-lookup"><span data-stu-id="36d8e-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="36d8e-103">指示[DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)方法对其信息进行解码的事件类型。</span><span class="sxs-lookup"><span data-stu-id="36d8e-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d8e-104">语法</span><span class="sxs-lookup"><span data-stu-id="36d8e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="36d8e-105">Members</span><span class="sxs-lookup"><span data-stu-id="36d8e-105">Members</span></span>  
  
|<span data-ttu-id="36d8e-106">成员</span><span class="sxs-lookup"><span data-stu-id="36d8e-106">Member</span></span>|<span data-ttu-id="36d8e-107">描述</span><span class="sxs-lookup"><span data-stu-id="36d8e-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="36d8e-108">模块加载事件。</span><span class="sxs-lookup"><span data-stu-id="36d8e-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="36d8e-109">模块卸载事件。</span><span class="sxs-lookup"><span data-stu-id="36d8e-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="36d8e-110">最可能的异常。</span><span class="sxs-lookup"><span data-stu-id="36d8e-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="36d8e-111">最可能的用户异常。</span><span class="sxs-lookup"><span data-stu-id="36d8e-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="36d8e-112">`catch` 处理程序存在的异常。</span><span class="sxs-lookup"><span data-stu-id="36d8e-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="36d8e-113">未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="36d8e-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36d8e-114">备注</span><span class="sxs-lookup"><span data-stu-id="36d8e-114">Remarks</span></span>  
 <span data-ttu-id="36d8e-115">通过调用[ICorDebugDebugEvent：： GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)方法返回 `CorDebugDebugEventKind` 枚举的成员。</span><span class="sxs-lookup"><span data-stu-id="36d8e-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36d8e-116">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="36d8e-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36d8e-117">要求</span><span class="sxs-lookup"><span data-stu-id="36d8e-117">Requirements</span></span>  
 <span data-ttu-id="36d8e-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36d8e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36d8e-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36d8e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36d8e-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36d8e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36d8e-121">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36d8e-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d8e-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="36d8e-122">See also</span></span>

- [<span data-ttu-id="36d8e-123">调试枚举</span><span class="sxs-lookup"><span data-stu-id="36d8e-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
