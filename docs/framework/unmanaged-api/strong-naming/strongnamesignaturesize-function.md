---
title: StrongNameSignatureSize 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: a19d875b8fb81f2af3821e69452f0f0ed591cd22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176885"
---
# <a name="strongnamesignaturesize-function"></a>StrongNameSignatureSize 函数
返回强名称签名的大小。 `StrongNameSignatureSize`编译器通常用于确定在创建延迟签名程序集时文件中保留的空间。  
  
 此函数已被弃用。 改用[ICLR 强名称：：强名称签名大小](../hosting/iclrstrongname-strongnamesignaturesize-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a>parameters  
 `pbPublicKeyBlob`  
 [在][公共密钥Blob](publickeyblob-structure.md)类型的结构，其中包含用于生成强名称签名的密钥对的公共部分。  
  
 `cbPublicKeyBlob`  
 [在]的大小（以字节为单位）的大小`pbPublicKeyBlob`。  
  
 `pcbSize`  
 [在]存储强名称签名所需的字节数。  
  
## <a name="return-value"></a>返回值  
 `true`成功完成;否则， `false`.  
  
## <a name="remarks"></a>备注  
 如果`StrongNameSignatureSize`函数未成功完成，请调用[StrongNameErrorInfo 函数](strongnameerrorinfo-function.md)以检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** 强名称.h  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [StrongNameSignatureSize 方法](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
