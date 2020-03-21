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
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176898"
---
# <a name="strongnamesignaturegeneration-function"></a>StrongNameSignatureGeneration 函数
为指定的程序集生成强名称签名。  
  
 此函数已被弃用。 改用[ICLR 强名称：：强名称签名生成](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)方法。  
  
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
  
## <a name="parameters"></a>parameters  
 `wszFilePath`  
 [在]包含将为其生成强名称签名的程序集清单的文件的路径。  
  
 `wszKeyContainer`  
 [在]包含公钥/私钥对的密钥容器的名称。  
  
 如果`pbKeyBlob`为 null，`wszKeyContainer`则必须在加密服务提供商 （CSP） 中指定有效的容器。 在这种情况下，存储在容器中的密钥对用于对文件进行签名。  
  
 如果`pbKeyBlob`不是空，则假定密钥对包含在密钥二进制大型对象 （BLOB） 中。  
  
 密钥必须是 1024 位里维斯-沙米尔-阿德尔曼 （RSA） 签名密钥。 目前不支持其他类型的密钥。  
  
 `pbKeyBlob`  
 [在]指向公钥/私钥对的指针。 此对采用 Win32`CryptExportKey`函数创建的格式。 如果`pbKeyBlob`为 null，则假定 指定的`wszKeyContainer`键容器包含密钥对。  
  
 `cbKeyBlob`  
 [在]的大小（以字节为单位）的大小`pbKeyBlob`。  
  
 `ppbSignatureBlob`  
 [出]指向公共语言运行时返回签名的位置的指针。 如果`ppbSignatureBlob`为 null，运行时将签名存储在 指定的`wszFilePath`文件中。  
  
 如果`ppbSignatureBlob`为 null，则通用语言运行时会分配用于返回签名的空间。 调用方必须使用[强名称自由缓冲区](strongnamefreebuffer-function.md)函数释放此空间。  
  
 `pcbSignatureBlob`  
 [出]返回的签名的大小（以字节为单位）。  
  
## <a name="return-value"></a>返回值  
 `true`成功完成;否则， `false`.  
  
## <a name="remarks"></a>备注  
 指定 null`wszFilePath`以计算签名的大小而不创建签名。  
  
 签名可以直接存储在文件中，也可以返回到调用方。  
  
 如果`StrongNameSignatureGeneration`函数未成功完成，请调用[StrongNameErrorInfo 函数](strongnameerrorinfo-function.md)以检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** 强名称.h  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [StrongNameSignatureGeneration 方法](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [StrongNameSignatureGenerationEx 方法](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
