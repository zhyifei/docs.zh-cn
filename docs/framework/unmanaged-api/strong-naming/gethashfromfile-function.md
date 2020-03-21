---
title: GetHashFromFile 函数
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176976"
---
# <a name="gethashfromfile-function"></a>GetHashFromFile 函数
生成指定文件内容的哈希。  
  
 此函数已被弃用。 改用[ICLR 强名称：：获取哈希文件](../hosting/iclrstrongname-gethashfromfile-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>parameters  
 `szFilePath`  
 [在]要哈希的文件的名称。  
  
 `piHashAlg`  
 [进出]生成哈希时使用的算法。 有效的算法是由 Win32 加密 API 定义的算法。 如果`piHashAlg`设置为 0，则使用默认算法CALG_SHA-1。  
  
 `pbHash`  
 [出]包含生成的哈希的字节数组。  
  
 `cchHash`  
 [在]`pbHash`指向的缓冲区的最大大小。  
  
 `pchHash`  
 [出]返回`pbHash`的大小（以字节为单位）。  
  
## <a name="remarks"></a>备注  
 此函数与[GetHashFromFileW](gethashfromfilew-function.md)相同，只不过文件名规范是 ANSI 而不是 Unicode。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** 强名称.h  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [GetHashFromFile 方法](../hosting/iclrstrongname-gethashfromfile-method.md)
- [GetHashFromFileW 方法](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
