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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7de5a6d38d43c20ce52f609ef6514a1f28022416
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781140"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="41033-102">StackOverflowInfo 结构</span><span class="sxs-lookup"><span data-stu-id="41033-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="41033-103">由于发生溢出时引发的异常上存储的类型发生溢出和信息。</span><span class="sxs-lookup"><span data-stu-id="41033-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41033-104">语法</span><span class="sxs-lookup"><span data-stu-id="41033-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="41033-105">成员</span><span class="sxs-lookup"><span data-stu-id="41033-105">Members</span></span>  
  
|<span data-ttu-id="41033-106">成员</span><span class="sxs-lookup"><span data-stu-id="41033-106">Member</span></span>|<span data-ttu-id="41033-107">描述</span><span class="sxs-lookup"><span data-stu-id="41033-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="41033-108">值为[StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md)枚举，用于指定溢出的类型。</span><span class="sxs-lookup"><span data-stu-id="41033-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="41033-109">一个指向 Win32`EXCEPTION_POINTERS`对象，其中包含与计算机无关的描述异常的异常记录以及具有依赖于计算机的说明的处理器上下文时的异常的上下文记录。</span><span class="sxs-lookup"><span data-stu-id="41033-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41033-110">备注</span><span class="sxs-lookup"><span data-stu-id="41033-110">Remarks</span></span>  
 <span data-ttu-id="41033-111">一个`StackOverflowInfo`对象传递给[iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)方法`Event_StackOverflow`事件。</span><span class="sxs-lookup"><span data-stu-id="41033-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41033-112">要求</span><span class="sxs-lookup"><span data-stu-id="41033-112">Requirements</span></span>  
 <span data-ttu-id="41033-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="41033-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41033-114">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="41033-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="41033-115">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="41033-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41033-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41033-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41033-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="41033-117">See also</span></span>

- [<span data-ttu-id="41033-118">承载结构</span><span class="sxs-lookup"><span data-stu-id="41033-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
