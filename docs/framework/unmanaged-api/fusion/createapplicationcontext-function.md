---
title: "CreateApplicationContext 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateApplicationContext
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateApplicationContext
helpviewer_keywords: CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89c3181a157ce5162d93d1df14641b393fb3082d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="createapplicationcontext-function"></a>CreateApplicationContext 函数
此函数支持的.NET Framework 基础结构，不宜在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
#### <a name="parameters"></a>参数  
 `pName`  
 [in]指向一个友好名称的指针。  
  
 `ppCtx`  
 [out]指向应用程序上下文的指针。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **库：**作为中为 Fusion.dll 资源包括  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IAssemblyCache 接口](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [合成全局静态函数](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [全局程序集缓存](../../../../docs/framework/app-domains/gac.md)
