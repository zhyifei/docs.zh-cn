---
title: CorUnmanagedCallingConvention 枚举
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: 58d30e71929d314ee36adb9f83270858ff8a161b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442447"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="1ccf7-102">CorUnmanagedCallingConvention 枚举</span><span class="sxs-lookup"><span data-stu-id="1ccf7-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="1ccf7-103">指定非托管代码的调用约定。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ccf7-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ccf7-104">Syntax</span></span>  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="1ccf7-105">Members</span><span class="sxs-lookup"><span data-stu-id="1ccf7-105">Members</span></span>  
  
|<span data-ttu-id="1ccf7-106">成员</span><span class="sxs-lookup"><span data-stu-id="1ccf7-106">Member</span></span>|<span data-ttu-id="1ccf7-107">说明</span><span class="sxs-lookup"><span data-stu-id="1ccf7-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="1ccf7-108">C 语言调用约定。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="1ccf7-109">标准调用约定。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="1ccf7-110">"This" 调用约定。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="1ccf7-111">"Fast" 调用约定。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="1ccf7-112">未使用。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="1ccf7-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="1ccf7-114">未使用。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="1ccf7-115">未使用。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ccf7-116">备注</span><span class="sxs-lookup"><span data-stu-id="1ccf7-116">Remarks</span></span>  
 <span data-ttu-id="1ccf7-117">CLR 不支持 .NET Framework 版本1.0 中的 "fast" 调用约定。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ccf7-118">要求</span><span class="sxs-lookup"><span data-stu-id="1ccf7-118">Requirements</span></span>  
 <span data-ttu-id="1ccf7-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ccf7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ccf7-120">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="1ccf7-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1ccf7-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ccf7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ccf7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ccf7-122">See also</span></span>

- [<span data-ttu-id="1ccf7-123">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="1ccf7-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
