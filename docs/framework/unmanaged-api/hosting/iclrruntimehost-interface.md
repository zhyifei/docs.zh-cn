---
title: ICLRRuntimeHost 接口
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f159c0b57f2087b608fac8cbc9b9c64ceb063a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965996"
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost 接口
提供与 .NET Framework 版本1中提供的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)接口类似的功能, 其中包含以下更改:  
  
- 用于设置宿主控件接口的[SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)方法的添加。  
  
- 省略提供`ICorRuntimeHost`的某些方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ExecuteApplication 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|在基于清单的 ClickOnce 部署方案中用于指定要在新域中激活的应用程序。|  
|[ExecuteInAppDomain 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|指定要<xref:System.AppDomain>在其中执行指定的托管代码的。|  
|[ExecuteInDefaultAppDomain 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|在指定的程序集中调用指定类型的指定方法。|  
|[GetCLRControl 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|获取宿主可用于自定义公共语言运行时 (CLR) 的各个方面的[ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)类型的接口指针。|  
|[GetCurrentAppDomainId 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|获取当前正在执行的的<xref:System.AppDomain>数值标识符。|  
|[SetHostControl 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|设置宿主控件接口。 `SetHostControl` 调用`Start`之前必须调用。|  
|[Start 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|将 CLR 初始化为一个进程。|  
|[Stop 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|停止由运行时执行的代码。|  
|[UnloadAppDomain 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<xref:System.AppDomain>卸载对应于指定数值标识符的。|  
  
## <a name="remarks"></a>备注  
 从 .NET Framework 4 开始, 使用[ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)接口获取指向[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口的指针, 然后调用[ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)方法`ICLRRuntimeHost`以获取指向的指针。 在 .NET Framework 的早期版本中, 主机通过调用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)获取`ICLRRuntimeHost`指向实例的指针。 若要提供 .NET Framework 版本2.0 中提供的任何技术的实现, 必须使用`ICLRRuntimeHost` `ICorRuntimeHost`而不是。  
  
> [!IMPORTANT]
> 请不要在调用[ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)方法之前调用[Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法来激活基于清单的应用程序。 如果首先调用`ExecuteApplication`方法,方法调用将失败。 `Start`  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CLRRuntimeHost 组件类](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
