---
title: GetHashFromFileW 函数
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd96b5acb22f63b6e06c981119186680d6593a79
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799197"
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW 函数
生成由 Unicode 字符串指定的文件内容的哈希。  
  
 此函数已弃用。 改为使用[ICLRStrongName：： GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a>参数  
 `wszFilePath`  
 中要进行哈希处理的文件的 Unicode 名称。  
  
 `piHashAlg`  
 [in，out]生成哈希时要使用的算法。 有效算法是由 Win32 CryptoAPI 定义的算法。 如果`piHashAlg`设置为0，则使用默认算法 CALG_SHA-1。  
  
 `pbHash`  
 弄一个字节数组，其中包含生成的哈希。  
  
 `cchHash`  
 中所指向`pbHash`的缓冲区的最大大小。  
  
 `pchHash`  
 弄的`pbHash`大小（以字节为单位）。  
  
## <a name="remarks"></a>备注  
 此函数与[GetHashFromFile](gethashfromfile-function.md)相同，不同之处在于文件名规范是 Unicode 而不是 ANSI。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [GetHashFromFileW 方法](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [GetHashFromFile 方法](../hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
