---
title: StrongNameTokenFromAssemblyEx 函数
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
ms.openlocfilehash: 8b7866b92be3195b0a767a823a0d7fb1c0aa4918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104250"
---
# <a name="strongnametokenfromassemblyex-function"></a>StrongNameTokenFromAssemblyEx 函数
从指定的程序集文件创建强名称令牌，并返回该令牌表示的公钥。  
  
 此函数已弃用。 改为使用[ICLRStrongName：： StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>参数  
 `wszFilePath`  
 中程序集的可移植可执行（PE）文件的路径。  
  
 `ppbStrongNameToken`  
 弄返回的强名称标记。  
  
 `pcbStrongNameToken`  
 弄强名称令牌的大小（以字节为单位）。  
  
 `ppbPublicKeyBlob`  
 弄返回的公钥。  
  
 `pcbPublicKeyBlob`  
 弄公钥的大小（以字节为单位）。  
  
## <a name="return-value"></a>返回值  
 成功完成后 `true`;否则，`false`。  
  
## <a name="remarks"></a>备注  
 强名称标记是公钥的缩写形式。 标记是从用于对程序集进行签名的公钥创建的64位哈希。 该令牌是程序集的强名称的一部分，并且可以从程序集元数据中读取。  
  
 检索到密钥并创建令牌后，应调用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数以释放已分配的内存。  
  
 如果 `StrongNameTokenFromAssemblyEx` 函数未成功完成，请调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数以检索上次生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **库：** 作为资源包括在 mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameTokenFromAssemblyEx 方法](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [StrongNameTokenFromAssembly 方法](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
