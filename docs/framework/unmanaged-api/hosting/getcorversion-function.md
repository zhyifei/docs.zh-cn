---
title: GetCORVersion 函数
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178192"
---
# <a name="getcorversion-function"></a>GetCORVersion 函数
返回当前进程中运行的通用语言运行时 （CLR） 的版本号。  
  
 此功能已在 .NET 框架 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>parameters  
 `pbuffer`  
 指向缓冲区的指针，其中 CLR 返回一个字符串，指定当前加载到进程的运行时的版本。 返回的字符串采用与传递给[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)的字符串相同的形式，例如"v1.0.1216"。 如果运行时尚未加载到进程中，该函数将返回计算机上安装的最新版本的运行时的相应目录信息。  
  
 `cchBuffer`  
 可在 中`pbuffer`持有的字符`WCHAR`数 。  
  
 `dwLength`  
 指向 中`pbuffer`实际返回的字符数的指针。 如果`pbuffer`为空指针，则运行时返回E_POINTER。 如果字符数大于，则`pbuffer`长度 为 ，运行时将返回ERROR_INSUFFICIENT_BUFFER。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
