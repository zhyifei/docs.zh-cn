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
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178150"
---
# <a name="getrequestedruntimeinfo-function"></a>GetRequestedRuntimeInfo 函数
获取有关应用程序请求的通用语言运行时 （CLR） 的版本和目录信息。  
  
 此功能已在 .NET 框架 4 中弃用。  
  
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
  
## <a name="parameters"></a>parameters  
 `pExe`  
 [在]应用程序的名称。  
  
 `pwszVersion`  
 [在]指定运行时的版本号的字符串。  
  
 `pConfigurationFile`  
 [在]与`pExe`关联的配置文件的名称。  
  
 `startupFlags`  
 [在]一个或多个[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举值。  
  
 `runtimeInfoFlags`  
 [在]一个或多个[RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)枚举值。  
  
 `pDirectory`  
 [出]一个缓冲区，在成功完成时包含到运行时的目录路径。  
  
 `dwDirectory`  
 [在]目录缓冲区的长度。  
  
 `dwDirectoryLength`  
 [出]指向目录路径字符串长度的指针。  
  
 `pVersion`  
 [出]一个缓冲区，在成功完成时包含运行时的版本号。  
  
 `cchBuffer`  
 [在]版本字符串缓冲区的长度。  
  
 `dwlength`  
 [出]指向版本字符串长度的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回 WinError.h 中定义的标准组件对象模型 （COM） 错误代码，以及以下值。  
  
|返回代码|说明|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|ERROR_INSUFFICIENT_BUFFER|目录缓冲区不够大，无法存储目录路径。<br /><br /> - 或 -<br /><br /> 版本缓冲区不够大，无法存储版本字符串。|  
  
## <a name="remarks"></a>备注  
 该方法`GetRequestedRuntimeInfo`返回有关加载到进程中的版本的运行时信息，这不一定是计算机上安装的最新版本。  
  
 在 .NET 框架版本 2.0 中，可以使用如下`GetRequestedRuntimeInfo`方法获取有关最新安装版本的信息：  
  
- 将`pExe`和`pwszVersion`参数`pConfigurationFile`指定为 null。  
  
- 在`runtimeInfoFlags`参数的枚举中`RUNTIME_INFO_FLAGS`指定RUNTIME_INFO_UPGRADE_VERSION标志。  
  
 在`GetRequestedRuntimeInfo`以下情况下，该方法不会返回最新的 CLR 版本：  
  
- 存在指定加载特定 CLR 版本的应用程序配置文件。 请注意，即使为`pConfigurationFile`参数指定 null，.NET 框架也会使用配置文件。  
  
- [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)方法称为指定较早的 CLR 版本。  
  
- 为早期 CLR 版本编译的应用程序当前正在运行。  
  
 对于参数`runtimeInfoFlags`，一次只能指定枚举的`RUNTIME_INFO_FLAGS`一个体系结构常量：  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [GetRequestedRuntimeVersion 函数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [GetVersionFromProcess 函数](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
