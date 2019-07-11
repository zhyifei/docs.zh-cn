---
title: CorDebugMDAFlags 枚举
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf9f7f3d3419efc9e1dc7d75fc7272432c0cf5d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739689"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="b15a8-102">CorDebugMDAFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="b15a8-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="b15a8-103">指定在其上激发托管调试助手 (MDA) 的线程的状态。</span><span class="sxs-lookup"><span data-stu-id="b15a8-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b15a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="b15a8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b15a8-105">成员</span><span class="sxs-lookup"><span data-stu-id="b15a8-105">Members</span></span>  
  
|<span data-ttu-id="b15a8-106">成员</span><span class="sxs-lookup"><span data-stu-id="b15a8-106">Member</span></span>|<span data-ttu-id="b15a8-107">描述</span><span class="sxs-lookup"><span data-stu-id="b15a8-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="b15a8-108">在其触发 MDA 的线程将落后由于 MDA 时触发。</span><span class="sxs-lookup"><span data-stu-id="b15a8-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b15a8-109">备注</span><span class="sxs-lookup"><span data-stu-id="b15a8-109">Remarks</span></span>  
 <span data-ttu-id="b15a8-110">该线程时调用堆栈不再介绍最初引发 MDA 的位置，将被视为已*跳过*。</span><span class="sxs-lookup"><span data-stu-id="b15a8-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="b15a8-111">这是一种特殊情况由线程的执行无效操作在退出时。</span><span class="sxs-lookup"><span data-stu-id="b15a8-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b15a8-112">要求</span><span class="sxs-lookup"><span data-stu-id="b15a8-112">Requirements</span></span>  
 <span data-ttu-id="b15a8-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b15a8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b15a8-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b15a8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b15a8-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b15a8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b15a8-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b15a8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b15a8-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b15a8-117">See also</span></span>

- [<span data-ttu-id="b15a8-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="b15a8-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
