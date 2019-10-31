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
ms.openlocfilehash: c7af194351290ad937e40a2fc8b960c2c242629c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132798"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="fa8a4-102">CorDebugMDAFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="fa8a4-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="fa8a4-103">指定在其上激发托管调试助手 (MDA) 的线程的状态。</span><span class="sxs-lookup"><span data-stu-id="fa8a4-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa8a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa8a4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="fa8a4-105">Members</span><span class="sxs-lookup"><span data-stu-id="fa8a4-105">Members</span></span>  
  
|<span data-ttu-id="fa8a4-106">成员</span><span class="sxs-lookup"><span data-stu-id="fa8a4-106">Member</span></span>|<span data-ttu-id="fa8a4-107">描述</span><span class="sxs-lookup"><span data-stu-id="fa8a4-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="fa8a4-108">触发 mda 后，触发 MDA 的线程发生了。</span><span class="sxs-lookup"><span data-stu-id="fa8a4-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa8a4-109">备注</span><span class="sxs-lookup"><span data-stu-id="fa8a4-109">Remarks</span></span>  
 <span data-ttu-id="fa8a4-110">当调用堆栈不再描述最初引发 MDA 的位置时，线程被视为已*落后*。</span><span class="sxs-lookup"><span data-stu-id="fa8a4-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="fa8a4-111">这是一个不寻常的情况，导致在退出时线程执行无效操作的情况。</span><span class="sxs-lookup"><span data-stu-id="fa8a4-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa8a4-112">要求</span><span class="sxs-lookup"><span data-stu-id="fa8a4-112">Requirements</span></span>  
 <span data-ttu-id="fa8a4-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa8a4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa8a4-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa8a4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa8a4-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa8a4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa8a4-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa8a4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa8a4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa8a4-117">See also</span></span>

- [<span data-ttu-id="fa8a4-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="fa8a4-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
