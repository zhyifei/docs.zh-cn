---
title: "ICLRRuntimeInfo::GetProcAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetProcAddress
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1b8af06a52a3961bb3e551375350dee849343b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetprocaddress-method"></a>ICLRRuntimeInfo::GetProcAddress 方法
获取指定已从公共语言运行时 (CLR) 与此接口关联导出的函数的地址。  
  
 此方法取代[GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
#### <a name="parameters"></a>参数  
 `pszProcName`  
 [in]导出函数的名称。  
  
 `ppProc`  
 [out]导出函数的地址。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_POINTER|`pszProcName` 或 `ppProc` 为 null。|  
|CLR_E_SHIM_RUNTIMEEXPORT|指定的函数不是导出的函数。|  
  
## <a name="remarks"></a>备注  
 此方法会导致 CLR 加载，但未初始化。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRRuntimeInfo 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
