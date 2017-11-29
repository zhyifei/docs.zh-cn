---
title: "ICLRDebuggingLibraryProvider::ProvideLibrary 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3a34579787e976022ffa8caf7c29d8a565a7c73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>ICLRDebuggingLibraryProvider::ProvideLibrary 方法
获取一个库提供程序允许公共语言运行时 (CLR) 特定于版本的调试库需要定位和加载上的回调接口。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
#### <a name="parameters"></a>参数  
 `pwszFilename`  
 [in]请求的模块的名称。  
  
 `dwTimestamp`  
 [in]COFF 文件头的 PE 文件中存储日期时间戳。  
  
 `pLibraryProvider`  
 [in]`SizeOfImage` COFF 可选文件头的 PE 文件中存储的字段。  
  
 `hModule`  
 [out]请求的模块句柄。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 `ProvideLibrary`使调试器能够提供所需的调试特定 CLR 文件，如 mscordbi.dll 和 mscordacwks.dll 的模块。 模块句柄已保留，直到调用有效[iclrdebugging:: Canunloadnow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)方法指示它们可能会被释放，此时它是调用方负责释放句柄。  
  
 调试器可以使用任何可用的方式来定位或获得调试模块。  
  
> [!IMPORTANT]
>  此功能允许 API 调用方提供包含可执行文件，并可能是恶意代码的模块。 作为安全措施，调用方不应使用`ProvideLibrary`来分发不愿意本身执行任何代码。  
>   
>  如果在已发布的库中，如 mscordbi.dll 或 mscordacwks.dll，发现了严重的安全问题填充程序可以进行修补，以识别错误版本的文件。 然后，填充程序可以发出修补版本的文件的请求并拒绝不适用的版本，如果对任何请求响应中提供。 仅当用户具有修补到该填充程序的新版本时，才会出现此问题。 未安装修补程序的版本仍易受攻击。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
