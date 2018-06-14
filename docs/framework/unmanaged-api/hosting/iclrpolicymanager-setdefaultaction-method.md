---
title: ICLRPolicyManager::SetDefaultAction 方法
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a183c7491ad5d67bc2c68edba3ef2d54839da12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435445"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a>ICLRPolicyManager::SetDefaultAction 方法
指定公共语言运行时 (CLR) 指定的操作发生时应执行的策略操作。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a>参数  
 `operation`  
 [in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，指示应为哪些 CLR 自定义行为的操作。  
  
 `action`  
 [in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，指示时，应采取的策略措施 CLR`operation`时发生。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`SetDefaultAction` 已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 方法返回 E_FAIL 后，CLR 不再进程内中使用。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_INVALIDARG|无效`action`为指定`operation`，或为提供的无效值`operation`。|  
  
## <a name="remarks"></a>备注  
 并非所有策略操作值可以都指定为 CLR 操作的默认行为。 `SetDefaultAction` 可以通常仅用于提升行为。 例如，主机可以指定线程中止转变为强制线程终止，但不能指定相反。 下表描述了有效`action`对每个可能的值`operation`值。  
  
|值 `operation`|有效值为 `action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadAbort|-eAbortThread<br />-eRudeAbortThread<br />-eUnloadAppDomain<br />-eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />-eDisableRuntime|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|-eRudeAbortThread<br />-eUnloadAppDomain<br />-eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />-eDisableRuntime|  
|OPR_AppDomainUnload|-eUnloadAppDomain<br />-eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />-eDisableRuntime|  
|OPR_AppDomainRudeUnload|-eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />-eDisableRuntime|  
|OPR_ProcessExit|-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />-eDisableRuntime|  
|OPR_FinalizerRun|-eNoAction<br />-eAbortThread<br />-eRudeAbortThread<br />-eUnloadAppDomain<br />-eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />-eDisableRuntime|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [EClrOperation 枚举](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [EPolicyAction 枚举](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [ICLRPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
