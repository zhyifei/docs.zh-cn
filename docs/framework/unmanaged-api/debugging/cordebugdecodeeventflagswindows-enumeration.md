---
title: “Cor调试解码事件标志窗口”枚举
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d4e006a03db5b16de93dfd07ec7b964db4bfc1d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207729"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="c8723-102">“Cor调试解码事件标志窗口”枚举</span><span class="sxs-lookup"><span data-stu-id="c8723-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="c8723-103">提供关于 Windows 平台上的调试事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="c8723-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8723-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8723-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="c8723-105">成员</span><span class="sxs-lookup"><span data-stu-id="c8723-105">Members</span></span>  
  
|<span data-ttu-id="c8723-106">成员</span><span class="sxs-lookup"><span data-stu-id="c8723-106">Member</span></span>|<span data-ttu-id="c8723-107">描述</span><span class="sxs-lookup"><span data-stu-id="c8723-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="c8723-108">指出调试事件为最可能的异常。</span><span class="sxs-lookup"><span data-stu-id="c8723-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8723-109">备注</span><span class="sxs-lookup"><span data-stu-id="c8723-109">Remarks</span></span>  
 <span data-ttu-id="c8723-110">[ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)方法包括`dwFlags`参数提供调试事件相关的其他信息，并且其值取决于目标体系结构。</span><span class="sxs-lookup"><span data-stu-id="c8723-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="c8723-111">`CorDebugDecodeEventFlagsWindows` 枚举可与 Windows 平台上的调试事件一起使用。</span><span class="sxs-lookup"><span data-stu-id="c8723-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8723-112">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="c8723-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8723-113">要求</span><span class="sxs-lookup"><span data-stu-id="c8723-113">Requirements</span></span>  
 <span data-ttu-id="c8723-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8723-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8723-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8723-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8723-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8723-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c8723-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="c8723-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c8723-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8723-118">See also</span></span>

- [<span data-ttu-id="c8723-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="c8723-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
