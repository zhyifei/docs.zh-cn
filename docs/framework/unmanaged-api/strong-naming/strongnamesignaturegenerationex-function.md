---
title: "StrongNameSignatureGenerationEx 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureGenerationEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureGenerationEx
helpviewer_keywords: StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49000a00f278b4c1dd7a2eeded7eb91a592c863f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignaturegenerationex-function"></a>StrongNameSignatureGenerationEx 函数
为指定的程序集中，根据指定的标志生成的强名称签名。  
  
 此函数已弃用。 使用[iclrstrongname:: Strongnamesignaturegenerationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
#### <a name="parameters"></a>参数  
 `wszFilePath`  
 [in]包含将为其生成强名称签名的程序集清单文件的路径。  
  
 `wszKeyContainer`  
 [in]包含公钥/私钥对的密钥容器的名称。  
  
 如果`pbKeyBlob`为 null，`wszKeyContainer`必须指定加密服务提供商 (CSP) 中有效的容器。 在这种情况下，存储在容器的密钥对用于对文件进行签名。  
  
 如果`pbKeyBlob`不为 null，则假定的密钥对要包含在密钥二进制大型对象 (BLOB)。  
  
 `pbKeyBlob`  
 [in]指向公钥/私钥对的指针。 此对采用以下格式创建由 Win32`CryptExportKey`函数。 如果`pbKeyBlob`是 null，指定的密钥容器`wszKeyContainer`假定包含密钥对。  
  
 `cbKeyBlob`  
 [in]大小，以字节为单位的`pbKeyBlob`。  
  
 `ppbSignatureBlob`  
 [out]指向公共语言运行时向其返回签名的位置的指针。 如果`ppbSignatureBlob`是 null，运行时将签名存储在指定的文件中`wszFilePath`。  
  
 如果`ppbSignatureBlob`是不为 null，公共语言运行时分配的空间内进行返回签名。 调用方必须释放此空间使用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数。  
  
 `pcbSignatureBlob`  
 [out]以字节为单位，返回签名的大小。  
  
 `dwFlags`  
 [in]一个或多个以下值：  
  
-   `SN_SIGN_ALL_FILES`(0x00000001)-重新计算所有链接的模块的哈希值。  
  
-   `SN_TEST_SIGN`(0x00000002) — 程序集进行测试签名。  
  
## <a name="return-value"></a>返回值  
 `true`在成功完成;否则为`false`。  
  
## <a name="remarks"></a>备注  
 指定为空`wszFilePath`来计算而无需创建签名的签名的大小。  
  
 可以直接在文件中，存储或返回到调用方的签名。  
  
 如果`SN_SIGN_ALL_FILES`指定但不包含的公共密钥 (同时`pbKeyBlob`和`wszFilePath`都为 null 时)，重新计算链接的模块的哈希值，但该程序集未重新签名。  
  
 如果`SN_TEST_SIGN`指定，则不会修改公共语言运行时标头以指示程序集使用强名称签名。  
  
 如果`StrongNameSignatureGenerationEx`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [StrongNameSignatureGenerationEx 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [StrongNameSignatureGeneration 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
