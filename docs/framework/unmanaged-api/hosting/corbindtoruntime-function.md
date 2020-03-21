---
title: CorBindToRuntime 函数
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
ms.openlocfilehash: 2db9d26ef2dec150977c468b16334a7cb4b3d49c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176508"
---
# <a name="corbindtoruntime-function"></a>CorBindToRuntime 函数
使非托管主机能够将通用语言运行时 （CLR） 加载到进程中。  
  
 此功能已在 .NET 框架 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,
    [in]  LPCWSTR     pwszBuildFlavor,
    [in]  REFCLSID    rclsid,
    [in]  REFIID      riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>parameters  
 `pwszVersion`  
 [在]描述要加载的 CLR 版本的字符串。  
  
 .NET 框架中的版本号由四个部分组成，由句点分隔：*主要.minor.build.revision*. 传递的`pwszVersion`字符串必须以字符"v"开头，后跟版本号的前三个部分（例如，"v1.0.1529"）。  
  
 CLR 的某些版本都安装了策略语句，该语句指定与 CLR 的早期版本的兼容性。 默认情况下，启动希姆`pwszVersion`根据策略语句进行评估，并加载与所请求版本兼容的最新版本的运行时。 主机可以强制 him 跳过策略评估，并通过传递`pwszVersion``STARTUP_LOADER_SAFEMODE``flags`参数的值来加载指定的确切版本，如下所述。  
  
 如果调用方为`pwszVersion`指定 null，则加载运行时的最新版本。 传递 null 使主机无法控制加载的哪个版本的运行时。 尽管此方法在某些情况下可能适用，但强烈建议主机提供要加载的特定版本。  
  
 `pwszBuildFlavor`  
 [在]指定是加载 CLR 的服务器还是工作站构建的字符串。 有效值为 `svr` 和 `wks`。 服务器生成经过优化，以利用多个处理器进行垃圾回收，工作站生成针对在单处理器计算机上运行的客户端应用程序进行了优化。  
  
 如果`pwszBuildFlavor`设置为 null，则加载工作站生成。 在单处理器计算机上运行时，工作站生成始终加载，即使`pwszBuildFlavor`设置为`svr`。 但是，如果`pwszBuildFlavor`设置为`svr`并指定了并发垃圾回收（请参阅`flags`参数的说明），则加载服务器生成。  
  
 `rclsid`  
 [在]`CLSID`实现[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口的共类。 支持的值CLSID_CorRuntimeHost或CLSID_CLRRuntimeHost。  
  
 `riid`  
 [在]从`IID`的请求接口的`rclsid`的 支持的值IID_ICorRuntimeHost或IID_ICLRRuntimeHost。  
  
 `ppv`  
 [出]返回的接口指针到`riid`。  
  
## <a name="remarks"></a>备注  
 如果`pwszVersion`指定不存在的运行时版本，`CorBindToRuntimeEx`则返回 hRESULT 值CLR_E_SHIM_RUNTIMELOAD。  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>执行上下文和 Windows 标识的流  
 在 CLR 的版本 1<xref:System.Security.Principal.WindowsIdentity>中，对象不会跨异步点（如新线程、线程池或计时器回调）流动。 在 CLR 的版本 2.0<xref:System.Threading.ExecutionContext>中，对象会包装有关当前正在执行的线程的一些信息，并将其流过任何异步点，但不跨应用程序域边界。 同样，<xref:System.Security.Principal.WindowsIdentity>对象也流过任何异步点。 因此，线程上的当前模拟（如果有）也会流动。  
  
 您可以通过两种方式更改流：  
  
1. 通过修改<xref:System.Threading.ExecutionContext>设置以按线程禁止流（请参阅 、<xref:System.Threading.ExecutionContext.SuppressFlow%2A><xref:System.Security.SecurityContext.SuppressFlow%2A>和方法）。 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>  
  
2. 通过将进程默认模式更改为版本 1 兼容性模式，其中<xref:System.Security.Principal.WindowsIdentity>对象不会流过任何异步点，而不考虑当前线程上的<xref:System.Threading.ExecutionContext>设置。 更改默认模式的方式取决于您是使用托管可执行文件还是非托管托管接口来加载 CLR：  
  
    1. 对于托管可执行文件，必须将`enabled`[\<旧模拟策略>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)元素的属性设置为`true`。  
  
    2. 对于非托管托管接口，在`STARTUP_LEGACY_IMPERSONATION`调用`flags``CorBindToRuntimeEx`函数时在参数中设置标志。  
  
     版本 1 兼容性模式适用于整个过程和流程中的所有应用程序域。  
  
## <a name="remarks"></a>备注  
 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) `CorBindToRuntime`并执行相同的操作，`CorBindToRuntimeEx`但该函数允许您设置标志以指定 CLR 的行为。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntimeByCfg 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
