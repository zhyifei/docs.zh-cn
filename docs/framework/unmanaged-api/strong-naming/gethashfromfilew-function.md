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
ms.openlocfilehash: 00ee1139b4b8340a73740117b74208a6a1f6b639
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461586"
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW 函数
生成指定的 Unicode 字符串的文件的内容哈希代码。  
  
 此函数已弃用。 使用[iclrstrongname:: Gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a>参数  
 `wszFilePath`  
 [in]Unicode 哈希的文件的名称。  
  
 `piHashAlg`  
 [在中，out]要生成哈希时使用的算法。 有效算法是定义的 Win32 CryptoAPI。 如果`piHashAlg`设置为 0，则使用 CALG_SHA 1 的默认算法。  
  
 `pbHash`  
 [out]包含生成的哈希的字节数组。  
  
 `cchHash`  
 [in]指向缓冲区的最大大小`pbHash`。  
  
 `pchHash`  
 [out]大小，以字节为单位的`pbHash`。  
  
## <a name="remarks"></a>备注  
 此函数是与相同[GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)，只指定文件名称是 Unicode 而不是 ANSI。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [GetHashFromFileW 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [GetHashFromFile 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
