---
title: CorBindToRuntimeHost 函数
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
ms.openlocfilehash: 6566adc442034763e0209869404b60b5afa63866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176482"
---
# <a name="corbindtoruntimehost-function"></a>CorBindToRuntimeHost 函数
使主机能够将指定版本的通用语言运行时 （CLR） 加载到进程中。  
  
 此功能已在 .NET 框架 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,
    [in] LPCWSTR       pwszBuildFlavor,
    [in] LPCWSTR       pwszHostConfigFile,
    [in] VOID*         pReserved,
    [in] DWORD         startupFlags,
    [in] REFCLSID      rclsid,
    [in] REFIID        riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>parameters  
 `pwszVersion`  
 [在]描述要加载的 CLR 版本的字符串。  
  
 .NET 框架中的版本号由四个部分组成，由句点分隔：*主要.minor.build.revision*. 传递的`pwszVersion`字符串必须以字符"v"开头，后跟版本号的前三个部分（例如，"v1.0.1529"）。  
  
 CLR 的某些版本都安装了策略语句，该语句指定与 CLR 的早期版本的兼容性。 默认情况下，启动希姆`pwszVersion`根据策略语句进行评估，并加载与所请求版本兼容的最新版本的运行时。 主机可以通过传递`startupFlags`参数的STARTUP_LOADER_SAFEMODE值来强制 him 跳过策略评估并加载指定`pwszVersion`的确切版本。  
  
 如果`pwszVersion`是`null,`，该方法不会加载 CLR 的任何版本。 相反，它将返回CLR_E_SHIM_RUNTIMELOAD，这表明它无法加载运行时。  
  
 `pwszBuildFlavor`  
 [在]指定是加载 CLR 的服务器还是工作站构建的字符串。 有效值为 `svr` 和 `wks`。 服务器生成经过优化，以利用多个处理器进行垃圾回收，工作站生成针对在单处理器计算机上运行的客户端应用程序进行了优化。  
  
 如果`pwszBuildFlavor`设置为 null，则加载工作站生成。 在单处理器计算机上运行时，工作站生成始终加载，即使`pwszBuildFlavor`设置为`svr`。 但是，如果`pwszBuildFlavor`设置为`svr`并指定了并发垃圾回收（请参阅`startupFlags`参数的说明），则加载服务器生成。  
  
> [!NOTE]
> 在 64 位系统上运行 WOW64 x86 仿真器的应用程序不支持并发垃圾回收，这些系统实现了英特尔 Itanium 架构（以前称为 IA-64）。 有关在 64 位 Windows 系统上使用 WOW64 的详细信息，请参阅[运行 32 位应用程序](/windows/desktop/WinProg64/running-32-bit-applications)。  
  
 `pwszHostConfigFile`  
 [在]指定要加载的 CLR 版本的主机配置文件的名称。 如果文件名不包含完全限定的路径，则假定该文件与进行调用的可执行文件位于同一目录中。  
  
 `pReserved`  
 [在]保留以供将来扩展。  
  
 `startupFlags`  
 [在]控制并发垃圾回收、域中立代码和`pwszVersion`参数行为的标志集。 如果未设置标志，则默认值为单个域。 有关受支持值的列表，请参阅[STARTUP_FLAGS枚举](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)。  
  
 `rclsid`  
 [在]`CLSID`实现[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口的共类。 支持的值CLSID_CorRuntimeHost或CLSID_CLRRuntimeHost。  
  
 `riid`  
 [在]您`IID`请求的接口的。 支持的值IID_ICorRuntimeHost或IID_ICLRRuntimeHost。  
  
 `ppv`  
 [出]指向加载的运行时版本的接口指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.idl  
  
 **库：** MSCorEE.dll  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [CorBindToRuntimeByCfg 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
