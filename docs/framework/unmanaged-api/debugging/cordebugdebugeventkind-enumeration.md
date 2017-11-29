---
title: "“Cor调试调试事件类型”枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugDebugEventKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5aeb6085671e645e12713944d6456b9581a3886f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="ba415-102">“Cor调试调试事件类型”枚举</span><span class="sxs-lookup"><span data-stu-id="ba415-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="ba415-103">指示由解码获取其信息的事件类型[解码事件](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ba415-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba415-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba415-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ba415-105">成员</span><span class="sxs-lookup"><span data-stu-id="ba415-105">Members</span></span>  
  
|<span data-ttu-id="ba415-106">成员</span><span class="sxs-lookup"><span data-stu-id="ba415-106">Member</span></span>|<span data-ttu-id="ba415-107">描述</span><span class="sxs-lookup"><span data-stu-id="ba415-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="ba415-108">模块加载事件。</span><span class="sxs-lookup"><span data-stu-id="ba415-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="ba415-109">模块卸载事件。</span><span class="sxs-lookup"><span data-stu-id="ba415-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="ba415-110">最可能的异常。</span><span class="sxs-lookup"><span data-stu-id="ba415-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="ba415-111">最可能的用户异常。</span><span class="sxs-lookup"><span data-stu-id="ba415-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="ba415-112">`catch` 处理程序存在的异常。</span><span class="sxs-lookup"><span data-stu-id="ba415-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="ba415-113">未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="ba415-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba415-114">备注</span><span class="sxs-lookup"><span data-stu-id="ba415-114">Remarks</span></span>  
 <span data-ttu-id="ba415-115">成员`CorDebugDebugEventKind`枚举返回通过调用[icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ba415-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba415-116">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="ba415-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba415-117">要求</span><span class="sxs-lookup"><span data-stu-id="ba415-117">Requirements</span></span>  
 <span data-ttu-id="ba415-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba415-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba415-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba415-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba415-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba415-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba415-121">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba415-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba415-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba415-122">See Also</span></span>  
 [<span data-ttu-id="ba415-123">调试枚举</span><span class="sxs-lookup"><span data-stu-id="ba415-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
