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
ms.openlocfilehash: 11bb220068e978dc130701e3b28ab3f421be7337
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937656"
---
# <a name="loadlibraryshim-function"></a>LoadLibraryShim 函数
加载 .NET Framework 可再发行组件包中包含的 DLL 的指定版本。  
  
 此函数已在 .NET Framework 4 中弃用。 改为使用[ICLRRuntimeInfo：： LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a>参数  
 `szDllName`  
 中以零结尾的字符串，表示要从 .NET Framework 库中加载的 DLL 的名称。  
  
 `szVersion`  
 中以零结尾的字符串，表示要加载的 DLL 的版本。 如果 `szVersion` 为 null，则为加载选择的版本是最新版本的指定 DLL （低于版本4）。 也就是说，如果 `szVersion` 为空，则将忽略等于或大于版本4的所有版本，如果安装的版本低于版本4，则无法加载 DLL。 这是为了确保 .NET Framework 4 的安装不会影响预先存在的应用程序或组件。 请参阅 CLR 团队博客中的 "[进程内 SxS 和迁移快速入门](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/)条目。  
  
 `pvReserved`  
 留待将来使用。  
  
 `phModDll`  
 弄指向模块的句柄的指针。  
  
## <a name="return-value"></a>返回值  
 除以下值外，此方法还返回 Winerror.h 中定义的标准组件对象模型（COM）错误代码。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法成功完成。|  
|CLR_E_SHIM_RUNTIMELOAD|加载 `szDllName` 需要加载公共语言运行时（CLR），并且无法加载 CLR 的必要版本。|  
  
## <a name="remarks"></a>备注  
 此函数用于加载 .NET Framework 可再发行组件包中包含的 Dll。 它不会加载用户生成的 Dll。  
  
> [!NOTE]
> 从 .NET Framework 版本2.0 开始，加载合成 .dll 会导致加载 CLR。 这是因为，合成 .dll 中的函数现在是由运行时提供其实现的包装器。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
