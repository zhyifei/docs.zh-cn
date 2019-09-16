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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f98b971e430a2c35a4c484f4f9c4bf387c640c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798953"
---
# <a name="strongnamesignaturesize-function"></a>StrongNameSignatureSize 函数
返回强名称签名的大小。 `StrongNameSignatureSize`通常由编译器用来确定在创建延迟签名程序集时要在文件中保留多少空间。  
  
 此函数已弃用。 改为使用[ICLRStrongName：： StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a>参数  
 `pbPublicKeyBlob`  
 中[PublicKeyBlob](publickeyblob-structure.md)类型的结构，它包含用于生成强名称签名的密钥对的公共部分。  
  
 `cbPublicKeyBlob`  
 中的`pbPublicKeyBlob`大小（以字节为单位）。  
  
 `pcbSize`  
 中存储强名称签名所需的字节数。  
  
## <a name="return-value"></a>返回值  
 `true`成功完成时;否则为`false`。  
  
## <a name="remarks"></a>备注  
 如果`StrongNameSignatureSize`函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameSignatureSize 方法](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
