---
title: ICorRuntimeHost::GetConfiguration 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b10ec088f087c45b8a75805e326bc543bb64b3d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665079"
---
# <a name="icorruntimehostgetconfiguration-method"></a>ICorRuntimeHost::GetConfiguration 方法
获取允许指定公共语言运行时 (CLR) 的回调配置主机的对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pConfiguration`  
 [out]指向的地址的指针[ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)可以用于配置 CLR 对象。  
  
## <a name="remarks"></a>备注  
 CLR 必须在其初始化; 之前配置否则为`GetConfiguration`方法返回一个 HRESULT，指示错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 包含为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** 1.0, 1.1  
  
## <a name="see-also"></a>请参阅
- [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
