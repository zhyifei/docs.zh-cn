---
title: ICeeGen::GetString 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: e81ef33f4fb684cce29aa9afb756451b1e5db896
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426172"
---
# <a name="iceegengetstring-method"></a>ICeeGen::GetString 方法
获取存储在指定的相对虚拟地址的字符串。  
  
 此方法已过时，不应使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a>参数  
 `RVA`  
 中要返回的字符串的相对虚拟地址。  
  
 `lpString`  
 弄返回的字符串。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICeeGen 接口](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
