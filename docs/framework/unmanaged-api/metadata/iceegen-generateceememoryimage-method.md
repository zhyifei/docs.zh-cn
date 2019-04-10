---
title: ICeeGen::GenerateCeeMemoryImage 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GenerateCeeMemoryImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GenerateCeeMemoryImage
helpviewer_keywords:
- ICeeGen::GenerateCeeMemoryImage method [.NET Framework metadata]
- GenerateCeeMemoryImage method [.NET Framework metadata]
ms.assetid: b3847495-0ae6-4a72-b496-65ce2424afc6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8136ccc2306894f2a2cfc0203460cb62c0bbec73
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143086"
---
# <a name="iceegengenerateceememoryimage-method"></a>ICeeGen::GenerateCeeMemoryImage 方法
在基本代码的内存中生成的映像。  
  
 此方法已过时，不应使用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GenerateCeeMemoryImage (  
    [out] void    **ppImage  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppImage`  
 [out]指向所生成的图像的指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICeeGen 接口](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
