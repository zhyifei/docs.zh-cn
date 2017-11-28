---
title: "ICLRStrongName::StrongNameCompareAssemblies 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameCompareAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab69a0d0bb5894c2393e240b4f89b9a16dd98939
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>ICLRStrongName::StrongNameCompareAssemblies 方法
确定是否两个程序集的差异仅在于其强名称签名。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszAssembly1`  
 [in]第一个程序集的路径。  
  
 `wszAssembly2`  
 [in]第二个程序集的路径。  
  
 `pdwResult`  
 [out]以下值之一：  
  
-   `SN_CMP_DIFFERENT`(0)-指定程序集包含不同的数据。  
  
-   `SN_CMP_IDENTICAL`(1)-指定程序程序集完全相同，包括其签名和校验和。  
  
-   `SN_CMP_SIGONLY`(2)-指定程序集不同只能由签名和校验和。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>备注  
 程序集的强名称签名组成程序集的文本名称、 版本、 区域性和公钥标记。  
  
## <a name="see-also"></a>另请参阅  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
