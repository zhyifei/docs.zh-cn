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
ms.openlocfilehash: 468ad1acf55c4d1b4fc2b53730f16ee8630cf19b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444010"
---
# <a name="corcallingconvention-enumeration"></a>CorCallingConvention 枚举
包含一些值，用于描述托管代码中执行的调用约定类型。  
  
## <a name="syntax"></a>语法  
  
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
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|指示默认调用约定。|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|指示该方法采用可变数目的参数。|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|指示调用是对字段。|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|指示调用是对局部方法。|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|指示调用是对属性。|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|指示调用不受管理。|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|指示泛型方法实例化。|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|指示 64 位 PInvoke 调用采用可变数目的参数的方法。|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|描述 4 位值无效。|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|指示底部四位所描述的调用约定。|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|指示高位描述`this`参数。|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|指示`this`参数描述是明确的签名中。|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|指示与显式数目的类型参数的泛型方法签名。 这位于之前的普通参数计数。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
