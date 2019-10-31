---
title: StackOverflowInfo 结构
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 1072026f92edbc646653c6dd74ec8e22d5b887e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105909"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="fb814-102">StackOverflowInfo 结构</span><span class="sxs-lookup"><span data-stu-id="fb814-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="fb814-103">存储发生的溢出的类型以及因溢出而引发的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="fb814-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb814-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb814-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="fb814-105">Members</span><span class="sxs-lookup"><span data-stu-id="fb814-105">Members</span></span>  
  
|<span data-ttu-id="fb814-106">成员</span><span class="sxs-lookup"><span data-stu-id="fb814-106">Member</span></span>|<span data-ttu-id="fb814-107">描述</span><span class="sxs-lookup"><span data-stu-id="fb814-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="fb814-108">指定溢出类型的[StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md)枚举的值。</span><span class="sxs-lookup"><span data-stu-id="fb814-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="fb814-109">一个指向 Win32 `EXCEPTION_POINTERS` 对象的指针，该对象包含一个异常记录，其中包含与计算机无关的异常说明和一个上下文记录，并在发生异常时提供与计算机相关的处理器上下文说明。</span><span class="sxs-lookup"><span data-stu-id="fb814-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb814-110">备注</span><span class="sxs-lookup"><span data-stu-id="fb814-110">Remarks</span></span>  
 <span data-ttu-id="fb814-111">将 `StackOverflowInfo` 对象传递到 `Event_StackOverflow` 事件的[IActionOnCLREvent：： OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fb814-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb814-112">要求</span><span class="sxs-lookup"><span data-stu-id="fb814-112">Requirements</span></span>  
 <span data-ttu-id="fb814-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb814-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb814-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fb814-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="fb814-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="fb814-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb814-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb814-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb814-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb814-117">See also</span></span>

- [<span data-ttu-id="fb814-118">承载结构</span><span class="sxs-lookup"><span data-stu-id="fb814-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
