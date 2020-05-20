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
ms.openlocfilehash: 23d68e8e4bbd87779e3b49f0c40f5a5ab9f5124f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617212"
---
# <a name="getcorversion-function"></a>GetCORVersion 函数
返回当前进程中运行的公共语言运行时（CLR）的版本号。  
  
 此函数已在 .NET Framework 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>参数  
 `pbuffer`  
 指向缓冲区的指针，CLR 在此缓冲区中返回一个字符串，该字符串指定当前加载到进程中的运行时版本。 返回的字符串采用与传递到[CorBindToRuntimeEx](corbindtoruntimeex-function.md)的字符串相同的形式，例如 "v 1.0.1216"。 如果运行时尚未加载到进程中，则该函数将为计算机上安装的最新版本的运行时返回相应的目录信息。  
  
 `cchBuffer`  
 可保留的字符数 `WCHAR` `pbuffer` 。  
  
 `dwLength`  
 一个指针，指向中实际返回的字符数 `pbuffer` 。 如果 `pbuffer` 为 null 指针，则运行时返回 E_POINTER。 如果字符数超过了的长度 `pbuffer` ，则运行时返回 ERROR_INSUFFICIENT_BUFFER。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](deprecated-clr-hosting-functions.md)
