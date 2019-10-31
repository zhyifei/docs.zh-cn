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
ms.openlocfilehash: 76c033b11f3212241827d74f4fe18ee881f20b64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127039"
---
# <a name="getversionfromprocess-function"></a>GetVersionFromProcess 函数
获取与指定的进程句柄关联的公共语言运行时（CLR）的版本号。  
  
 此函数已在 .NET Framework 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a>参数  
 `hProcess`  
 中进程的句柄。  
  
 `pVersion`  
 弄一个缓冲区，其中包含成功完成方法后的版本号字符串。  
  
 `cchBuffer`  
 中版本缓冲区的长度。  
  
 `pdwLength`  
 弄指向版本号字符串长度的指针。  
  
## <a name="return-value"></a>返回值  
 除以下值外，此方法还返回 Winerror.h 中定义的标准组件对象模型（COM）错误代码。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|`pVersion` 为 null，并且 `cchBuffer` 不为 null，反之亦然。<br /><br /> 或<br /><br /> `hProcess` 不是进程的有效句柄。<br /><br /> 或<br /><br /> 未加载 CLR。|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer` 为 null 或小于版本字符串的长度。|  
|E_NOTIMPL|此方法在 Microsoft Windows 95、Microsoft Windows 98 或 Microsoft Windows Millennium Edition 操作系统上不可用。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [GetRequestedRuntimeInfo 函数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [GetRequestedRuntimeVersion 函数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
