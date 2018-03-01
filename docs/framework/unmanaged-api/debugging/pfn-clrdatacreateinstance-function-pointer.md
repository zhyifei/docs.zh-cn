---
title: "PFN_CLRDataCreateInstance 函数指针"
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
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 98a966434332549d9ceb7f29de81e19fa1b2108f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a>PFN_CLRDataCreateInstance 函数指针
指向一个函数来创建一个接口对象，用于指定的目标项。  
  
## <a name="syntax"></a>语法  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a>参数  
 `iid`  
 [in]要进行实例化的接口标识符。  
  
 `target`  
 [in]指向用户实现[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)表示要为其创建接口对象的目标项的对象。  
  
 `iface`  
 [out]指向返回的接口对象的地址的指针。  
  
## <a name="remarks"></a>备注  
 `ICLRDataTarget`对象由调试应用程序编写器实现。 实现取决于所表示的目标项的类型。 目标项可能进程、 内存转储，远程计算机和等等。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** ClrData.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试全局静态函数](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
