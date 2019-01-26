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
ms.openlocfilehash: f62ad2c9ec6e1c9672ac5c78e838e926b02359f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512367"
---
# <a name="cordllmain-function"></a>_CorDllMain 函数
初始化公共语言运行时 (CLR) 中，查找托管的入口点 DLL 程序集 CLR 头中，并开始执行。  
  
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
 [in]已加载的模块实例句柄。  
  
 `dwReason`  
 [in]指示调用 DLL 入口点函数。 此参数可以是下列值之一：DLL_PROCESS_ATTACH、 DLL_THREAD_ATTACH、 DLL_THREAD_ATTACH 或 DLL_PROCESS_DETACH。 有关这些值的说明，请参阅`DllMain`Platform SDK 中的文档。  
  
 `lpReserved`  
 [in]未使用。  
  
## <a name="return-value"></a>返回值  
 此方法返回`true`成功和`false`如果发生错误。  
  
## <a name="remarks"></a>备注  
 DLL 程序集由操作系统加载程序调用此函数。 对于可执行程序集，加载程序将调用[_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)函数。  
  
 操作系统加载程序调用此方法而不考虑 DLL 文件中指定的入口点。  
  
 在 Windows 98、 Windows ME、 Windows NT 和 Windows 2000`_CorDllMain`函数间接通过调用 fixupin 操作系统加载程序。 在所有其他版本的 Windows，它是由操作系统加载程序直接进行调用。  
  
 有关其他信息，请参阅中的备注部分[_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)主题。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 包含为 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
