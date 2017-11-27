---
title: "_AxlGetIssuerPublicKeyHash 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlGetIssuerPublicKeyHash
api_location: clr.dll
api_type: DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38be1f621425797e27fc41cb3192a628ebbfdb0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
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
  
## <a name="see-also"></a>另请参阅  
 [验证码](../../../../docs/framework/unmanaged-api/authenticode/index.md)
