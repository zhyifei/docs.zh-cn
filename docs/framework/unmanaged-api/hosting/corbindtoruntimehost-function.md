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
ms.openlocfilehash: a6d9708e7281a72c88ba28012006784f7b0ee9d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124360"
---
# <a name="corbindtoruntimehost-function"></a>CorBindToRuntimeHost 函数
使宿主可以将指定版本的公共语言运行时（CLR）加载到进程中。  
  
 此函数已在 .NET Framework 4 中弃用。  
  
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
  
## <a name="parameters"></a>参数  
 `pwszVersion`  
 中一个字符串，描述要加载的 CLR 的版本。  
  
 .NET Framework 中的版本号由以句点分隔的四个部分组成：*主*版本. 次要版本. 内部版本号. 修订号。 作为 `pwszVersion` 传递的字符串必须以字符 "v" 开头，后跟版本号的前三个部分（例如，"1.0.1529"）。  
  
 某些版本的 CLR 随策略声明一起安装，后者指定与以前版本的 CLR 的兼容性。 默认情况下，启动填充程序根据策略语句计算 `pwszVersion`，并加载与请求的版本兼容的运行时的最新版本。 主机可以通过为 `startupFlags` 参数传递值 STARTUP_LOADER_SAFEMODE 来强制填充程序跳过策略评估并加载 `pwszVersion` 中指定的确切版本。  
  
 如果 `pwszVersion` `null,` 则此方法不会加载任何版本的 CLR。 相反，它会返回 CLR_E_SHIM_RUNTIMELOAD，这表示它未能加载运行时。  
  
 `pwszBuildFlavor`  
 中一个字符串，指定是加载 CLR 的服务器还是工作站版本。 有效值为 `svr` 和 `wks`。 服务器版本经过优化，可利用多个处理器进行垃圾回收，工作站构建针对单处理器计算机上运行的客户端应用程序进行了优化。  
  
 如果 `pwszBuildFlavor` 设置为 null，则会加载工作站构建。 在单处理器计算机上运行时，始终会加载工作站构建，即使 `pwszBuildFlavor` 设置为 `svr`。 但是，如果 `pwszBuildFlavor` 设置为 `svr` 并指定了并发垃圾回收（请参阅 `startupFlags` 参数的说明），则将加载服务器生成。  
  
> [!NOTE]
> 在实现 Intel Itanium 体系结构（以前称为 IA-64）的64位系统上运行 WOW64 x86 模拟器的应用程序中不支持并发垃圾回收。 有关在64位 Windows 系统上使用 WOW64 的详细信息，请参阅[运行32位应用程序](/windows/desktop/WinProg64/running-32-bit-applications)。  
  
 `pwszHostConfigFile`  
 中主机配置文件的名称，该名称指定要加载的 CLR 的版本。 如果文件名不包含完全限定的路径，则假定该文件与进行调用的可执行文件位于同一目录中。  
  
 `pReserved`  
 中保留以供将来进行扩展。  
  
 `startupFlags`  
 中一组标志，这些标志控制并发垃圾回收、非特定于域的代码以及 `pwszVersion` 参数的行为。 如果未设置任何标志，则默认值为单一域。 有关支持的值的列表，请参阅[STARTUP_FLAGS 枚举](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)。  
  
 `rclsid`  
 中用于实现[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口的 coclass 的 `CLSID`。 支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。  
  
 `riid`  
 中请求的接口的 `IID`。 支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。  
  
 `ppv`  
 弄指向已加载的运行时版本的接口指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [CorBindToRuntimeByCfg 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
