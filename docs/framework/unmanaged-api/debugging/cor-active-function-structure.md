---
title: COR_ACTIVE_FUNCTION 结构
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5adf43bd68db449e465ffe3517c9eb9d41a5c18a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502047"
---
# <a name="coractivefunction-structure"></a><span data-ttu-id="55ed0-102">COR_ACTIVE_FUNCTION 结构</span><span class="sxs-lookup"><span data-stu-id="55ed0-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="55ed0-103">包含有关在线程框架中当前处于活动状态的函数的信息。</span><span class="sxs-lookup"><span data-stu-id="55ed0-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="55ed0-104">此结构可供[ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="55ed0-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ed0-105">语法</span><span class="sxs-lookup"><span data-stu-id="55ed0-105">Syntax</span></span>  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="55ed0-106">成员</span><span class="sxs-lookup"><span data-stu-id="55ed0-106">Members</span></span>  
  
|<span data-ttu-id="55ed0-107">成员</span><span class="sxs-lookup"><span data-stu-id="55ed0-107">Member</span></span>|<span data-ttu-id="55ed0-108">描述</span><span class="sxs-lookup"><span data-stu-id="55ed0-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="55ed0-109">指向的应用程序域所有者`ilOffset`字段。</span><span class="sxs-lookup"><span data-stu-id="55ed0-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="55ed0-110">指针的模块所有者`ilOffset`字段。</span><span class="sxs-lookup"><span data-stu-id="55ed0-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="55ed0-111">指向函数的所有者`ilOffset`字段。</span><span class="sxs-lookup"><span data-stu-id="55ed0-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="55ed0-112">框架的 Microsoft 中间语言 (MSIL) 偏移量。</span><span class="sxs-lookup"><span data-stu-id="55ed0-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="55ed0-113">保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="55ed0-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55ed0-114">要求</span><span class="sxs-lookup"><span data-stu-id="55ed0-114">Requirements</span></span>  
 <span data-ttu-id="55ed0-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55ed0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55ed0-116">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="55ed0-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="55ed0-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55ed0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55ed0-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55ed0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ed0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="55ed0-119">See also</span></span>
- [<span data-ttu-id="55ed0-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="55ed0-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="55ed0-121">调试</span><span class="sxs-lookup"><span data-stu-id="55ed0-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
