---
title: ICLRRuntimeInfo::LoadLibrary 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: 8c72f58bb65bd862b0625bfa0398b26bad0197e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192083"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a>ICLRRuntimeInfo::LoadLibrary 方法
从[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口表示的公共语言运行时（CLR）加载 .NET Framework 库。  
  
 此方法取代了[LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a>参数  
 `pwzDllName`  
 中要加载的程序集的名称。  
  
 `phndModule`  
 弄已加载的程序集的句柄。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_POINTER|`pwzDllName` 或 `phndModule` 为 null。|  
|E_OUTOFMEMORY|没有足够的内存可用来处理请求。|  
  
## <a name="remarks"></a>备注  
 此方法仅加载 .NET Framework 可再发行组件包中包含的 Dll。 它无法加载用户生成的程序集。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRRuntimeInfo 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
