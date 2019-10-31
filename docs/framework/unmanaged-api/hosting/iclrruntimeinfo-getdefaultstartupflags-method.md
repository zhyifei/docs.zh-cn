---
title: ICLRRuntimeInfo::GetDefaultStartupFlags 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: 0ce822533b0699f3467dc08044aa4dab59285a77
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120316"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>ICLRRuntimeInfo::GetDefaultStartupFlags 方法
获取启动标志和主机配置文件，该文件将用于启动运行时。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a>参数  
 `pdwStartupFlags`  
 弄指向当前设置的主机启动标志的指针。  
  
 `pwzHostConfigFile`  
 弄一个指针，指向当前宿主配置文件的目录路径。  
  
 `pcchHostConfigFile`  
 [in，out]对于输入，为避免缓冲区溢出的 `pwzHostConfigFile`大小。 如果 `pwzHostConfigFile` 为 null，则该方法返回预分配所需的 `pwzHostConfigFile` 大小。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定的 HRESULT 以及指示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
  
## <a name="remarks"></a>备注  
 此方法返回默认标志值（`STARTUP_CONCURRENT_GC` 和 `NULL`），或以前对[ICLRRuntimeInfo：： SetDefaultStartupFlags 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md)的调用提供的值; 或者，如果绑定到此运行时，则为任何 `CorBind*` 方法设置的值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRRuntimeInfo 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
