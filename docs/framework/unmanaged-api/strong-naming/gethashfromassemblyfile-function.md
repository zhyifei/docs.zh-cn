---
title: GetHashFromAssemblyFile 函数
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e9c0abcd395caf09ebe11e060a4b922e78ad1e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457927"
---
# <a name="gethashfromassemblyfile-function"></a>GetHashFromAssemblyFile 函数
获取使用指定的哈希算法对指定的程序集文件的哈希值。  
  
 此函数已弃用。 使用[iclrstrongname:: Gethashfromassemblyfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szFilePath`  
 [in]要进行哈希处理的文件路径。  
  
 `piHashAlg`  
 [在中，out]一个指定的哈希算法的常数。 使用默认哈希算法的零。  
  
 `pbHash`  
 [out]返回的哈希缓冲区中。  
  
 `cchHash`  
 [in]请求的最大大小的`pbHash`。  
  
 `pchHash`  
 [out]返回的大小，以字节为单位， `pbHash`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [GetHashFromAssemblyFile 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [GetHashFromAssemblyFileW 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
