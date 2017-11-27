---
title: "GetRequestedRuntimeVersionForCLSID 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersionForCLSID
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersionForCLSID
helpviewer_keywords: GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a5b9e4b186b6c9b91c1182e8700268f0e1c038f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID 函数
获取适当的公共语言运行时 (CLR) 版本信息，使用指定的类`CLSID`。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `rclsid`  
 [in] `CLSID`的组件。  
  
 `pVersion`  
 [out] 包含成功完成后的版本号字符串的缓冲区。  
  
 `cchBuffer`  
 [in] 大小，以宽字符为单位的`pVersion`缓冲区。  
  
 `dwLength`  
 [out]返回的缓冲区长度 （字节）。  
  
 `dwResolutionFlags`  
 [in] CLSID_RESOLUTION_FLAGS 值之一。 支持以下值：  
  
-   CLSID_RESOLUTION_DEFAULT: (0x0) 该默认互操作行为指定应使用。  
  
-   CLSID_RESOLUTION_REGISTERED: (0x1) 指定注册表应搜索并填充策略应为应用。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该函数成功返回。|  
|E_INVALIDARG|其中一个参数具有无效的类型或格式。|  
|ERROR_INSUFFICIENT_BUFFER|`pVersion`的缓冲区不可足以容纳完整版本字符串。|  
|REGDB_E_CLASSNOTREG|没有注册使用指定的类`CLSID`。|  
|E_POINTER|`dwLength`为 null，或`cchBuffer`足够大，能够容纳的版本字符串，但`pVersion`为 null。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
