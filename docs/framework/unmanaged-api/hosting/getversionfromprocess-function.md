---
title: GetVersionFromProcess 函数
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: a04a0c5e6865c3664d2cb5fb341c3625e35d4d7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178121"
---
# <a name="getversionfromprocess-function"></a>GetVersionFromProcess 函数
获取与指定进程句柄关联的通用语言运行时 （CLR） 的版本号。  
  
 此功能已在 .NET 框架 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a>parameters  
 `hProcess`  
 [在]进程的句柄。  
  
 `pVersion`  
 [出]在成功完成方法后包含版本号字符串的缓冲区。  
  
 `cchBuffer`  
 [在]版本缓冲区的长度。  
  
 `pdwLength`  
 [出]指向版本号字符串长度的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回 WinError.h 中定义的标准组件对象模型 （COM） 错误代码，以及以下值。  
  
|返回代码|说明|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|`pVersion`为空，`cchBuffer`不为空，反之亦然。<br /><br /> -或-<br /><br /> `hProcess`不是进程的有效句柄。<br /><br /> -或-<br /><br /> 未加载 CLR。|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer`为空或小于版本字符串的长度。|  
|E_NOTIMPL|此方法在 Microsoft Windows 95、微软 Windows 98 或 Microsoft Windows 千年版操作系统上不可用。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [GetRequestedRuntimeInfo 函数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [GetRequestedRuntimeVersion 函数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
