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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c1d83b32402343f3cd2b5403e328698abd6a930
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436210"
---
# <a name="corbindtoruntimehost-function"></a>CorBindToRuntimeHost 函数
使主机可以加载到进程的指定公共语言运行时 (CLR) 版本。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
#### <a name="parameters"></a>参数  
 `pwszVersion`  
 [in]一个字符串，描述要加载的 clr 的版本。  
  
 .NET Framework 中的版本号用句点分隔的四个部分组成： *major.minor.build.revision*。 将字符串作为传递`pwszVersion`必须以字符"v"跟版本号 (例如，"v1.0.1529") 的前三个部分开头。  
  
 某些版本的 CLR 与指定与以前版本的 CLR 的兼容性的策略语句一起安装。 默认情况下，启动填充码将评估`pwszVersion`针对策略语句和加载运行时的最新版本的适用于所请求的版本。 主机可以强制填充码可跳过策略评估，负载中指定的确切版本`pwszVersion`通过传递一个值为 STARTUP_LOADER_SAFEMODE`startupFlags`参数。  
  
 如果`pwszVersion`是`null,`方法不会加载任何版本的 CLR。 相反，它将返回 CLR_E_SHIM_RUNTIMELOAD，指示它未能将运行时加载。  
  
 `pwszBuildFlavor`  
 [in]一个字符串，指定是否以加载服务器或工作站生成的 CLR。 有效值为 `svr` 和 `wks`。 服务器版本进行了优化以利用多个处理器进行垃圾回收和工作站生成优化的单处理器计算机上运行的客户端应用程序。  
  
 如果`pwszBuildFlavor`设置为 null，则将加载工作站版本。 单处理器计算机上运行时，工作站生成始终处于加载状态，即使`pwszBuildFlavor`设置为`svr`。 但是，如果`pwszBuildFlavor`设置为`svr`和指定并发垃圾回收 (请参阅的说明`startupFlags`参数)，则服务器将加载版本。  
  
> [!NOTE]
>  运行 WOW64 应用程序中不支持并发垃圾回收 x86 仿真程序上实现 （以前称为 ia-64） 的 Intel 的 Itanium 体系结构的 64 位系统。 有关使用 64 位 Windows 系统上的 WOW64 的详细信息，请参阅[运行 32 位应用程序](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx)。  
  
 `pwszHostConfigFile`  
 [in]指定要加载的 clr 版本的主机配置文件的名称。 如果文件名称不包含完全限定的路径，则假定文件进行调用的可执行文件所在相同目录中。  
  
 `pReserved`  
 [in]留待将来扩展。  
  
 `startupFlags`  
 [in]一组控制并发垃圾回收、 非特定于域的代码和的行为的标志`pwszVersion`参数。 如果未设置标志，则默认值是单一域。 有关支持的值的列表，请参阅[STARTUP_FLAGS 枚举](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)。  
  
 `rclsid`  
 [in]`CLSID`实现的组件类的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。 支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。  
  
 `riid`  
 [in]`IID`您请求的接口。 支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。  
  
 `ppv`  
 [out]指向已加载的运行时版本的接口指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.idl  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [CorBindToRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [CorBindToRuntimeByCfg 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
