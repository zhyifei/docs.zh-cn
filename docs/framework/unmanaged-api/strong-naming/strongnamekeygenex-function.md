---
title: StrongNameKeyGenEx 函数
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
ms.openlocfilehash: 63ddd90f3a8090853d10f03052915d10e1503ea6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125219"
---
# <a name="strongnamekeygenex-function"></a>StrongNameKeyGenEx 函数
使用指定的密钥大小生成新的公钥/私钥对，以便使用强名称。  
  
 此函数已弃用。 改为使用[ICLRStrongName：： StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>参数  
 `wszKeyContainer`  
 中请求的密钥容器名称。 `wszKeyContainer` 必须为非空字符串，或者为 null 以生成临时名称。  
  
 `dwFlags`  
 中指定是否保留注册的密钥。 支持以下值：  
  
- 0x00000000-在 `wszKeyContainer` 为 null 时使用，以生成临时密钥容器名称。  
  
- 0x00000001 （`SN_LEAVE_KEY`）-指定密钥应为 "已注册"。  
  
 `dwKeySize`  
 中请求的密钥大小，以位为单位。  
  
 `ppbKeyBlob`  
 弄返回的公钥/私钥对。  
  
 `pcbKeyBlob`  
 弄`ppbKeyBlob`的大小（以字节为单位）。  
  
## <a name="return-value"></a>返回值  
 成功完成后 `true`;否则，`false`。  
  
## <a name="remarks"></a>备注  
 .NET Framework 版本1.0 和1.1 需要 `dwKeySize` 1024 位才能使用强名称为程序集签名;版本2.0 添加了对2048位密钥的支持。  
  
 检索到密钥后，应调用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数以释放已分配的内存。  
  
 如果 `StrongNameKeyGenEx` 函数未成功完成，请调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数以检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameKeyGenEx 方法](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [StrongNameKeyGen 方法](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
