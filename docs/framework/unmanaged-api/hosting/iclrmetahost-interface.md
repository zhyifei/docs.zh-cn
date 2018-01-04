---
title: "ICLRMetaHost 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost
helpviewer_keywords: ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type: apiref
caps.latest.revision: "28"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a12635e14b694b361e2877041588d7d9f08a4102
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahost-interface"></a>ICLRMetaHost 接口
提供一些方法，返回特定版本的公共语言运行时 (CLR) 基于其版本号，列表所有已安装的 Clr 中，列出在指定的进程中加载的所有运行时，发现用于编译的程序集、 退出进程的 CLR 版本使用正常的运行时关闭和查询旧的 API 绑定。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumerateInstalledRuntimes 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|返回一个包含有效的枚举[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)的计算机安装每个 CLR 版本的接口指针。|  
|[EnumerateLoadedRuntimes 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|返回一个包含有效的枚举[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)给定进程中加载每个 CLR 的接口指针。 此方法取代[GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)。|  
|[ExitProcess 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|尝试正常关闭所有已加载的运行时，然后终止该进程。 取代[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)函数。|  
|[GetRuntime 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|获取[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)与特定的 CLR 版本相对应的接口。 此方法取代[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数用于[STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)标志。|  
|[GetVersionFromFile 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|获取程序集的原始.NET Framework 编译版本 （存储在元数据），将给定文件路径。 此方法取代[GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)。|  
|[QueryLegacyV2RuntimeBinding 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|返回表示旧式激活策略具有已绑定到，例如通过使用的运行时的接口`useLegacyV2RuntimeActivationPolicy`属性[\<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)配置文件项，直接使用通过旧激活 Api 或通过调用[iclrruntimeinfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)方法。|  
|[RequestRuntimeLoadedNotification 方法](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|当首次加载，但尚未启动的 CLR 版本，可确保对指定的函数指针的回调。 此方法取代[LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)|  
  
## <a name="remarks"></a>备注  
 若要获取此接口的实例的唯一方法是通过调用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数，如下所示：  
  
```  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
