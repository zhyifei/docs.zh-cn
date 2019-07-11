---
title: CorLaunchApplication 函数
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9861de733a9acb43c7e2a4b4941f9945fc5f0ba7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758371"
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication 函数
启动指定的网络路径，使用指定的清单和其他应用程序数据的应用程序。  
  
 .NET Framework 4 中已弃用此函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="parameters"></a>参数  
 `dwClickOnceHost`  
 [in]值为[HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md)枚举，用于指定的启动应用程序的宿主类型。  
  
 `pwzAppFullName`  
 [in]正在启动的应用程序的全名。  
  
 `dwManifestPaths`  
 [in]应用程序的清单路径数。  
  
 `ppwzManifestPaths`  
 [in]一个字符串数组，其中每个指定要启动的应用程序清单的路径。  
  
 `dwActivationData`  
 [in]正在启动的应用程序的激活数据项目数。  
  
 `ppwzActivationData`  
 [in]一个字符串数组，其中每个是要启动的应用程序的激活数据项。  
  
 `lpProcessInformation`  
 [out]指向有关在其中加载应用程序过程的信息的指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
