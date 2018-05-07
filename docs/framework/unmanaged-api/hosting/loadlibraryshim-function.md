---
title: LoadLibraryShim 函数
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8936fa3d22cfde4c2536fccf9d46c1990133db1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="loadlibraryshim-function"></a>LoadLibraryShim 函数
加载的 dll 的.NET Framework 可再发行组件包中包含的指定的版本。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。 使用[iclrruntimeinfo:: Loadlibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szDllName`  
 [in]表示要从.NET Framework 库加载的 DLL 的名称以零结尾的字符串。  
  
 `szVersion`  
 [in]表示要加载的 dll 版本以零结尾的字符串。 如果`szVersion`是 null，选择加载为指定的 DLL 小于版本 4 的最新版本的版本。 也就是说，将忽略所有版本等于或大于版本 4，如果`szVersion`为 null，并且如果不安装任何版本低于版本 4，则无法加载 DLL。 这是为了确保该安装[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]不会影响现有应用程序或组件。 请参阅文章[进程内 SxS 和迁移快速启动](http://go.microsoft.com/fwlink/?LinkId=200329)CLR 团队博客中。  
  
 `pvReserved`  
 留待将来使用。  
  
 `phModDll`  
 [out]指向模块的句柄的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回标准的组件对象模型 (COM) 错误代码，除了以下值中 WinError.h，定义。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|CLR_E_SHIM_RUNTIMELOAD|加载`szDllName`需要的加载无法加载公共语言运行时 (CLR) 和 CLR 的必要版本。|  
  
## <a name="remarks"></a>备注  
 此函数用于加载.NET Framework 可再发行组件包中包含的 Dll。 它将不加载用户生成的 Dll。  
  
> [!NOTE]
>  从.NET Framework 2.0 版开始，将加载为 Fusion.dll 导致要加载的 CLR。 这是因为在为 Fusion.dll 函数现在是由运行时提供其实现的包装器。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
