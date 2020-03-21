---
title: GetRequestedRuntimeVersionForCLSID 函数
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178112"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID 函数
获取具有指定的`CLSID`类的相应通用语言运行时 （CLR） 版本信息。  
  
 此功能已在 .NET 框架 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a>parameters  
 `rclsid`  
 [在] 组件`CLSID`的 。  
  
 `pVersion`  
 [出] 成功完成后包含版本号字符串的缓冲区。  
  
 `cchBuffer`  
 [在] `pVersion`缓冲区的大小（以宽字符表示）。  
  
 `dwLength`  
 [出]返回的缓冲区的长度（以字节为单位）。  
  
 `dwResolutionFlags`  
 [在] 值CLSID_RESOLUTION_FLAGS之一。 支持以下值：  
  
- CLSID_RESOLUTION_DEFAULT：（0x0）指定应使用默认互操作行为。  
  
- CLSID_RESOLUTION_REGISTERED：（0x1）指定应搜索注册表并应用 shim 策略。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|函数已成功返回。|  
|E_INVALIDARG|其中一个参数的类型或格式无效。|  
|ERROR_INSUFFICIENT_BUFFER|缓冲区`pVersion`不够大，无法容纳整个版本字符串。|  
|REGDB_E_CLASSNOTREG|没有在指定的`CLSID`中注册了类。|  
|E_POINTER|`dwLength`为 null，`cchBuffer`或足够大以容纳版本字符串，但`pVersion`为 null。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
