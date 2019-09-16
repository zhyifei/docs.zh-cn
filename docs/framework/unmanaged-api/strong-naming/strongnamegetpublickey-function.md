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
ms.openlocfilehash: ae87ebd0b8225f14ca029fac80528d47f5a866cf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799057"
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
 中包含公钥/私钥对的密钥容器的名称。 如果`pbKeyBlob`为 null， `szKeyContainer`则必须在 CSP 内指定有效容器。 在这种情况`StrongNameGetPublicKey`下，从存储在容器中的密钥对中提取公钥。  
  
 如果`pbKeyBlob`不为 null，则假定密钥对包含在关键的二进制大型对象（BLOB）中。  
  
 密钥必须是1024位 Rivest-Rivest-shamir-adleman-Rivest-shamir-adleman （RSA）签名密钥。 此时不支持其他类型的密钥。  
  
 `pbKeyBlob`  
 中指向公钥/私钥对的指针。 此对采用 Win32 `CryptExportKey`函数创建的格式。 如果`pbKeyBlob`为 null， `szKeyContainer`则假定指定的密钥容器包含密钥对。  
  
 `cbKeyBlob`  
 中的`pbKeyBlob`大小（以字节为单位）。  
  
 `ppbPublicKeyBlob`  
 弄返回的公钥 BLOB。 `ppbPublicKeyBlob`参数由公共语言运行时分配并返回给调用方。 调用方必须使用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数释放内存。  
  
 `pcbPublicKeyBlob`  
 弄返回的公钥 BLOB 的大小。  
  
## <a name="return-value"></a>返回值  
 `true`成功完成时;否则为`false`。  
  
## <a name="remarks"></a>备注  
 公钥包含在[PublicKeyBlob](publickeyblob-structure.md)结构中。  
  
 如果`StrongNameGetPublicKey`函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameGetPublicKey 方法](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [StrongNameTokenFromPublicKey 方法](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
- [PublicKeyBlob Strong Naming](publickeyblob-structure.md)
