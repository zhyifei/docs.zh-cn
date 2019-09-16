---
title: StrongNameSignatureGeneration 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48cdd550e5d8c7c75a603d74456e99a066d5c599
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798975"
---
# <a name="strongnamesignaturegeneration-function"></a>StrongNameSignatureGeneration 函数
为指定的程序集生成强名称签名。  
  
 此函数已弃用。 改为使用[ICLRStrongName：： StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a>参数  
 `wszFilePath`  
 中包含要为其生成强名称签名的程序集清单的文件的路径。  
  
 `wszKeyContainer`  
 中包含公钥/私钥对的密钥容器的名称。  
  
 如果`pbKeyBlob`为 null， `wszKeyContainer`则必须在加密服务提供程序（CSP）中指定有效的容器。 在这种情况下，存储在容器中的密钥对用于对文件进行签名。  
  
 如果`pbKeyBlob`不为 null，则假定密钥对包含在关键的二进制大型对象（BLOB）中。  
  
 密钥必须是1024位 Rivest-Rivest-shamir-adleman-Rivest-shamir-adleman （RSA）签名密钥。 此时不支持其他类型的密钥。  
  
 `pbKeyBlob`  
 中指向公钥/私钥对的指针。 此对采用 Win32 `CryptExportKey`函数创建的格式。 如果`pbKeyBlob`为 null， `wszKeyContainer`则假定指定的密钥容器包含密钥对。  
  
 `cbKeyBlob`  
 中的`pbKeyBlob`大小（以字节为单位）。  
  
 `ppbSignatureBlob`  
 弄指向公共语言运行时返回签名的位置的指针。 如果`ppbSignatureBlob`为 null，则运行时将签名存储在`wszFilePath`指定的文件中。  
  
 如果`ppbSignatureBlob`不为 null，则公共语言运行时将分配要在其中返回签名的空间。 调用方必须使用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数释放此空间。  
  
 `pcbSignatureBlob`  
 弄返回签名的大小（以字节为单位）。  
  
## <a name="return-value"></a>返回值  
 `true`成功完成时;否则为`false`。  
  
## <a name="remarks"></a>备注  
 指定 null `wszFilePath`以计算签名大小，而不创建签名。  
  
 签名可以直接存储在文件中，也可以返回给调用方。  
  
 如果`StrongNameSignatureGeneration`函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameSignatureGeneration 方法](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [StrongNameSignatureGenerationEx 方法](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
