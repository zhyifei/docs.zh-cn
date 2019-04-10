---
title: CorCallingConvention 枚举
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44a4b5903cec2249eb1e176381fe3d8e600dd5e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145868"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="7aed1-102">CorCallingConvention 枚举</span><span class="sxs-lookup"><span data-stu-id="7aed1-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="7aed1-103">包含一些值，用于描述托管代码中执行的调用约定类型。</span><span class="sxs-lookup"><span data-stu-id="7aed1-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aed1-104">语法</span><span class="sxs-lookup"><span data-stu-id="7aed1-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="7aed1-105">成员</span><span class="sxs-lookup"><span data-stu-id="7aed1-105">Members</span></span>  
  
|<span data-ttu-id="7aed1-106">成员</span><span class="sxs-lookup"><span data-stu-id="7aed1-106">Member</span></span>|<span data-ttu-id="7aed1-107">描述</span><span class="sxs-lookup"><span data-stu-id="7aed1-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="7aed1-108">指示默认调用约定。</span><span class="sxs-lookup"><span data-stu-id="7aed1-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="7aed1-109">指示该方法采用可变数目的参数。</span><span class="sxs-lookup"><span data-stu-id="7aed1-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="7aed1-110">指示在调用到一个字段。</span><span class="sxs-lookup"><span data-stu-id="7aed1-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="7aed1-111">指示调用是对本地方法。</span><span class="sxs-lookup"><span data-stu-id="7aed1-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="7aed1-112">指示调用是对一个属性。</span><span class="sxs-lookup"><span data-stu-id="7aed1-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="7aed1-113">指示在调用非托管。</span><span class="sxs-lookup"><span data-stu-id="7aed1-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="7aed1-114">指示泛型方法实例化。</span><span class="sxs-lookup"><span data-stu-id="7aed1-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="7aed1-115">指示 64 位 PInvoke 调用采用可变数量的参数的方法。</span><span class="sxs-lookup"><span data-stu-id="7aed1-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="7aed1-116">介绍 4 位值无效。</span><span class="sxs-lookup"><span data-stu-id="7aed1-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="7aed1-117">指示底部四位所描述的调用约定。</span><span class="sxs-lookup"><span data-stu-id="7aed1-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="7aed1-118">指示高位描述`this`参数。</span><span class="sxs-lookup"><span data-stu-id="7aed1-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="7aed1-119">指示`this`参数是在签名中明确描述。</span><span class="sxs-lookup"><span data-stu-id="7aed1-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="7aed1-120">指示具有明确的数字的类型参数的泛型方法签名。</span><span class="sxs-lookup"><span data-stu-id="7aed1-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="7aed1-121">这在之前发生的普通参数计数。</span><span class="sxs-lookup"><span data-stu-id="7aed1-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7aed1-122">要求</span><span class="sxs-lookup"><span data-stu-id="7aed1-122">Requirements</span></span>  
 <span data-ttu-id="7aed1-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7aed1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aed1-124">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7aed1-124">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="7aed1-125">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="7aed1-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7aed1-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7aed1-126">See also</span></span>

- [<span data-ttu-id="7aed1-127">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="7aed1-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
