---
title: "CorLaunchApplication 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type: COM
f1_keywords: CorLaunchApplication
helpviewer_keywords: CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf4392f7b30a5faa1cb01e24f9262260d9c6e93a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication 函数
启动位于指定的网络路径，使用指定的清单和其他应用程序数据的应用程序。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwClickOnceHost`  
 [in]值为[HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md)枚举，它指定的启动应用程序的宿主类型。  
  
 `pwzAppFullName`  
 [in]正在启动应用程序的完整名称。  
  
 `dwManifestPaths`  
 [in]应用程序的清单路径的数量。  
  
 `ppwzManifestPaths`  
 [in]一个字符串数组，其中每个指定的应用程序正在启动清单的路径。  
  
 `dwActivationData`  
 [in]激活的应用程序正在启动的数据项目数。  
  
 `ppwzActivationData`  
 [in]一个字符串数组，其中每个是正在启动该应用程序的激活数据项。  
  
 `lpProcessInformation`  
 [out]有关应用程序加载的过程的信息指向的指针。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
