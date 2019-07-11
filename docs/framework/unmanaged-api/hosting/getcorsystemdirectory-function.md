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
ms.openlocfilehash: deec4d40270a11b9e48a0ab39504d774314c077c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736184"
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory 函数
返回加载到进程的公共语言运行时 (CLR) 的安装目录。 安装目录是完全限定，例如，"c:\windows\microsoft.net\framework\v1.0.3705"。  
  
 此函数已弃用。 被取代[iclrruntimeinfo:: Getruntimedirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) .NET Framework 4 中提供的方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a>参数  
 `pbuffer`  
 [out]在缓冲区中运行时返回一个字符串，包含要加载到进程的运行时安装目录的完全限定的名称。 如果尚未在流程中加载运行时，函数将返回在计算机上安装的运行时的最新版本的相应的目录信息。  
  
 `cchBuffer`  
 [in]大小，以字节为单位的`pbuffer`。  
  
 `dwLength`  
 [out]在中返回的字符数`pbuffer`。  
  
## <a name="remarks"></a>备注  
  
> [!CAUTION]
>  在运行版本 4 的 CLR 的进程中不使用此函数。 如果在计算机上安装早期版本的 CLR，则此函数将返回该版本的安装目录。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
