---
title: ICorRuntimeHost::Stop 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca51b87e7afc8e9e48d541a32b3bd60a19a5ff70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965968"
---
# <a name="icorruntimehoststop-method"></a>ICorRuntimeHost::Stop 方法
停止执行当前进程的运行时中的代码。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|操作成功。|  
|S_FALSE|操作未能完成。|  
|E_FAIL|发生了未知的灾难性故障。 如果某个方法返回 E_FAIL, 则公共语言运行时 (CLR) 在该过程中将不再可用。 对任何托管 Api 的后续调用都将返回 HOST_E_CLRNOTAVAILABLE。|  
|HOST_E_CLRNOTAVAILABLE|CLR 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
  
## <a name="remarks"></a>备注  
 通常不需要调用`Stop`方法, 因为在进程退出时代码将停止执行。  
  
> [!NOTE]
> 调用`Stop`后, 无法将 CLR 重新初始化为同一进程。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本:** 1.0、1。1  
  
## <a name="see-also"></a>请参阅

- [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
