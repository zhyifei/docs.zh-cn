---
title: ICeeGen::GetIMapTokenIface 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIMapTokenIface
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIMapTokenIface
helpviewer_keywords:
- GetIMapTokenIface method [.NET Framework metadata]
- ICeeGen::GetIMapTokenIface method [.NET Framework metadata]
ms.assetid: 847a5531-c37d-49cd-8844-9e54b5d86cf7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b42c7ed5614f5f436559ce4af462ff16896a89c0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746152"
---
# <a name="iceegengetimaptokeniface-method"></a>ICeeGen::GetIMapTokenIface 方法
获取指定的标记所引用的接口。  
  
 此方法已过时，不应使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetIMapTokenIface (  
    [in, out] IUnknown   **pIMapToken  
);  
```  
  
## <a name="parameters"></a>参数  
 `pIMapToken`  
 [in、 out]要返回的接口的元数据标记。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICeeGen 接口](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
