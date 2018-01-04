---
title: "GetRequestedRuntimeInfo 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeInfo
helpviewer_keywords: GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 49459001d3764988eff7b7a4381a843c44e596cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo 函数
获取有关公共语言运行时 (CLR) 请求的应用程序版本和目录信息。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pExe`  
 [in]应用程序的名称。  
  
 `pwszVersion`  
 [in]指定运行时的版本号的字符串。  
  
 `pConfigurationFile`  
 [in]与关联的配置文件的名称`pExe`。  
  
 `startupFlags`  
 [in]一个或多个[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举值。  
  
 `runtimeInfoFlags`  
 [in]一个或多个[RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)枚举值。  
  
 `pDirectory`  
 [out]包含成功完成后运行时的目录路径的缓冲区。  
  
 `dwDirectory`  
 [in]目录缓冲区的长度。  
  
 `dwDirectoryLength`  
 [out]指向目录的路径字符串的长度的指针。  
  
 `pVersion`  
 [out]包含成功完成后运行时的版本号的缓冲区。  
  
 `cchBuffer`  
 [in]版本字符串缓冲区的长度。  
  
 `dwlength`  
 [out]指向版本字符串的长度的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回标准的组件对象模型 (COM) 错误代码，除了以下值中 WinError.h，定义。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|ERROR_INSUFFICIENT_BUFFER|在目录缓冲区未足以存储的目录路径。<br /><br /> - 或 -<br /><br /> 在版本缓冲区未足以存储的版本字符串。|  
  
## <a name="remarks"></a>备注  
 `GetRequestedRuntimeInfo`方法返回运行时加载到进程，这不一定是最新版本的计算机上安装的版本信息。  
  
 在.NET Framework 2.0 版中，你可以通过获取有关最新安装的版本信息`GetRequestedRuntimeInfo`方法，如下所示：  
  
-   指定`pExe`， `pwszVersion`，和`pConfigurationFile`参数为 null。  
  
-   指定在 RUNTIME_INFO_UPGRADE_VERSION 标志`RUNTIME_INFO_FLAGS`枚举的`runtimeInfoFlags`参数。  
  
 `GetRequestedRuntimeInfo`方法不在以下情况下返回的最新的 CLR 版本：  
  
-   指定正在加载特定的 CLR 版本的应用程序配置文件存在。 请注意，.NET Framework 将使用配置文件，即使你指定为空`pConfigurationFile`参数。  
  
-   [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)方法调用指定的早期的 CLR 版本。  
  
-   当前正在运行的应用程序编译为较早的 CLR 版本。  
  
 有关`runtimeInfoFlags`参数，你可以指定的体系结构常量之一`RUNTIME_INFO_FLAGS`一次的枚举：  
  
-   RUNTIME_INFO_REQUEST_IA64  
  
-   RUNTIME_INFO_REQUEST_AMD64  
  
-   RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [GetRequestedRuntimeVersion 函数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [GetVersionFromProcess 函数](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
