---
title: "CorCallingConvention 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCallingConvention
helpviewer_keywords: CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c0fbbb5f2c8f73cb6c76137263fa457840cdddc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="aa7df-102">CorCallingConvention 枚举</span><span class="sxs-lookup"><span data-stu-id="aa7df-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="aa7df-103">包含一些值，用于描述托管代码中执行的调用约定类型。</span><span class="sxs-lookup"><span data-stu-id="aa7df-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa7df-104">语法</span><span class="sxs-lookup"><span data-stu-id="aa7df-104">Syntax</span></span>  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="aa7df-105">成员</span><span class="sxs-lookup"><span data-stu-id="aa7df-105">Members</span></span>  
  
|<span data-ttu-id="aa7df-106">成员</span><span class="sxs-lookup"><span data-stu-id="aa7df-106">Member</span></span>|<span data-ttu-id="aa7df-107">描述</span><span class="sxs-lookup"><span data-stu-id="aa7df-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="aa7df-108">指示默认调用约定。</span><span class="sxs-lookup"><span data-stu-id="aa7df-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="aa7df-109">指示该方法采用可变数目的参数。</span><span class="sxs-lookup"><span data-stu-id="aa7df-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="aa7df-110">指示调用是对字段。</span><span class="sxs-lookup"><span data-stu-id="aa7df-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="aa7df-111">指示调用是对局部方法。</span><span class="sxs-lookup"><span data-stu-id="aa7df-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="aa7df-112">指示调用是对属性。</span><span class="sxs-lookup"><span data-stu-id="aa7df-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="aa7df-113">指示调用不受管理。</span><span class="sxs-lookup"><span data-stu-id="aa7df-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="aa7df-114">指示泛型方法实例化。</span><span class="sxs-lookup"><span data-stu-id="aa7df-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="aa7df-115">指示 64 位 PInvoke 调用采用可变数目的参数的方法。</span><span class="sxs-lookup"><span data-stu-id="aa7df-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="aa7df-116">描述 4 位值无效。</span><span class="sxs-lookup"><span data-stu-id="aa7df-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="aa7df-117">指示底部四位所描述的调用约定。</span><span class="sxs-lookup"><span data-stu-id="aa7df-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="aa7df-118">指示高位描述`this`参数。</span><span class="sxs-lookup"><span data-stu-id="aa7df-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="aa7df-119">指示`this`参数描述是明确的签名中。</span><span class="sxs-lookup"><span data-stu-id="aa7df-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="aa7df-120">指示与显式数目的类型参数的泛型方法签名。</span><span class="sxs-lookup"><span data-stu-id="aa7df-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="aa7df-121">这位于之前的普通参数计数。</span><span class="sxs-lookup"><span data-stu-id="aa7df-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa7df-122">要求</span><span class="sxs-lookup"><span data-stu-id="aa7df-122">Requirements</span></span>  
 <span data-ttu-id="aa7df-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aa7df-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa7df-124">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="aa7df-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="aa7df-125">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa7df-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa7df-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa7df-126">See Also</span></span>  
 [<span data-ttu-id="aa7df-127">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="aa7df-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
