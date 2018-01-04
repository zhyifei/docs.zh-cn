---
title: "CorBindToRuntime 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CorBindToRuntime
helpviewer_keywords: CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e6ce976961eedaa58ad265a133c15b2f27a8985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntime-function"></a>CorBindToRuntime 函数
使非托管的宿主能够将公共语言运行时 (CLR) 加载到过程中。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pwszVersion`  
 [in]你想要加载描述的 CLR 版本的字符串。  
  
 .NET Framework 中的版本号用句点分隔的四个部分组成： *major.minor.build.revision*。 将字符串作为传递`pwszVersion`必须以字符"v"跟版本号 (例如，"v1.0.1529") 的前三个部分开头。  
  
 某些版本的 CLR 与指定与以前版本的 CLR 的兼容性的策略语句一起安装。 默认情况下，启动填充码将评估`pwszVersion`针对策略语句和加载运行时的最新版本的适用于所请求的版本。 主机可以强制填充码可跳过策略评估，负载中指定的确切版本`pwszVersion`通过将的值传递`STARTUP_LOADER_SAFEMODE`为`flags`参数，如下所述。  
  
 如果调用方指定为 null `pwszVersion`，加载运行时的最新版本。 如果传递 null 不，主机加载的运行时版本的任何控件。 虽然这种方法可能在某些情况下适用，但强烈建议主机提供一个要加载的特定版本。  
  
 `pwszBuildFlavor`  
 [in]一个字符串，指定是否以加载服务器或工作站生成的 CLR。 有效值为 `svr` 和 `wks`。 服务器版本进行了优化以利用多个处理器进行垃圾回收和工作站生成优化的单处理器计算机上运行的客户端应用程序。  
  
 如果`pwszBuildFlavor`设置为 null，则将加载工作站版本。 单处理器计算机上运行时，工作站生成始终处于加载状态，即使`pwszBuildFlavor`设置为`svr`。 但是，如果`pwszBuildFlavor`设置为`svr`和指定并发垃圾回收 (请参阅的说明`flags`参数)，则服务器将加载版本。  
  
 `rclsid`  
 [in]`CLSID`实现的组件类的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。 支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。  
  
 `riid`  
 [in]`IID`从所请求的接口的`rclsid`。 支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。  
  
 `ppv`  
 [out]指向返回的接口指针`riid`。  
  
## <a name="remarks"></a>备注  
 如果`pwszVersion`指定不存在，运行时版本`CorBindToRuntimeEx`返回 CLR_E_SHIM_RUNTIMELOAD HRESULT 值。  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>执行上下文和的 Windows 标识的流  
 中的 clr 版本 1<xref:System.Security.Principal.WindowsIdentity>对象不流过异步点，例如新线程，线程池或计时器回调。 在 2.0 版中的 CLR，<xref:System.Threading.ExecutionContext>对象包装有关当前正在执行的线程的一些信息，并且流动它跨任何异步的点，但是不能跨应用程序域边界。 同样，<xref:System.Security.Principal.WindowsIdentity>对象也会流过任何异步的点。 因此，当前线程上的模拟如果有的话，也会流动。  
  
 您可以改变两种方式流：  
  
1.  通过修改<xref:System.Threading.ExecutionContext>设置以禁止显示的每个线程基础上的流 (请参阅<xref:System.Threading.ExecutionContext.SuppressFlow%2A>， <xref:System.Security.SecurityContext.SuppressFlow%2A>，和<xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>方法)。  
  
2.  通过更改进程的默认模式为版本 1 兼容性模式，其中<xref:System.Security.Principal.WindowsIdentity>对象不流经任何异步的点，而不考虑<xref:System.Threading.ExecutionContext>当前线程上的设置。 如何更改默认模式取决于是否使用托管的可执行文件或使用非托管承载接口来加载 CLR:  
  
    1.  用于托管可执行文件，必须设置`enabled`属性[ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)元素`true`。  
  
    2.  对于非托管承载接口、 将`STARTUP_LEGACY_IMPERSONATION`中标记出来`flags`参数调用时`CorBindToRuntimeEx`函数。  
  
     版本 1 兼容模式适用于进程中的所有应用程序域和的整个过程。  
  
## <a name="remarks"></a>备注  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)和`CorBindToRuntime`执行相同的操作，但`CorBindToRuntimeEx`函数使你可以设置标志以指定的 CLR 的行为。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [CorBindToRuntimeByCfg 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [CorBindToRuntimeHost 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
