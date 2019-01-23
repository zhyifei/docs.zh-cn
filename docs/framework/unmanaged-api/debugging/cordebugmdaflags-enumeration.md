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
ms.openlocfilehash: b7f20dec86a85be85472037f58a2bd2002d9be1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620381"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="915b9-102">CorDebugMDAFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="915b9-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="915b9-103">指定在其上激发托管调试助手 (MDA) 的线程的状态。</span><span class="sxs-lookup"><span data-stu-id="915b9-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="915b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="915b9-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="915b9-105">成员</span><span class="sxs-lookup"><span data-stu-id="915b9-105">Members</span></span>  
  
|<span data-ttu-id="915b9-106">成员</span><span class="sxs-lookup"><span data-stu-id="915b9-106">Member</span></span>|<span data-ttu-id="915b9-107">描述</span><span class="sxs-lookup"><span data-stu-id="915b9-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="915b9-108">在其触发 MDA 的线程将落后由于 MDA 时触发。</span><span class="sxs-lookup"><span data-stu-id="915b9-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="915b9-109">备注</span><span class="sxs-lookup"><span data-stu-id="915b9-109">Remarks</span></span>  
 <span data-ttu-id="915b9-110">该线程时调用堆栈不再介绍最初引发 MDA 的位置，将被视为已*跳过*。</span><span class="sxs-lookup"><span data-stu-id="915b9-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="915b9-111">这是一种特殊情况由线程的执行无效操作在退出时。</span><span class="sxs-lookup"><span data-stu-id="915b9-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="915b9-112">要求</span><span class="sxs-lookup"><span data-stu-id="915b9-112">Requirements</span></span>  
 <span data-ttu-id="915b9-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="915b9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="915b9-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="915b9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="915b9-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="915b9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="915b9-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="915b9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="915b9-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="915b9-117">See also</span></span>
- [<span data-ttu-id="915b9-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="915b9-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
