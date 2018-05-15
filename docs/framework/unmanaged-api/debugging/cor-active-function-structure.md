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
ms.openlocfilehash: 86ab3d3a0f460f1ecdf86147b14df205aaf49635
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="coractivefunction-structure"></a><span data-ttu-id="58bdd-102">COR_ACTIVE_FUNCTION 结构</span><span class="sxs-lookup"><span data-stu-id="58bdd-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="58bdd-103">包含有关在线程框架中当前处于活动状态的函数的信息。</span><span class="sxs-lookup"><span data-stu-id="58bdd-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="58bdd-104">此结构可由[icordebugthread2:: Getactivefunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="58bdd-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58bdd-105">语法</span><span class="sxs-lookup"><span data-stu-id="58bdd-105">Syntax</span></span>  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="58bdd-106">成员</span><span class="sxs-lookup"><span data-stu-id="58bdd-106">Members</span></span>  
  
|<span data-ttu-id="58bdd-107">成员</span><span class="sxs-lookup"><span data-stu-id="58bdd-107">Member</span></span>|<span data-ttu-id="58bdd-108">描述</span><span class="sxs-lookup"><span data-stu-id="58bdd-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="58bdd-109">向应用程序域所有者的指针`ilOffset`字段。</span><span class="sxs-lookup"><span data-stu-id="58bdd-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="58bdd-110">指向的模块所有者`ilOffset`字段。</span><span class="sxs-lookup"><span data-stu-id="58bdd-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="58bdd-111">指向函数的所有者`ilOffset`字段。</span><span class="sxs-lookup"><span data-stu-id="58bdd-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="58bdd-112">帧 Microsoft 中间语言 (MSIL) 偏移量。</span><span class="sxs-lookup"><span data-stu-id="58bdd-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="58bdd-113">留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="58bdd-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58bdd-114">要求</span><span class="sxs-lookup"><span data-stu-id="58bdd-114">Requirements</span></span>  
 <span data-ttu-id="58bdd-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58bdd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58bdd-116">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="58bdd-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="58bdd-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58bdd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58bdd-118">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58bdd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58bdd-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="58bdd-119">See Also</span></span>  
 [<span data-ttu-id="58bdd-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="58bdd-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="58bdd-121">调试</span><span class="sxs-lookup"><span data-stu-id="58bdd-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
