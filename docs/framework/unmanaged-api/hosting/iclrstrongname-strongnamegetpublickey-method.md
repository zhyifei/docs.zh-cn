---
title: ICLRStrongName::StrongNameGetPublicKey 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: cb96c7e17627205db0573e56fc8c2a29e7717434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181935"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>ICLRStrongName::StrongNameGetPublicKey 方法
从公钥/私钥对获取公钥。 密钥对可以作为加密服务提供商 （CSP） 中的密钥容器名称提供，也可以作为字节的原始集合提供。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>parameters  
 `szKeyContainer`  
 [在]包含公钥/私钥对的密钥容器的名称。 如果`pbKeyBlob`为 null，`szKeyContainer`则必须在 CSP 中指定有效的容器。 在这种情况下[，ICLRStrongNameName：：StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)方法从存储在容器中的密钥对中提取公钥。  
  
 如果`pbKeyBlob`不是空，则假定密钥对包含在密钥二进制大型对象 （BLOB） 中。  
  
 密钥必须是 1024 位里维斯-沙米尔-阿德尔曼 （RSA） 签名密钥。 目前不支持其他类型的密钥。  
  
 `pbKeyBlob`  
 [在]指向公钥/私钥对的指针。 此对采用 Win32`CryptExportKey`函数创建的格式。 如果`pbKeyBlob`为 null，则假定 指定的`szKeyContainer`键容器包含密钥对。  
  
 `cbKeyBlob`  
 [在]的大小（以字节为单位）的大小`pbKeyBlob`。  
  
 `ppbPublicKeyBlob`  
 [出]返回的公钥 BLOB。 参数`ppbPublicKeyBlob`由通用语言运行时分配并返回到调用方。 调用方必须使用[ICLRStrongNameName：：StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法释放内存。  
  
 `pcbPublicKeyBlob`  
 [出]返回的公钥 BLOB 的大小。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果方法成功完成;如果方法成功完成;否则，指示失败的 HRESULT 值（请参阅列表[的常用 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。  
  
## <a name="remarks"></a>备注  
 公钥包含在[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)结构中。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MetaHost.h  
  
 **库：** 作为资源包含在 MSCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [StrongNameTokenFromPublicKey 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [PublicKeyBlob Strong Naming](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
