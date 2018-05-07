---
title: StrongNameGetPublicKey 函数
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3ace4a3103231f776d4e2b034f8e18ce861ee97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="strongnamegetpublickey-function"></a>StrongNameGetPublicKey 函数
获取从私钥/公钥对的公钥。 可以提供的密钥对，为加密服务提供商 (CSP) 中的密钥容器名称或原始字节的集合。  
  
 此函数已弃用。 使用[iclrstrongname:: Strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szKeyContainer`  
 [in]包含公钥/私钥对的密钥容器的名称。 如果`pbKeyBlob`为 null，`szKeyContainer`必须指定一个有效的容器的 CSP 中。 在这种情况下，`StrongNameGetPublicKey`从容器中存储的密钥对中提取公钥。  
  
 如果`pbKeyBlob`不为 null，则假定的密钥对要包含在密钥二进制大型对象 (BLOB)。  
  
 键必须为 1024年位 Rivest 仅使用 Adleman (RSA) 签名密钥。 这次不支持的密钥的任何其他类型。  
  
 `pbKeyBlob`  
 [in]指向公钥/私钥对的指针。 此对采用以下格式创建由 Win32`CryptExportKey`函数。 如果`pbKeyBlob`是 null，指定的密钥容器`szKeyContainer`假定包含密钥对。  
  
 `cbKeyBlob`  
 [in]大小，以字节为单位的`pbKeyBlob`。  
  
 `ppbPublicKeyBlob`  
 [out]返回的公钥 BLOB。 `ppbPublicKeyBlob`参数是由公共语言运行时分配的和返回到调用方。 调用方必须释放的内存使用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数。  
  
 `pcbPublicKeyBlob`  
 [out]返回的公共密钥 BLOB 的大小。  
  
## <a name="return-value"></a>返回值  
 `true` 在成功完成;否则为`false`。  
  
## <a name="remarks"></a>备注  
 中包含的公钥[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)结构。  
  
 如果`StrongNameGetPublicKey`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameGetPublicKey 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [StrongNameTokenFromPublicKey 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [PublicKeyBlob Strong Naming](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
