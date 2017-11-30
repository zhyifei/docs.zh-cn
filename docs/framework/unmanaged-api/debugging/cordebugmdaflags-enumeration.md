---
title: "CorDebugMDAFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugMDAFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugMDAFlags
helpviewer_keywords: CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 827825e4012b421caa4e05702a6f1a1b863ac69d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="0fc3c-102">CorDebugMDAFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="0fc3c-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="0fc3c-103">指定在其上激发托管调试助手 (MDA) 的线程的状态。</span><span class="sxs-lookup"><span data-stu-id="0fc3c-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fc3c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0fc3c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0fc3c-105">成员</span><span class="sxs-lookup"><span data-stu-id="0fc3c-105">Members</span></span>  
  
|<span data-ttu-id="0fc3c-106">成员</span><span class="sxs-lookup"><span data-stu-id="0fc3c-106">Member</span></span>|<span data-ttu-id="0fc3c-107">描述</span><span class="sxs-lookup"><span data-stu-id="0fc3c-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="0fc3c-108">在其激发 MDA 的线程已由于 MDA 已激发。</span><span class="sxs-lookup"><span data-stu-id="0fc3c-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fc3c-109">备注</span><span class="sxs-lookup"><span data-stu-id="0fc3c-109">Remarks</span></span>  
 <span data-ttu-id="0fc3c-110">当调用堆栈不再描述最初引发 MDA 的位置时，该线程被视为具有*跳过*。</span><span class="sxs-lookup"><span data-stu-id="0fc3c-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="0fc3c-111">这是一种特殊情况，由在退出时的无效操作的线程的执行。</span><span class="sxs-lookup"><span data-stu-id="0fc3c-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fc3c-112">要求</span><span class="sxs-lookup"><span data-stu-id="0fc3c-112">Requirements</span></span>  
 <span data-ttu-id="0fc3c-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0fc3c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fc3c-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fc3c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fc3c-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fc3c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fc3c-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fc3c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc3c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0fc3c-117">See Also</span></span>  
 [<span data-ttu-id="0fc3c-118">调试枚举</span><span class="sxs-lookup"><span data-stu-id="0fc3c-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
