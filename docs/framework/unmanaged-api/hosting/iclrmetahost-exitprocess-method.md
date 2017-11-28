---
title: "ICLRMetaHost::ExitProcess 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.ExitProcess
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10fb9bef99a90a76ea5bb1f4abe73cd756717285
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostexitprocess-method"></a>ICLRMetaHost::ExitProcess 方法
尝试正常关闭所有已加载的运行时，然后终止该进程。 取代[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a>参数  
 `iExitCode`  
 [in]进程的退出代码。  
  
## <a name="return-value"></a>返回值  
 永远不会返回此方法，以便其返回值是不确定。  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRMetaHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
