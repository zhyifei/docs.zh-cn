---
title: StrongNameSignatureGenerationEx 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
ms.openlocfilehash: e8f63a6379af8f2b7b88c511840622d49d65d587
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141573"
---
# <a name="strongnamesignaturegenerationex-function"></a>StrongNameSignatureGenerationEx 函数
根据指定的标志，为指定的程序集生成强名称签名。  
  
 此函数已弃用。 改为使用[ICLRStrongName：： StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `wszFilePath`  
 中包含要为其生成强名称签名的程序集清单的文件的路径。  
  
 `wszKeyContainer`  
 中包含公钥/私钥对的密钥容器的名称。  
  
 如果 `pbKeyBlob` 为 null，则 `wszKeyContainer` 必须在加密服务提供程序（CSP）中指定有效的容器。 在这种情况下，存储在容器中的密钥对用于对文件进行签名。  
  
 如果 `pbKeyBlob` 不为 null，则假定密钥对包含在关键的二进制大型对象（BLOB）中。  
  
 `pbKeyBlob`  
 中指向公钥/私钥对的指针。 此对采用 Win32 `CryptExportKey` 函数创建的格式。 如果 `pbKeyBlob` 为 null，则假定 `wszKeyContainer` 指定的密钥容器包含密钥对。  
  
 `cbKeyBlob`  
 中`pbKeyBlob`的大小（以字节为单位）。  
  
 `ppbSignatureBlob`  
 弄指向公共语言运行时返回签名的位置的指针。 如果 `ppbSignatureBlob` 为 null，则运行时将签名存储在 `wszFilePath`指定的文件中。  
  
 如果 `ppbSignatureBlob` 不为 null，则公共语言运行时将分配要在其中返回签名的空间。 调用方必须使用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数释放此空间。  
  
 `pcbSignatureBlob`  
 弄返回签名的大小（以字节为单位）。  
  
 `dwFlags`  
 中以下一个或多个值：  
  
- `SN_SIGN_ALL_FILES` （0x00000001）-重新计算链接模块的所有哈希。  
  
- `SN_TEST_SIGN` （0x00000002）-对程序集进行测试签名。  
  
## <a name="return-value"></a>返回值  
 成功完成后 `true`;否则，`false`。  
  
## <a name="remarks"></a>备注  
 为 `wszFilePath` 指定 null，以计算签名大小而不创建签名。  
  
 签名可以直接存储在文件中，也可以返回给调用方。  
  
 如果指定了 `SN_SIGN_ALL_FILES` 但未包括公钥（`pbKeyBlob` 和 `wszFilePath` 均为 null），则会重新计算链接模块的哈希值，但不会对程序集进行重新签名。  
  
 如果指定 `SN_TEST_SIGN`，则不会修改公共语言运行时标头以指示程序集使用强名称进行签名。  
  
 如果 `StrongNameSignatureGenerationEx` 函数未成功完成，请调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数以检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameSignatureGenerationEx 方法](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [StrongNameSignatureGeneration 方法](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
