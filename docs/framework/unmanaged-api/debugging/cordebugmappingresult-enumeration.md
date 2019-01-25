---
title: CorDebugMappingResult 枚举
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16c4e03667d4af3ab5cc8b653d77f15eaef25843
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691822"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="29c25-102">CorDebugMappingResult 枚举</span><span class="sxs-lookup"><span data-stu-id="29c25-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="29c25-103">提供如何获取指令指针 (IP) 的值的详细信息。</span><span class="sxs-lookup"><span data-stu-id="29c25-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c25-104">语法</span><span class="sxs-lookup"><span data-stu-id="29c25-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="29c25-105">成员</span><span class="sxs-lookup"><span data-stu-id="29c25-105">Members</span></span>  
  
|<span data-ttu-id="29c25-106">成员</span><span class="sxs-lookup"><span data-stu-id="29c25-106">Member</span></span>|<span data-ttu-id="29c25-107">描述</span><span class="sxs-lookup"><span data-stu-id="29c25-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="29c25-108">本机代码是在序言中，因此 IP 的值为 0。</span><span class="sxs-lookup"><span data-stu-id="29c25-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="29c25-109">本机代码是在 epilog 中，因此 IP 的值是该方法的最后一个指令的地址。</span><span class="sxs-lookup"><span data-stu-id="29c25-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="29c25-110">没有映射信息，则对于方法，因此 IP 的值为 0。</span><span class="sxs-lookup"><span data-stu-id="29c25-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="29c25-111">尽管没有映射信息的方法，但当前的地址不能映射到 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="29c25-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="29c25-112">IP 的值为 0。</span><span class="sxs-lookup"><span data-stu-id="29c25-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="29c25-113">该方法准确地映射到 MSIL 代码，或者已解释了框架，因此 IP 的值为精确值。</span><span class="sxs-lookup"><span data-stu-id="29c25-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="29c25-114">已成功映射方法，但 IP 的值可能为近似值。</span><span class="sxs-lookup"><span data-stu-id="29c25-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29c25-115">备注</span><span class="sxs-lookup"><span data-stu-id="29c25-115">Remarks</span></span>  
 <span data-ttu-id="29c25-116">可以使用[icordebugilframe:: Getip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)方法来获取指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="29c25-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29c25-117">要求</span><span class="sxs-lookup"><span data-stu-id="29c25-117">Requirements</span></span>  
 <span data-ttu-id="29c25-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="29c25-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c25-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29c25-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29c25-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29c25-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29c25-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29c25-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c25-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="29c25-122">See also</span></span>
- [<span data-ttu-id="29c25-123">调试枚举</span><span class="sxs-lookup"><span data-stu-id="29c25-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
