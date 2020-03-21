---
title: LoadStringRCEx 函数
ms.date: 03/30/2017
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
ms.openlocfilehash: a300c2679ef11a84edb2ab89c8dea96e445c9ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177986"
---
# <a name="loadstringrcex-function"></a>LoadStringRCEx 函数
将 HRESULT 值转换为指定区域性的相应错误消息。  
  
 此功能已在 .NET 框架 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a>parameters  
 `lcid`  
 [在]区域性标识符。 通过 -1`lcid`用于使用默认区域性。  
  
 `iResourceID`  
 [在]A HRESULT。  
  
 `szBuffer`  
 [出]成功完成后包含错误消息的缓冲区。  
  
 `iMax`  
 [在]错误消息缓冲区的大小。  
  
 `bQuiet`  
 [在]忽视。  
  
 `pcwchUsed`  
 [出]指向错误消息长度的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回 WinError.h 中定义的标准 COM 错误代码，以及以下值。  
  
|返回代码|说明|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|`szBuffer`为空或`iMax`为零 （0）。|  
  
## <a name="remarks"></a>备注  
 如果方法未成功完成，`szBuffer`则包含一个空字符串。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [LoadStringRC 函数](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
