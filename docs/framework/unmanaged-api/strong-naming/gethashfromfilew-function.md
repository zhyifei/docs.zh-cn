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
ms.openlocfilehash: 9db583c7064cb910b29e84437f31143dac0d3ec9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175078"
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW 函数
生成由 Unicode 字符串指定的文件内容的哈希。  
  
 此函数已被弃用。 使用[ICLR 强名称：：获取哈希弗罗瓦](../hosting/iclrstrongname-gethashfromfilew-method.md)方法。  
  
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
  
## <a name="parameters"></a>parameters  
 `wszFilePath`  
 [在]要哈希的文件的 Unicode 名称。  
  
 `piHashAlg`  
 [进出]生成哈希时使用的算法。 有效的算法是由 Win32 加密 API 定义的算法。 如果`piHashAlg`设置为 0，则使用默认算法CALG_SHA-1。  
  
 `pbHash`  
 [出]包含生成的哈希的字节数组。  
  
 `cchHash`  
 [在]指向 的缓冲区的最大大小`pbHash`。  
  
 `pchHash`  
 [出]的大小（以字节为单位）的大小`pbHash`。  
  
## <a name="remarks"></a>备注  
 此函数与[GetHashFromFile](gethashfromfile-function.md)相同，只不过文件名规范是 Unicode 而不是 ANSI。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** 强名称.h  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [GetHashFromFileW 方法](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [GetHashFromFile 方法](../hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
