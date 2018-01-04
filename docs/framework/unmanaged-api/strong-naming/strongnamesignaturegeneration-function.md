---
title: "StrongNameSignatureGeneration 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureGeneration
helpviewer_keywords: StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c26e230f2bc0b115d898a34742fe3e637f934fd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignaturegeneration-function"></a>StrongNameSignatureGeneration 函数
为指定的程序集生成强名称签名。  
  
 此函数已弃用。 使用[iclrstrongname:: Strongnamesignaturegeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszFilePath`  
 [in]包含将为其生成强名称签名的程序集清单文件的路径。  
  
 `wszKeyContainer`  
 [in]包含公钥/私钥对的密钥容器的名称。  
  
 如果`pbKeyBlob`为 null，`wszKeyContainer`必须指定加密服务提供商 (CSP) 中有效的容器。 在这种情况下，存储在容器的密钥对用于对文件进行签名。  
  
 如果`pbKeyBlob`不为 null，则假定的密钥对要包含在密钥二进制大型对象 (BLOB)。  
  
 键必须为 1024年位 Rivest 仅使用 Adleman (RSA) 签名密钥。 这次不支持的密钥的任何其他类型。  
  
 `pbKeyBlob`  
 [in]指向公钥/私钥对的指针。 此对采用以下格式创建由 Win32`CryptExportKey`函数。 如果`pbKeyBlob`是 null，指定的密钥容器`wszKeyContainer`假定包含密钥对。  
  
 `cbKeyBlob`  
 [in]大小，以字节为单位的`pbKeyBlob`。  
  
 `ppbSignatureBlob`  
 [out]指向公共语言运行时向其返回签名的位置的指针。 如果`ppbSignatureBlob`是 null，运行时将签名存储在指定的文件中`wszFilePath`。  
  
 如果`ppbSignatureBlob`是不为 null，公共语言运行时分配的空间内进行返回签名。 调用方必须释放此空间使用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数。  
  
 `pcbSignatureBlob`  
 [out]以字节为单位，返回签名的大小。  
  
## <a name="return-value"></a>返回值  
 `true`在成功完成;否则为`false`。  
  
## <a name="remarks"></a>备注  
 指定为空`wszFilePath`来计算而无需创建签名的签名的大小。  
  
 签名可以是直接存储在该文件，或返回到调用方。  
  
 如果`StrongNameSignatureGeneration`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [StrongNameSignatureGeneration 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [StrongNameSignatureGenerationEx 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
