---
title: "ICLRRuntimeInfo::GetRuntimeDirectory 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetRuntimeDirectory
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddaca8232f0b262377c7915852da89cecec09993
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a>ICLRRuntimeInfo::GetRuntimeDirectory 方法
获取公共语言运行时 (CLR) 与此接口关联的安装目录。  
  
 此方法取代[GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)函数中的.NET Framework 版本 2.0、 3.0 和 3.5 提供。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a>参数  
 `pwzBuffer`  
 [out]返回的 CLR 安装目录。 安装路径是完全限定;例如，"c:\windows\microsoft.net\framework\v1.0.3705\\"。  
  
 `pchBuffer`  
 [在中，out]指定的大小`pwzBuffer`以避免缓冲区溢出。 如果`pwzBuffer`为 null，`pchBuffer`返回的所需的大小`pwzBuffer`。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_POINTER|`pwzBuffer` 或 `pchBuffer` 为 null。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRRuntimeInfo 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
