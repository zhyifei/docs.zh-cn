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
ms.openlocfilehash: b4c521489f38360d45c2cf8ff3780e057299f0b4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008945"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="f25d5-102">CorUnmanagedCallingConvention 枚举</span><span class="sxs-lookup"><span data-stu-id="f25d5-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="f25d5-103">指定非托管代码的调用约定。</span><span class="sxs-lookup"><span data-stu-id="f25d5-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f25d5-104">语法</span><span class="sxs-lookup"><span data-stu-id="f25d5-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f25d5-105">成员</span><span class="sxs-lookup"><span data-stu-id="f25d5-105">Members</span></span>  
  
|<span data-ttu-id="f25d5-106">成员</span><span class="sxs-lookup"><span data-stu-id="f25d5-106">Member</span></span>|<span data-ttu-id="f25d5-107">描述</span><span class="sxs-lookup"><span data-stu-id="f25d5-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="f25d5-108">C 语言调用约定。</span><span class="sxs-lookup"><span data-stu-id="f25d5-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="f25d5-109">标准调用约定。</span><span class="sxs-lookup"><span data-stu-id="f25d5-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="f25d5-110">"This" 调用约定。</span><span class="sxs-lookup"><span data-stu-id="f25d5-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="f25d5-111">"Fast" 调用约定。</span><span class="sxs-lookup"><span data-stu-id="f25d5-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="f25d5-112">未使用。</span><span class="sxs-lookup"><span data-stu-id="f25d5-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="f25d5-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="f25d5-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="f25d5-114">未使用。</span><span class="sxs-lookup"><span data-stu-id="f25d5-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="f25d5-115">未使用。</span><span class="sxs-lookup"><span data-stu-id="f25d5-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f25d5-116">备注</span><span class="sxs-lookup"><span data-stu-id="f25d5-116">Remarks</span></span>  
 <span data-ttu-id="f25d5-117">CLR 不支持 .NET Framework 版本1.0 中的 "fast" 调用约定。</span><span class="sxs-lookup"><span data-stu-id="f25d5-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f25d5-118">要求</span><span class="sxs-lookup"><span data-stu-id="f25d5-118">Requirements</span></span>  
 <span data-ttu-id="f25d5-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f25d5-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f25d5-120">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="f25d5-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f25d5-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f25d5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f25d5-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f25d5-122">See also</span></span>

- [<span data-ttu-id="f25d5-123">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="f25d5-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
