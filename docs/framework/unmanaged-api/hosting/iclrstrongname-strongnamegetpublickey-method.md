---
title: "ICLRStrongName::StrongNameGetPublicKey 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9a639644405ce215a373dadf248e9a0e1a5558ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>ICLRStrongName::StrongNameGetPublicKey 方法
获取从公钥/私钥对的公钥。 可以提供的密钥对，为加密服务提供商 (CSP) 中的密钥容器名称或原始字节的集合。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szKeyContainer`  
 [in]包含公钥/私钥对的密钥容器的名称。 如果`pbKeyBlob`为 null，`szKeyContainer`必须指定一个有效的容器的 CSP 中。 在这种情况下， [iclrstrongname:: Strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)方法从容器中存储的密钥对中提取公钥。  
  
 如果`pbKeyBlob`不为 null，则假定的密钥对要包含在密钥二进制大型对象 (BLOB)。  
  
 键必须为 1024年位 Rivest 仅使用 Adleman (RSA) 签名密钥。 这次不支持的密钥的任何其他类型。  
  
 `pbKeyBlob`  
 [in]指向公钥/私钥对的指针。 此对采用以下格式创建由 Win32`CryptExportKey`函数。 如果`pbKeyBlob`是 null，指定的密钥容器`szKeyContainer`假定包含密钥对。  
  
 `cbKeyBlob`  
 [in]大小，以字节为单位的`pbKeyBlob`。  
  
 `ppbPublicKeyBlob`  
 [out]返回的公钥 BLOB。 `ppbPublicKeyBlob`参数是由公共语言运行时分配的和返回到调用方。 调用方必须释放的内存使用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法。  
  
 `pcbPublicKeyBlob`  
 [out]返回的公共密钥 BLOB 的大小。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。  
  
## <a name="remarks"></a>备注  
 中包含的公钥[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)结构。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameTokenFromPublicKey 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [PublicKeyBlob Strong Naming](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
