---
title: "LoadStringRC 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadStringRC
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: LoadStringRC
helpviewer_keywords: LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fd42a576e1315ea029f98b94d8dc84d2b92b5e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="loadstringrc-function"></a>LoadStringRC 函数
将 HRESULT 值转换为一条错误消息中，通过使用当前线程的默认区域性。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
#### <a name="parameters"></a>参数  
 `iResourceID`  
 [in]HRESULT。  
  
 `szBuffer`  
 [out]包含成功完成后的错误消息的缓冲区。  
  
 `iMax`  
 [in]错误消息缓冲区的大小。  
  
 `bQuiet`  
 [in]忽略。  
  
## <a name="return-value"></a>返回值  
 此方法返回标准的组件对象模型 (COM) 错误代码，除了以下值中 WinError.h，定义。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|`szBuffer`为 null 或`iMax`为零 (0)。|  
  
## <a name="remarks"></a>备注  
 如果方法不成功，完成`szBuffer`包含一个空字符串。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll 和 Mscorwks.dll。 使用而不是 Mscorwks.dll MSCorEE.dll 来确保面向.NET Framework 的正确版本。  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [LoadStringRCEx 函数](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
