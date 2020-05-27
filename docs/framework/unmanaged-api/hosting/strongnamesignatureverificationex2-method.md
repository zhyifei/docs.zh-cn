---
title: StrongNameSignatureVerificationEx2 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
ms.openlocfilehash: 5e6f77b9b5da061a75d23d7f3f7b673754b62afd
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006358"
---
# <a name="strongnamesignatureverificationex2-method"></a>StrongNameSignatureVerificationEx2 方法
验证强名称程序集的签名，并提供从 ECMA 密钥到实际密钥的映射。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>参数  
 `wszFilePath`  
 中要验证的程序集的可移植可执行文件（.exe 或 .dll）文件的路径。  
  
 `fForceVerification`  
 [in] `true`若要执行验证，即使需要重写注册表设置，否则为 `false` 。  
  
 `pbEcmaPublicKey`  
 中一个指针，指向用于验证的从 ECMA 公钥到实际密钥的映射。  
  
 `cbEcmaPublicKey`  
 中实际 ECMA 公钥的长度。  
  
 `pfWasVerified`  
 [out] `true`如果验证了强名称签名，则为;否则为 `false` 。 `false`如果验证因为注册表设置而成功，则也将此参数设置为。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果验证成功，则为;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [StrongNameSignatureVerification 方法](iclrstrongname-strongnamesignatureverification-method.md)
- [StrongNameSignatureVerificationEx 方法](iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName 接口](iclrstrongname-interface.md)
