---
title: ICLRMetaHost 接口
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
ms.openlocfilehash: bb760f4923cc3530a28bc68180db743ee468b51d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140908"
---
# <a name="iclrmetahost-interface"></a>ICLRMetaHost 接口
提供一些方法，这些方法基于公共语言运行时（CLR）的版本号返回特定版本的公共语言运行时（CLR），列出所有已安装的 Clr，列出在指定进程中加载的所有运行时，发现编译程序集所用的 CLR 版本，退出进程在干净运行时关闭的情况下，查询旧 API 绑定。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumerateInstalledRuntimes 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|返回一个枚举，该枚举包含计算机上安装的每个 CLR 版本的有效[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口指针。|  
|[EnumerateLoadedRuntimes 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|返回一个枚举，该枚举包含给定进程中加载的每个 CLR 的有效[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口指针。 此方法取代了[GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)。|  
|[ExitProcess 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|尝试正常关闭所有加载的运行时，然后终止进程。 取代[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)函数。|  
|[GetRuntime 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|获取与特定 CLR 版本相对应的[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。 此方法取代了与[STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)标志一起使用的[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数。|  
|[GetVersionFromFile 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|在给定程序集的文件路径的情况下，获取程序集的原始 .NET Framework 编译版本（存储在元数据中）。 此方法取代了[GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)。|  
|[QueryLegacyV2RuntimeBinding 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|返回一个接口，该接口表示已绑定旧式激活策略的运行时，例如通过使用[\<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)配置文件项上的 `useLegacyV2RuntimeActivationPolicy` 特性，通过直接使用旧的激活 api 或调用[ICLRRuntimeInfo：： BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)方法。|  
|[RequestRuntimeLoadedNotification 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|当首次加载 CLR 版本但尚未启动时，保证对指定函数指针的回调。 此方法取代[LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)|  
  
## <a name="remarks"></a>备注  
 获取此接口实例的唯一方法是调用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数，如下所示：  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
