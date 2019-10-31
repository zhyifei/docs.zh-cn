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
ms.openlocfilehash: a8856790b655f071df704879a247169f456ae2f5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130878"
---
# <a name="strongnamesignaturesize-function"></a>StrongNameSignatureSize 函数
返回强名称签名的大小。 当创建延迟签名程序集时，编译器通常使用 `StrongNameSignatureSize` 来确定文件中要保留的空间量。  
  
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
 中`pbPublicKeyBlob`的大小（以字节为单位）。  
  
 `pcbSize`  
 中存储强名称签名所需的字节数。  
  
## <a name="return-value"></a>返回值  
 成功完成后 `true`;否则，`false`。  
  
## <a name="remarks"></a>备注  
 如果 `StrongNameSignatureSize` 函数未成功完成，请调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数以检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameSignatureSize 方法](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
