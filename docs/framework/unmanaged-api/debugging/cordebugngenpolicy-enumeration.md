---
title: CorDebugNGenPolicy 枚举
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca922d8b582c0608073d4fd0ba986167ae470e34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599491"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="75346-102">CorDebugNGenPolicy 枚举</span><span class="sxs-lookup"><span data-stu-id="75346-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="75346-103">提供用于确定调试器是否从本机映像缓存中加载本机 (NGen) 映像的值。</span><span class="sxs-lookup"><span data-stu-id="75346-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75346-104">语法</span><span class="sxs-lookup"><span data-stu-id="75346-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="75346-105">成员</span><span class="sxs-lookup"><span data-stu-id="75346-105">Members</span></span>  
  
|<span data-ttu-id="75346-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="75346-106">Member name</span></span>|<span data-ttu-id="75346-107">描述</span><span class="sxs-lookup"><span data-stu-id="75346-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="75346-108">在[!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)]禁用应用程序中，使用本地本机映像缓存中的图像。</span><span class="sxs-lookup"><span data-stu-id="75346-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="75346-109">在桌面应用中，此设置不起。</span><span class="sxs-lookup"><span data-stu-id="75346-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75346-110">备注</span><span class="sxs-lookup"><span data-stu-id="75346-110">Remarks</span></span>  
 <span data-ttu-id="75346-111">`CorDebugNGENPolicy`枚举由[ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="75346-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="75346-112">禁用的本地本机映像缓存中的映像使用通过确保调试器加载可调试 JIT 编译的映像，而不是优化的本机映像提供了一致的调试体验。</span><span class="sxs-lookup"><span data-stu-id="75346-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75346-113">要求</span><span class="sxs-lookup"><span data-stu-id="75346-113">Requirements</span></span>  
 <span data-ttu-id="75346-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="75346-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75346-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75346-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75346-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75346-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75346-117">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75346-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75346-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="75346-118">See also</span></span>

- [<span data-ttu-id="75346-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="75346-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
