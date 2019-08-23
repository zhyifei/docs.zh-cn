---
title: ICLRMetaHost::GetRuntime 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b796942df153bf2c6ab703d748449331c9a0b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939848"
---
# <a name="iclrmetahostgetruntime-method"></a>ICLRMetaHost::GetRuntime 方法
获取与特定版本的公共语言运行时 (CLR) 相对应的[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。 此方法取代了与[STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)标志一起使用的[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a>参数  
 `pwzVersion`  
 中存储在元数据中的 .NET Framework 编译版本, 格式为 "v*A*"。*B*[.*X*] "。 *A*、 *B*和*X*是与主版本、次版本和生成号对应的十进制数字。  
  
> [!NOTE]
> 此参数必须匹配 .NET Framework 版本的目录名称, 因为它显示在 C:\Windows\Microsoft.NET\Framework 或 C:\Windows\Microsoft.NET\Framework64。  
  
 示例值为 "v1.0.3705"、"v 1.1.4322"、"v 2.0.50727" 和 "v4.0"。*X*", 其中*X*依赖于安装的生成号。 "V" 前缀是必需的。  
  
 `riid`  
 中所需接口的标识符。 目前, 此参数的有效值只有 IID_ICLRRuntimeInfo。  
  
 `ppRuntime`  
 弄指向[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口的指针, 该接口对应于所请求的运行时。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_POINTER|`pwzVersion` 或 `ppRuntime` 为 null。|  
  
## <a name="remarks"></a>备注  
 此方法与旧接口 (如[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)接口) 和旧功能 (如不推荐`CorBindTo*`使用的函数) 一致地交互 (请参阅 .NET Framework 2.0 托管中已弃用的[CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)API)。 也就是说, 用旧版 API 加载的运行时对新 API 可见, 而与新 API 一起加载的运行时对旧 API 可见。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRMetaHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [弃用的 CLR 承接接口和组件类](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)
- [CLR Hosting 接口](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
