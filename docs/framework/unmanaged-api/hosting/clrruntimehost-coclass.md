---
title: "CLRRuntimeHost 组件类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CLRRuntimeHost
helpviewer_keywords: CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 372b2466baaa76ba47a6710447d93f9fa6bb967f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="clrruntimehost-coclass"></a>CLRRuntimeHost 组件类
用于管理代码执行的运行时提供的接口。  
  
## <a name="syntax"></a>语法  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a>接口  
  
|接口|描述|  
|---------------|-----------------|  
|[ICLRRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|提供由运行时控制应用程序的执行的方法。|  
|[ICLRValidator 接口](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|提供一些方法的可移植可执行映像的验证和验证错误的详细报告。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.idl  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [承载组件类](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
