---
title: GetRequestedRuntimeInfo 函数
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
ms.openlocfilehash: cd1d9e768698115bee22e35699b044e0c3526d2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136326"
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo 函数
获取有关应用程序请求的公共语言运行时（CLR）的版本和目录信息。  
  
 此函数已在 .NET Framework 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="parameters"></a>参数  
 `pExe`  
 中应用程序的名称。  
  
 `pwszVersion`  
 中一个字符串，指定运行时的版本号。  
  
 `pConfigurationFile`  
 中与 `pExe`相关联的配置文件的名称。  
  
 `startupFlags`  
 中一个或多个[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举值。  
  
 `runtimeInfoFlags`  
 中一个或多个[RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)枚举值。  
  
 `pDirectory`  
 弄一个缓冲区，其中包含成功完成后运行时的目录路径。  
  
 `dwDirectory`  
 中目录缓冲区的长度。  
  
 `dwDirectoryLength`  
 弄指向目录路径字符串长度的指针。  
  
 `pVersion`  
 弄一个缓冲区，其中包含成功完成后运行时的版本号。  
  
 `cchBuffer`  
 中版本字符串缓冲区的长度。  
  
 `dwlength`  
 弄指向版本字符串长度的指针。  
  
## <a name="return-value"></a>返回值  
 除以下值外，此方法还返回 Winerror.h 中定义的标准组件对象模型（COM）错误代码。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|ERROR_INSUFFICIENT_BUFFER|目录缓冲区不够大，无法存储目录路径。<br /><br /> - 或 -<br /><br /> 版本缓冲区不够大，无法存储版本字符串。|  
  
## <a name="remarks"></a>备注  
 `GetRequestedRuntimeInfo` 方法返回有关加载到进程中的版本的运行时信息，这不一定是计算机上安装的最新版本。  
  
 在 .NET Framework 版本2.0 中，可以通过使用 `GetRequestedRuntimeInfo` 方法获取有关最新安装的版本的信息，如下所示：  
  
- 将 `pExe`、`pwszVersion`和 `pConfigurationFile` 参数指定为 null。  
  
- 指定 `runtimeInfoFlags` 参数 `RUNTIME_INFO_FLAGS` 枚举中的 RUNTIME_INFO_UPGRADE_VERSION 标志。  
  
 在以下情况下，`GetRequestedRuntimeInfo` 方法不会返回最新的 CLR 版本：  
  
- 指定加载特定 CLR 版本的应用程序配置文件存在。 请注意，.NET Framework 将使用配置文件，即使为 `pConfigurationFile` 参数指定了 null 也是如此。  
  
- 将[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)方法指定为指定较早的 CLR 版本。  
  
- 为早期 CLR 版本编译的应用程序当前正在运行。  
  
 对于 `runtimeInfoFlags` 参数，可以一次仅指定 `RUNTIME_INFO_FLAGS` 枚举的一个体系结构常量：  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [GetRequestedRuntimeVersion 函数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [GetVersionFromProcess 函数](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
