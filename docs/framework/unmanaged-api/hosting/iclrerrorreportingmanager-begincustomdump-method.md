---
title: ICLRErrorReportingManager::BeginCustomDump 方法
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98eebd489792f57f7f98d3596d4f25be2e847441
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966283"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a>ICLRErrorReportingManager::BeginCustomDump 方法
指定用于错误报告的自定义堆转储配置。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a>参数  
 `dwFlavor`  
 中一个[ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)值, 指示用于生成自定义堆转储的堆转储的种类。  
  
 `dwNumItems`  
 中`items`数组的长度。 如果`dwFlavor`不是 DUMP_FLAVOR_Mini, `dwNumItems`则应为零。  
  
 `items`  
 中[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)实例的数组, 指定要添加到小型转储中的项。 如果`dwFlavor`不是 DUMP_FLAVOR_Mini, `items`则应为 null。  
  
 `dwReserved`  
 中保留供将来使用。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|方法已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时, 该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 方法返回 E_FAIL 后, CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `BeginCustomDump`方法设置自定义堆转储配置。 [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)方法清除自定义堆转储配置并释放任何关联的状态。 应在自定义堆转储完成后调用它。  
  
> [!IMPORTANT]
> 调用`EndCustomDump`失败会导致内存泄露。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [CustomDumpItem 结构](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [ECustomDumpFlavor 枚举](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [ICLRErrorReportingManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
