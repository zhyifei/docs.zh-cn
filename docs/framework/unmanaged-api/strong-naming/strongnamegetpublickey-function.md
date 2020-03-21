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
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176924"
---
# <a name="strongnamegetpublickey-function"></a>StrongNameGetPublicKey 函数
从私钥/公钥对中获取公钥。 密钥对可以作为加密服务提供商 （CSP） 中的密钥容器名称提供，也可以作为字节的原始集合提供。  
  
 此函数已被弃用。 改用[ICLR 强名称：：强名称GetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)方法。  
  
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
  
## <a name="parameters"></a>parameters  
 `szKeyContainer`  
 [在]包含公钥/私钥对的密钥容器的名称。 如果`pbKeyBlob`为 null，`szKeyContainer`则必须在 CSP 中指定有效的容器。 在这种情况下，`StrongNameGetPublicKey`从容器中存储的密钥对中提取公钥。  
  
 如果`pbKeyBlob`不是空，则假定密钥对包含在密钥二进制大型对象 （BLOB） 中。  
  
 密钥必须是 1024 位里维斯-沙米尔-阿德尔曼 （RSA） 签名密钥。 目前不支持其他类型的密钥。  
  
 `pbKeyBlob`  
 [在]指向公钥/私钥对的指针。 此对采用 Win32`CryptExportKey`函数创建的格式。 如果`pbKeyBlob`为 null，则假定 指定的`szKeyContainer`键容器包含密钥对。  
  
 `cbKeyBlob`  
 [在]的大小（以字节为单位）的大小`pbKeyBlob`。  
  
 `ppbPublicKeyBlob`  
 [出]返回的公钥 BLOB。 参数`ppbPublicKeyBlob`由通用语言运行时分配并返回到调用方。 调用方必须使用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数释放内存。  
  
 `pcbPublicKeyBlob`  
 [出]返回的公钥 BLOB 的大小。  
  
## <a name="return-value"></a>返回值  
 `true`成功完成;否则， `false`.  
  
## <a name="remarks"></a>备注  
 公钥包含在[PublicKeyBlob](publickeyblob-structure.md)结构中。  
  
 如果`StrongNameGetPublicKey`函数未成功完成，请调用[StrongNameErrorInfo 函数](strongnameerrorinfo-function.md)以检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** 强名称.h  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [StrongNameGetPublicKey 方法](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [StrongNameTokenFromPublicKey 方法](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
- [PublicKeyBlob Strong Naming](publickeyblob-structure.md)
