---
title: ICLRMetaHost::EnumerateInstalledRuntimes 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ed4c09d910db6fa2e61d44e4ac777f9b6095a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434276"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a>ICLRMetaHost::EnumerateInstalledRuntimes 方法
返回一个包含有效的枚举[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)每个版本的计算机安装公共语言运行时 (CLR) 的接口。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnumerator`  
 [out]枚举[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)对应于每个版本的计算机安装的 CLR 的接口。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_POINTER|`ppEnumerator` 为 null。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRMetaHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
