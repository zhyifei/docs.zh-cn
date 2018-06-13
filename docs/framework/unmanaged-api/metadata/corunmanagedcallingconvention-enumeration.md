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
ms.openlocfilehash: 0b249d26335a66b55d0643f3e75bfd90554f731e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448864"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="64657-102">CorUnmanagedCallingConvention 枚举</span><span class="sxs-lookup"><span data-stu-id="64657-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="64657-103">指定非托管代码的调用约定。</span><span class="sxs-lookup"><span data-stu-id="64657-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64657-104">语法</span><span class="sxs-lookup"><span data-stu-id="64657-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="64657-105">成员</span><span class="sxs-lookup"><span data-stu-id="64657-105">Members</span></span>  
  
|<span data-ttu-id="64657-106">成员</span><span class="sxs-lookup"><span data-stu-id="64657-106">Member</span></span>|<span data-ttu-id="64657-107">描述</span><span class="sxs-lookup"><span data-stu-id="64657-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="64657-108">C 语言的调用约定。</span><span class="sxs-lookup"><span data-stu-id="64657-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="64657-109">标准调用约定。</span><span class="sxs-lookup"><span data-stu-id="64657-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="64657-110">"This"调用约定。</span><span class="sxs-lookup"><span data-stu-id="64657-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="64657-111">"快速"的调用约定。</span><span class="sxs-lookup"><span data-stu-id="64657-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="64657-112">未使用。</span><span class="sxs-lookup"><span data-stu-id="64657-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="64657-113">未使用。</span><span class="sxs-lookup"><span data-stu-id="64657-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="64657-114">未使用。</span><span class="sxs-lookup"><span data-stu-id="64657-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="64657-115">未使用。</span><span class="sxs-lookup"><span data-stu-id="64657-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64657-116">备注</span><span class="sxs-lookup"><span data-stu-id="64657-116">Remarks</span></span>  
 <span data-ttu-id="64657-117">CLR 不支持在.NET Framework 1.0 版中的"快速"的调用约定。</span><span class="sxs-lookup"><span data-stu-id="64657-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64657-118">要求</span><span class="sxs-lookup"><span data-stu-id="64657-118">Requirements</span></span>  
 <span data-ttu-id="64657-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64657-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64657-120">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="64657-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="64657-121">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64657-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64657-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="64657-122">See Also</span></span>  
 [<span data-ttu-id="64657-123">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="64657-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
