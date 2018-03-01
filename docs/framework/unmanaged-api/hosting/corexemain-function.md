---
title: "_CorExeMain 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f5c0909db10c7bf8e15a7af998b78e0a193a908
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corexemain-function"></a>_CorExeMain 函数
初始化公共语言运行时 (CLR)，查找可执行程序集的 CLR 标头中的托管的入口点并开始执行。  
  
## <a name="syntax"></a>语法  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>备注  
 从托管的可执行程序集创建的进程中加载程序调用此函数。 对于 DLL 程序集，加载程序调用[_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)函数。  
  
 操作系统加载程序调用此方法而不考虑图像文件中指定的入口点。  
  
 在 Windows 98、 Windows ME、 Windows NT 和 Windows 2000`_CorExeMain`通过操作系统加载程序在修正间接调用函数。 在所有其他版本的 Windows，它是直接由操作系统加载程序进行调用。  
  
 有关其他信息，请参阅备注部分中的[_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)主题。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
