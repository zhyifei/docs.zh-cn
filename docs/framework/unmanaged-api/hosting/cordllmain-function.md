---
title: _CorDllMain 函数
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5d541f834e829305fa2b091c45d0dc8f387bb55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431664"
---
# <a name="cordllmain-function"></a>_CorDllMain 函数
初始化公共语言运行时 (CLR)、 查找托管的入口点 DLL 程序集的 CLR 头中，并开始执行。  
  
## <a name="syntax"></a>语法  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a>参数  
 `hInst`  
 [in]加载的模块的实例句柄。  
  
 `dwReason`  
 [in]指示调用的 DLL 入口点函数。 此参数可以是以下值之一： DLL_PROCESS_ATTACH、 DLL_THREAD_ATTACH、 DLL_THREAD_ATTACH 或 DLL_PROCESS_DETACH。 有关这些值的说明，请参阅`DllMain`平台 SDK 中的文档。  
  
 `lpReserved`  
 [in]未使用。  
  
## <a name="return-value"></a>返回值  
 此方法返回`true`成功和`false`如果发生错误。  
  
## <a name="remarks"></a>备注  
 为 DLL 程序集，操作系统加载程序调用此函数。 对于可执行程序集，加载程序调用[_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)函数。  
  
 操作系统加载程序调用此方法而不考虑 DLL 文件中指定的入口点。  
  
 在 Windows 98、 Windows ME、 Windows NT 和 Windows 2000`_CorDllMain`通过调用函数间接 fixupin 操作系统加载程序。 在所有其他版本的 Windows，它是直接由操作系统加载程序进行调用。  
  
 有关其他信息，请参阅备注部分中的[_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)主题。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
