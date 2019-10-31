---
title: BucketParameters 结构
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
ms.openlocfilehash: 80623bdec939b0ae5fc13008c1c4001c613ac435
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195963"
---
# <a name="bucketparameters-structure"></a>BucketParameters 结构
存储事件的类型名称和与事件关联的当前异常的参数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`fInited`|如果此结构的其余部分有效，则 `true`;否则，`false`。|  
|`pszEventTypeName`|事件类型的名称。|  
|`pszParams`|一个字符串数组，其中每个字符串都为与事件关联的当前异常指定一个参数。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载结构](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
