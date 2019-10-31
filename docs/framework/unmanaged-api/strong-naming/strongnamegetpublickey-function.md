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
ms.openlocfilehash: 966a2a628f30f1999688da7b6ba435c1d6cb830c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094664"
---
# <a name="strongnamegetpublickey-function"></a>StrongNameGetPublicKey 函数
从私钥/公钥对中获取公钥。 密钥对可以作为加密服务提供程序（CSP）中的密钥容器名称提供，也可以作为字节的原始集合提供。  
  
 此函数已弃用。 改为使用[ICLRStrongName：： StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>参数  
 `szKeyContainer`  
 中包含公钥/私钥对的密钥容器的名称。 如果 `pbKeyBlob` 为 null，则 `szKeyContainer` 必须在 CSP 中指定有效容器。 在这种情况下，`StrongNameGetPublicKey` 从存储在容器中的密钥对中提取公钥。  
  
 如果 `pbKeyBlob` 不为 null，则假定密钥对包含在关键的二进制大型对象（BLOB）中。  
  
 密钥必须是1024位 Rivest-Rivest-shamir-adleman-Rivest-shamir-adleman （RSA）签名密钥。 此时不支持其他类型的密钥。  
  
 `pbKeyBlob`  
 中指向公钥/私钥对的指针。 此对采用 Win32 `CryptExportKey` 函数创建的格式。 如果 `pbKeyBlob` 为 null，则假定 `szKeyContainer` 指定的密钥容器包含密钥对。  
  
 `cbKeyBlob`  
 中`pbKeyBlob`的大小（以字节为单位）。  
  
 `ppbPublicKeyBlob`  
 弄返回的公钥 BLOB。 `ppbPublicKeyBlob` 参数由公共语言运行时分配并返回给调用方。 调用方必须使用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数释放内存。  
  
 `pcbPublicKeyBlob`  
 弄返回的公钥 BLOB 的大小。  
  
## <a name="return-value"></a>返回值  
 成功完成后 `true`;否则，`false`。  
  
## <a name="remarks"></a>备注  
 公钥包含在[PublicKeyBlob](publickeyblob-structure.md)结构中。  
  
 如果 `StrongNameGetPublicKey` 函数未成功完成，请调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数以检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameGetPublicKey 方法](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [StrongNameTokenFromPublicKey 方法](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
- [PublicKeyBlob Strong Naming](publickeyblob-structure.md)
