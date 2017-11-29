---
title: "CorRuntimeHost 组件类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRuntimeHost
helpviewer_keywords: CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3d7a272aff3a3c7d32042b76d37fdb15c9dcad4d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corruntimehost-coclass"></a>CorRuntimeHost 组件类
提供用于管理正由公共语言运行时执行的应用程序的接口。  
  
## <a name="syntax"></a>语法  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a>接口  
  
|接口|描述|  
|---------------|-----------------|  
|[ICorConfiguration 接口](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|提供用于配置公共语言运行时 (CLR) 方法。|  
|[ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|提供使主机能够显式启动和停止公共语言运行时，创建和配置应用程序域，以访问默认域，以及枚举进程中运行的所有域的方法。|  
|[IDebuggerInfo 接口](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|提供用于获取有关调试服务的状态信息的方法。|  
|[IGCHost 接口](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|提供用于获取有关垃圾回收系统的信息以及控制垃圾回收的某些方面的方法。|  
|"IValidator"|提供用于验证和验证错误的详细报告的可移植可执行映像的方法。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.idl  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [承载组件类](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
