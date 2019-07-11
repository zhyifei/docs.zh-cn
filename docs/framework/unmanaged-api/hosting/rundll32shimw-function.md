---
title: RunDll32ShimW 函数
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 569efa9d14ef10d8c5cf735091778a6c78882815
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781165"
---
# <a name="rundll32shimw-function"></a>RunDll32ShimW 函数
执行指定的命令。  
  
 .NET Framework 4 中已弃用此函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a>参数  
 `hwnd`  
 [in]将在其中显示命令输出窗口的句柄。  
  
 `hinst`  
 [in]包含该命令的库句柄。  
  
 `lpszCmdLine`  
 [in]一个字符串，指定要执行的命令。  
  
 `nCmdShow`  
 [in]一个整数，指定的输出窗口的显示模式。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
