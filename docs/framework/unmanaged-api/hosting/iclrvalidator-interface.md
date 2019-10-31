---
title: ICLRValidator 接口
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: 483d647028d1a05ea20ab836730099afe3e09374
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127850"
---
# <a name="iclrvalidator-interface"></a>ICLRValidator 接口
提供用于验证可移植可执行（PE）映像和报告验证错误的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[FormatEventInfo 方法](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-formateventinfo-method.md)|获取有关指定验证错误的详细消息。|  
|[Validate 方法](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)|验证指定文件中的可移植可执行文件或 Microsoft 中间语言（MSIL）。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** IValidator，IValidator  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRErrorReportingManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CLRRuntimeHost 组件类](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
