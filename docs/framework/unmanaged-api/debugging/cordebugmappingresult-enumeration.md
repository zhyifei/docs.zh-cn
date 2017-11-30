---
title: "CorDebugMappingResult 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugMappingResult
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugMappingResult
helpviewer_keywords: CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 793158ef63a0de27786dc8bd9b306f10c228054e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="b7d05-102">CorDebugMappingResult 枚举</span><span class="sxs-lookup"><span data-stu-id="b7d05-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="b7d05-103">提供如何获取指令指针 (IP) 的值的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b7d05-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d05-104">语法</span><span class="sxs-lookup"><span data-stu-id="b7d05-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b7d05-105">成员</span><span class="sxs-lookup"><span data-stu-id="b7d05-105">Members</span></span>  
  
|<span data-ttu-id="b7d05-106">成员</span><span class="sxs-lookup"><span data-stu-id="b7d05-106">Member</span></span>|<span data-ttu-id="b7d05-107">描述</span><span class="sxs-lookup"><span data-stu-id="b7d05-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="b7d05-108">本机代码是在序言中，因此 IP 的值为 0。</span><span class="sxs-lookup"><span data-stu-id="b7d05-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="b7d05-109">本机代码处于 epilog，所以 IP 的值是该方法的最后一个指令的地址。</span><span class="sxs-lookup"><span data-stu-id="b7d05-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="b7d05-110">没有映射信息是可用的方法，因此 IP 的值为 0。</span><span class="sxs-lookup"><span data-stu-id="b7d05-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="b7d05-111">尽管没有映射信息的方法，但当前的地址不能映射到 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="b7d05-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="b7d05-112">IP 的值为 0。</span><span class="sxs-lookup"><span data-stu-id="b7d05-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="b7d05-113">该方法准确地映射到 MSIL 代码，或者已解释了帧，因此 IP 的值为精确值。</span><span class="sxs-lookup"><span data-stu-id="b7d05-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="b7d05-114">已成功映射方法，但 IP 的值可能为近似值。</span><span class="sxs-lookup"><span data-stu-id="b7d05-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d05-115">备注</span><span class="sxs-lookup"><span data-stu-id="b7d05-115">Remarks</span></span>  
 <span data-ttu-id="b7d05-116">你可以使用[icordebugilframe:: Getip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)方法来获取指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="b7d05-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7d05-117">要求</span><span class="sxs-lookup"><span data-stu-id="b7d05-117">Requirements</span></span>  
 <span data-ttu-id="b7d05-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7d05-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d05-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7d05-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7d05-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7d05-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7d05-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7d05-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d05-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7d05-122">See Also</span></span>  
 [<span data-ttu-id="b7d05-123">调试枚举</span><span class="sxs-lookup"><span data-stu-id="b7d05-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
