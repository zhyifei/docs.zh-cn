---
title: "IMetaDataDispenserEx::FindAssemblyModule 方法"
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
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 482bc9b9a89d876e7ac09fcb4edcd190adc168f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a>IMetaDataDispenserEx::FindAssemblyModule 方法
未实现此方法。 如果调用，它将返回 E_NOTIMPL。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szAppBase`  
 [in]未使用。  
  
 `szPrivateBin`  
 [in]未使用。  
  
 `szGlobalBin`  
 [in]未使用。  
  
 `szAssemblyName`  
 [in]模块的名称。  
  
 `szModuleName`  
 [in]要找的程序集。  
  
 `szName`  
 [out]程序集的简单名称。  
  
 `cchName`  
 [in]大小，以字节为单位的`szName`。  
  
 `pcName`  
 [out]中实际返回的字符数`szName`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
