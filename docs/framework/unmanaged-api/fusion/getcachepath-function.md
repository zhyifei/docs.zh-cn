---
title: GetCachePath 函数
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1c28f32a4b24393483241bd2d7d6f550b8b65ba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796903"
---
# <a name="getcachepath-function"></a>GetCachePath 函数
使用指定的标志获取缓存的程序集的路径。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>参数  
 `dwCacheFlags`  
 中指示缓存的程序集的源的[ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md)值。  
  
 `pwzCachePath`  
 弄指向路径的返回指针。  
  
 `pcchPath`  
 [in，out]请求的最大长度`pwzCachePath`，返回时为的实际`pwzCachePath`长度。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ASM_CACHE_FLAGS 枚举](asm-cache-flags-enumeration.md)
- [合成全局静态函数](fusion-global-static-functions.md)
