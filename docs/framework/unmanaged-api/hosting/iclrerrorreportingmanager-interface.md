---
title: ICLRErrorReportingManager 接口
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf9e04ed1d3a68fed120c4c13ad992af1f777244
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433791"
---
# <a name="iclrerrorreportingmanager-interface"></a>ICLRErrorReportingManager 接口
提供使该主机可配置的错误报告的自定义堆栈转储的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[BeginCustomDump 方法](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|指定的错误报告的自定义堆栈转储的配置。|  
|[EndCustomDump 方法](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|清除以前调用所设置的自定义堆栈转储配置`BeginCustomDump`。|  
|[GetBucketParametersForCurrentException 方法](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|获取在调用线程上的当前异常的 Watson bucket。|  
  
## <a name="remarks"></a>备注  
 `BeginCustomDump`方法设置自定义堆栈转储配置。 `EndCustomDump`方法清除自定义堆栈转储配置并释放任何关联的状态。 自定义转储完成之后才调用它。  
  
> [!IMPORTANT]
>  调用失败`EndCustomDump`导致内存泄漏。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ECustomDumpItemKind 枚举](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
