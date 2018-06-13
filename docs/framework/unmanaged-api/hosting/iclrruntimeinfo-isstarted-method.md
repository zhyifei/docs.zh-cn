---
title: ICLRRuntimeInfo::IsStarted 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8934a2a51ea4bc86166bf99a6087124d03ab11d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434111"
---
# <a name="iclrruntimeinfoisstarted-method"></a>ICLRRuntimeInfo::IsStarted 方法
该值指示是否已启动运行时 (即，是否[iclrruntimehost:: Start 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)已调用并已成功)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
#### <a name="parameters"></a>参数  
 `pbStarted`  
 [out]`true`此运行时是否已启动; 否则为`false`。  
  
 `pdwStartupFlags`  
 [out]返回用来启动运行时的标志。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_NOTIMPL|公共语言运行时 (CLR) 版本低于中的 CLR 版本[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。|  
  
## <a name="remarks"></a>备注  
 此方法不起使用 CLR 版本早于中的 CLR 版本[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRRuntimeInfo 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
