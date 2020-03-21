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
ms.openlocfilehash: bdafacfe52d678aacfcd44de1e924bcb88547424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178209"
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory 函数
返回加载到进程中的通用语言运行时 （CLR） 的安装目录。 安装目录完全限定，例如，"c：_windows_microsoft.net_framework_v1.0.3705"。  
  
 不推荐使用此函数。 它被[ICLRRuntimeInfo 取代：获取](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md).NET 框架 4 中提供的 RuntimeDirectory 方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>parameters  
 `pbuffer`  
 [出]运行时返回一个字符串，其中包含加载到进程的运行时安装目录的完全限定名称。 如果运行时尚未加载到进程中，该函数将返回计算机上安装的最新版本的运行时的相应目录信息。  
  
 `cchBuffer`  
 [在]的大小（以字节为单位）的大小`pbuffer`。  
  
 `dwLength`  
 [出]中`pbuffer`返回的字符数。  
  
## <a name="remarks"></a>备注  
  
> [!CAUTION]
> 请勿在运行 CLR 版本 4 的进程中使用此功能。 如果计算机上安装了 CLR 的早期版本，则此功能将返回该版本的安装目录。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
