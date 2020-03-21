---
title: LoadStringRC 函数
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 56ae7b7cf3b577bfe41ebd0bdd98e0da68047b44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176235"
---
# <a name="loadstringrc-function"></a>LoadStringRC 函数
使用当前线程的默认区域性将 HRESULT 值转换为错误消息。  
  
 此功能已在 .NET 框架 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a>parameters  
 `iResourceID`  
 [在]A HRESULT。  
  
 `szBuffer`  
 [出]成功完成后包含错误消息的缓冲区。  
  
 `iMax`  
 [在]错误消息缓冲区的大小。  
  
 `bQuiet`  
 [在]忽视。  
  
## <a name="return-value"></a>返回值  
 此方法返回 WinError.h 中定义的标准组件对象模型 （COM） 错误代码，以及以下值。  
  
|返回代码|说明|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|`szBuffer`为空或`iMax`为零 （0）。|  
  
## <a name="remarks"></a>备注  
 如果方法未成功完成，`szBuffer`则包含一个空字符串。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** MSCorE.dll 和 Mscorwks.dll. 使用 MSCorEE.dll 而不是 mscorwks.dll 来确保针对 .NET 框架的正确版本。  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [LoadStringRCEx 函数](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
