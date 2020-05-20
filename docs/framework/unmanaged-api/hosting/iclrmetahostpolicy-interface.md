---
title: ICLRMetaHostPolicy 接口
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 79b62a5e2aad9cfcd14ba40c1abf0342bfe57a4b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703528"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy 接口
提供[GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md)方法，该方法根据策略条件、托管程序集、版本和配置文件返回指向公共语言运行时（CLR）接口的指针。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetRequestedRuntime 方法](iclrmetahostpolicy-getrequestedruntime-method.md)|提供基于策略标准、托管程序集、版本和配置文件的首选 CLR 接口。|  
  
## <a name="remarks"></a>备注  
 可以通过调用[CLRCreateInstance](clrcreateinstance-function.md)函数获取对此接口的引用，如以下代码所示：  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> 此接口实际上不会加载或激活 CLR，只是根据安装或加载的可用版本返回首选 CLR 版本。  
  
 .NET Framework 4 托管 API 合并了策略，因此具有特定需求的主机可以使用基本功能，而不会产生意外的处罚。 例如，许多 Mscoree.dll 导出将绑定到特定的 CLR，不过，方法可能不会在逻辑上要求它。 [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md)枚举提供大部分主机所共有的绑定策略。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [.NET Framework 4 和 4.5 中添加的 CLR 承载接口](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [承载接口](hosting-interfaces.md)
- [承载](index.md)
