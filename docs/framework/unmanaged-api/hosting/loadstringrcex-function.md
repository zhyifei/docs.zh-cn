---
title: "LoadStringRCEx 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9b046387b5ae365ece694509b302f7ac3a7e066a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="loadstringrcex-function"></a>LoadStringRCEx 函数
将转换为相应的错误消息为指定的区域性的 HRESULT 值。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
#### <a name="parameters"></a>参数  
 `lcid`  
 [in]区域性标识符。 传递-1 `lcid` ，使用默认区域性。  
  
 `iResourceID`  
 [in]HRESULT。  
  
 `szBuffer`  
 [out]包含成功完成后的错误消息的缓冲区。  
  
 `iMax`  
 [in]错误消息缓冲区的大小。  
  
 `bQuiet`  
 [in]忽略。  
  
 `pcwchUsed`  
 [out]指向错误消息的长度的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回标准的 COM 错误代码，除了以下值中 WinError.h，定义。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|`szBuffer`为 null，或`iMax`为零 (0)。|  
  
## <a name="remarks"></a>备注  
 如果方法不成功，完成`szBuffer`包含一个空字符串。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>  
 [LoadStringRC 函数](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
