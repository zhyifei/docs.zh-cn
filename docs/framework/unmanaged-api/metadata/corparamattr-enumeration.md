---
title: CorParamAttr 枚举
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97f62b082db11a5f0bb930e33cb47acef76e7a04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092053"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="90b8c-102">CorParamAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="90b8c-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="90b8c-103">包含一些值，用于描述方法参数的元数据。</span><span class="sxs-lookup"><span data-stu-id="90b8c-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90b8c-104">语法</span><span class="sxs-lookup"><span data-stu-id="90b8c-104">Syntax</span></span>  
  
```  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="90b8c-105">成员</span><span class="sxs-lookup"><span data-stu-id="90b8c-105">Members</span></span>  
  
|<span data-ttu-id="90b8c-106">成员</span><span class="sxs-lookup"><span data-stu-id="90b8c-106">Member</span></span>|<span data-ttu-id="90b8c-107">描述</span><span class="sxs-lookup"><span data-stu-id="90b8c-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="90b8c-108">指定该参数传递到方法调用。</span><span class="sxs-lookup"><span data-stu-id="90b8c-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="90b8c-109">指定该参数将传递从方法返回。</span><span class="sxs-lookup"><span data-stu-id="90b8c-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="90b8c-110">指定参数为可选。</span><span class="sxs-lookup"><span data-stu-id="90b8c-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="90b8c-111">公共语言运行时，保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="90b8c-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="90b8c-112">指定参数具有默认值。</span><span class="sxs-lookup"><span data-stu-id="90b8c-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="90b8c-113">指定该参数具有封送处理信息。</span><span class="sxs-lookup"><span data-stu-id="90b8c-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="90b8c-114">未使用。</span><span class="sxs-lookup"><span data-stu-id="90b8c-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90b8c-115">要求</span><span class="sxs-lookup"><span data-stu-id="90b8c-115">Requirements</span></span>  
 <span data-ttu-id="90b8c-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90b8c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90b8c-117">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="90b8c-117">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="90b8c-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="90b8c-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="90b8c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="90b8c-119">See also</span></span>

- [<span data-ttu-id="90b8c-120">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="90b8c-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
