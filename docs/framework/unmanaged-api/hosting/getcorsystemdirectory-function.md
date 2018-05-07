---
title: GetCORSystemDirectory 函数
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 008514e3637a980f3722d0c9896a17be33d54c31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory 函数
返回加载到进程公共语言运行时 (CLR) 的安装目录。 安装目录是完全限定，例如，"c:\windows\microsoft.net\framework\v1.0.3705"。  
  
 此函数已弃用。 它已被取代[iclrruntimeinfo:: Getruntimedirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)中提供的方法[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a>参数  
 `pbuffer`  
 [out]在运行时用于返回包含加载到进程的运行时安装目录的完全限定的名称的字符串缓冲区。 如果尚未到过程加载运行时，函数将返回在计算机上安装的运行时的最新版本的相应目录信息。  
  
 `cchBuffer`  
 [in]大小，以字节为单位的`pbuffer`。  
  
 `dwLength`  
 [out]在中返回的字符数`pbuffer`。  
  
## <a name="remarks"></a>备注  
  
> [!CAUTION]
>  不要在运行版本 4 的 CLR 的进程中使用此函数。 如果在计算机上安装的 CLR 早期版本，此函数将返回该版本的安装目录。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
