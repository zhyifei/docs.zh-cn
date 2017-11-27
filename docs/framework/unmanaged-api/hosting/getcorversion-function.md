---
title: "GetCORVersion 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetCORVersion
helpviewer_keywords: GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6218714030892531f3b9ed4b4a79917347d250db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="getcorversion-function"></a>GetCORVersion 函数
返回在当前进程中运行公共语言运行时 (CLR) 的版本号。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a>参数  
 `pbuffer`  
 指向在 CLR 返回一个字符串，指定当前加载到进程的运行时版本的缓冲区的指针。 返回的字符串将相同的形式作为字符串传递给[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)，例如，"v1.0.1216"。 如果尚未到过程加载运行时，函数将返回在计算机上安装的运行时的最新版本的相应目录信息。  
  
 `cchBuffer`  
 字符数 (`WCHAR`s)，可以保存在`pbuffer`。  
  
 `dwLength`  
 指向中实际返回的字符数的指针`pbuffer`。 如果`pbuffer`是 null 指针，则运行时返回 E_POINTER。 如果字符数大于然后的长度`pbuffer`，则运行时返回 ERROR_INSUFFICIENT_BUFFER。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
