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
ms.openlocfilehash: cbc272070e9eb6810b34ec1f3fdc9e944c624cd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132385"
---
# <a name="cor_active_function-structure"></a><span data-ttu-id="24f6c-102">COR_ACTIVE_FUNCTION 结构</span><span class="sxs-lookup"><span data-stu-id="24f6c-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="24f6c-103">包含有关在线程框架中当前处于活动状态的函数的信息。</span><span class="sxs-lookup"><span data-stu-id="24f6c-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="24f6c-104">此结构由[ICorDebugThread2：： GetActiveFunctions](icordebugthread2-getactivefunctions-method.md)方法使用。</span><span class="sxs-lookup"><span data-stu-id="24f6c-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f6c-105">语法</span><span class="sxs-lookup"><span data-stu-id="24f6c-105">Syntax</span></span>  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="24f6c-106">Members</span><span class="sxs-lookup"><span data-stu-id="24f6c-106">Members</span></span>  
  
|<span data-ttu-id="24f6c-107">成员</span><span class="sxs-lookup"><span data-stu-id="24f6c-107">Member</span></span>|<span data-ttu-id="24f6c-108">描述</span><span class="sxs-lookup"><span data-stu-id="24f6c-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="24f6c-109">指向 `ilOffset` 字段的应用程序域所有者的指针。</span><span class="sxs-lookup"><span data-stu-id="24f6c-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="24f6c-110">指向 `ilOffset` 字段的模块所有者的指针。</span><span class="sxs-lookup"><span data-stu-id="24f6c-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="24f6c-111">指向 `ilOffset` 字段的函数所有者的指针。</span><span class="sxs-lookup"><span data-stu-id="24f6c-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="24f6c-112">帧的 Microsoft 中间语言（MSIL）偏移量。</span><span class="sxs-lookup"><span data-stu-id="24f6c-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="24f6c-113">保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="24f6c-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24f6c-114">要求</span><span class="sxs-lookup"><span data-stu-id="24f6c-114">Requirements</span></span>  
 <span data-ttu-id="24f6c-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24f6c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24f6c-116">**标头：** Cordebug.idl .idl</span><span class="sxs-lookup"><span data-stu-id="24f6c-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="24f6c-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24f6c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24f6c-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24f6c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f6c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="24f6c-119">See also</span></span>

- [<span data-ttu-id="24f6c-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="24f6c-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="24f6c-121">调试</span><span class="sxs-lookup"><span data-stu-id="24f6c-121">Debugging</span></span>](index.md)
