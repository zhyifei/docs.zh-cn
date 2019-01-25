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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9a1ee9ab1649a832b6daefc96049d68850f3bc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555552"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="7c669-102">CorUnmanagedCallingConvention 枚举</span><span class="sxs-lookup"><span data-stu-id="7c669-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="7c669-103">指定非托管代码的调用约定。</span><span class="sxs-lookup"><span data-stu-id="7c669-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c669-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c669-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="7c669-105">成员</span><span class="sxs-lookup"><span data-stu-id="7c669-105">Members</span></span>  
  
|<span data-ttu-id="7c669-106">成员</span><span class="sxs-lookup"><span data-stu-id="7c669-106">Member</span></span>|<span data-ttu-id="7c669-107">描述</span><span class="sxs-lookup"><span data-stu-id="7c669-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="7c669-108">C 语言的调用约定。</span><span class="sxs-lookup"><span data-stu-id="7c669-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="7c669-109">标准调用约定。</span><span class="sxs-lookup"><span data-stu-id="7c669-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="7c669-110">"This"调用约定。</span><span class="sxs-lookup"><span data-stu-id="7c669-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="7c669-111">"快速"的调用约定。</span><span class="sxs-lookup"><span data-stu-id="7c669-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="7c669-112">未使用。</span><span class="sxs-lookup"><span data-stu-id="7c669-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="7c669-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="7c669-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="7c669-114">未使用。</span><span class="sxs-lookup"><span data-stu-id="7c669-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="7c669-115">未使用。</span><span class="sxs-lookup"><span data-stu-id="7c669-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c669-116">备注</span><span class="sxs-lookup"><span data-stu-id="7c669-116">Remarks</span></span>  
 <span data-ttu-id="7c669-117">CLR 不支持在.NET Framework 1.0 版中的"快速"的调用约定。</span><span class="sxs-lookup"><span data-stu-id="7c669-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c669-118">要求</span><span class="sxs-lookup"><span data-stu-id="7c669-118">Requirements</span></span>  
 <span data-ttu-id="7c669-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c669-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c669-120">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7c669-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7c669-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c669-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c669-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c669-122">See also</span></span>
- [<span data-ttu-id="7c669-123">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="7c669-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
