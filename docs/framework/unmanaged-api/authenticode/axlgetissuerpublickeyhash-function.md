---
title: _AxlGetIssuerPublicKeyHash 函数
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b197aa539e60a9dbcee55cf190c44b45da3a5fb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402010"
---
# <a name="axlgetissuerpublickeyhash-function"></a>_AxlGetIssuerPublicKeyHash 函数
检索与用于对指定证书进行签名的私钥关联的公钥的 SHA-1 哈希。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pChainContext`  
 [in] CSP 公钥 Blob。 请参阅[CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx)结构。  
  
 `ppwszPublicKeyHash`  
 [out] 指向 WCHAR * 的指针，用于接收十六进制编码的公钥标记。  
  
## <a name="return-value"></a>返回值  
 如果函数成功，则为 `S_OK`；否则为 `S_FALSE`。  
  
## <a name="see-also"></a>请参阅  
 [验证码](../../../../docs/framework/unmanaged-api/authenticode/index.md)
