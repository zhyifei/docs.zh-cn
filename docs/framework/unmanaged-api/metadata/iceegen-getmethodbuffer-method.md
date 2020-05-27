---
title: ICeeGen::GetMethodBuffer 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type:
- apiref
ms.openlocfilehash: 99eef11c294dbb17b30b2ef28e65999d4d60f817
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008309"
---
# <a name="iceegengetmethodbuffer-method"></a>ICeeGen::GetMethodBuffer 方法
获取指定的相对虚拟地址处的方法的适当大小的缓冲区。  
  
 此方法已过时，不应使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a>参数  
 `RVA`  
 中要为其返回缓冲区的方法的相对虚拟地址。  
  
 `lpBuffer`  
 弄指向返回的缓冲区的指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICeeGen 接口](iceegen-interface.md)
