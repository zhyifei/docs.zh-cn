---
title: "ICLRStrongName::GetHashFromFileW 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eec58e0cf062e405c757a506e9c26955009b710b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromfilew-method"></a>ICLRStrongName::GetHashFromFileW 方法
生成指定的 Unicode 字符串的文件的内容哈希代码。  
  
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
  
## <a name="return-value"></a>返回值  
 `S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。  
  
## <a name="remarks"></a>备注  
 此方法等同于[iclrstrongname:: Gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)方法，只不过文件名规范是 Unicode 而不是 ANSI。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [GetHashFromFile 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
