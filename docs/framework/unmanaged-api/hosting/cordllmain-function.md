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
ms.openlocfilehash: f60f159ab4770023cee7123b39109040243e1ccd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136968"
---
# <a name="_cordllmain-function"></a>\_CorDllMain 函数

初始化公共语言运行时（CLR），定位 DLL 程序集的 CLR 头中的托管入口点，然后开始执行。  
  
## <a name="syntax"></a>语法  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>参数  
 `hInst`  
 中加载的模块的实例句柄。  
  
 `dwReason`  
 中指示调用 DLL 入口点函数的原因。 此参数可以是下列值之一： DLL\_PROCESS_ATTACH、DLL\_线程\_ATTACH、DLL\_线程\_ATTACH 或 DLL\_进程\_分离。 有关这些值的说明，请参阅 Platform SDK 中的 `DllMain` 文档。  
  
 `lpReserved`  
 中用.  
  
## <a name="return-value"></a>返回值  
 如果发生错误，此方法将返回成功 `true`，并 `false`。  
  
## <a name="remarks"></a>备注  
 此函数由 DLL 程序集的操作系统加载程序调用。 对于可执行程序集，加载程序将改为调用[\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)函数。  
  
 操作系统加载程序将调用此方法，而不考虑 DLL 文件中指定的入口点。  
  
`_CorDllMain` 函数是由操作系统加载程序直接调用的。
  
 有关其他信息，请参阅[\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)主题中的 "备注" 部分。  
  
## <a name="requirements"></a>要求  

 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
