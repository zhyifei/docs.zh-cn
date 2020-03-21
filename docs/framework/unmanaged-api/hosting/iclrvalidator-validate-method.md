---
title: ICLRValidator::Validate 方法
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
ms.openlocfilehash: 427895ffea94e6c657d775ebdeb8571070a61c6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178063"
---
# <a name="iclrvalidatorvalidate-method"></a>ICLRValidator::Validate 方法
验证指定文件中的可移植可执行 （PE） 或 Microsoft 中间语言 （MSIL）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);
```  
  
## <a name="parameters"></a>parameters  
 `veh`  
 [在]指向处理验证错误的`IVEHandler`实例的指针。  
  
 `ulAppDomainId`  
 [在]当前<xref:System.AppDomain>的标识符。  
  
 `ulFlags`  
 [在][验证器标志](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)值的组合，指示应执行的验证类型。  
  
 `ulMaxError`  
 [在]退出验证之前要允许的最大错误数。  
  
 `token`  
 [在]闲置。  
  
 `fileName`  
 [在]要验证的文件的名称。  
  
 `pe`  
 [在]指向文件缓冲区的指针。  
  
 `ulSize`  
 [在]要验证的文件的大小（以字节为单位）。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|`Validate`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 （CLR） 尚未加载到进程中，或者 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|呼叫超时。|  
|HOST_E_NOT_OWNER|调用方不拥有锁。|  
|HOST_E_ABANDONED|当阻塞的线程或光纤等待事件时，事件已被取消。|  
|E_FAIL|发生了未知的灾难性故障。 当方法返回E_FAIL时，CLR 在进程中不再可用。 对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** I 验证器.idl， I 验证器.h  
  
 **库：** 作为资源包含在 MSCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRValidator 接口](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
