---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
ms.openlocfilehash: d37ec8e17e62f58212a5f79f4d6b6aa75f57bf7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120260"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>ICLRRuntimeInfo::BindAsLegacyV2Runtime 方法
绑定所有旧公共语言运行时（CLR）版本2激活策略决策的当前运行时。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 Hresult：  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|绑定成功，或已将此运行时绑定为旧版 CLR 版本2激活策略运行时。|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|已将其他运行时绑定到旧版 CLR 版本2激活策略。|  
  
## <a name="remarks"></a>备注  
 如果当前运行时已绑定到所有旧 CLR 版本2激活策略决策（例如，通过使用配置文件中[\<startup > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)上的 `useLegacyV2RuntimeActivationPolicy` 属性），则此方法不会返回错误结果;相反，结果是 S_OK，就如同方法成功绑定了旧激活策略一样。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRRuntimeInfo 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [\<startup> 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
