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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e5479fad3f19c219a0ca1d5d01934ce92a7162e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127156"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="a47f9-102">“Cor调试调试事件类型”枚举</span><span class="sxs-lookup"><span data-stu-id="a47f9-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="a47f9-103">指示获取其信息进行解码的事件的类型[解码事件](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a47f9-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a47f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="a47f9-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="a47f9-105">成员</span><span class="sxs-lookup"><span data-stu-id="a47f9-105">Members</span></span>  
  
|<span data-ttu-id="a47f9-106">成员</span><span class="sxs-lookup"><span data-stu-id="a47f9-106">Member</span></span>|<span data-ttu-id="a47f9-107">描述</span><span class="sxs-lookup"><span data-stu-id="a47f9-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="a47f9-108">模块加载事件。</span><span class="sxs-lookup"><span data-stu-id="a47f9-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="a47f9-109">模块卸载事件。</span><span class="sxs-lookup"><span data-stu-id="a47f9-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="a47f9-110">最可能的异常。</span><span class="sxs-lookup"><span data-stu-id="a47f9-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="a47f9-111">最可能的用户异常。</span><span class="sxs-lookup"><span data-stu-id="a47f9-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="a47f9-112">`catch` 处理程序存在的异常。</span><span class="sxs-lookup"><span data-stu-id="a47f9-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="a47f9-113">未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="a47f9-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a47f9-114">备注</span><span class="sxs-lookup"><span data-stu-id="a47f9-114">Remarks</span></span>  
 <span data-ttu-id="a47f9-115">成员`CorDebugDebugEventKind`枚举返回通过调用[icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a47f9-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a47f9-116">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="a47f9-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a47f9-117">要求</span><span class="sxs-lookup"><span data-stu-id="a47f9-117">Requirements</span></span>  
 <span data-ttu-id="a47f9-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a47f9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a47f9-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a47f9-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a47f9-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a47f9-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a47f9-121">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a47f9-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47f9-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a47f9-122">See also</span></span>

- [<span data-ttu-id="a47f9-123">调试枚举</span><span class="sxs-lookup"><span data-stu-id="a47f9-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
