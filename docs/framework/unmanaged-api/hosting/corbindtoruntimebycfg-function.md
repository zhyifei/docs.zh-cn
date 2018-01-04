---
title: "CorBindToRuntimeByCfg 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntimeByCfg
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CorBindToRuntimeByCfg
helpviewer_keywords: CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2dccd777ef20f68d091cfdd7939c57a1f8d42ad5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntimebycfg-function"></a>CorBindToRuntimeByCfg 函数
通过使用版本信息从 XML 文件读取到的进程中加载公共语言运行时 (CLR)。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pCfgStream`  
 [in]指向的指针`IStream`读取 XML 文件的对象。  
  
 `reserved`  
 [in]留待将来使用。 使用作为值 0 （零）。  
  
 `startupFlags`  
 [in]值为[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)指定 CLR 的启动行为的枚举。  
  
 `rclsid`  
 [in]`CLSID`实现的组件类的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。 支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。  
  
 `riid`  
 [in]`IID`任一`ICorRuntimeHost`或`ICLRRuntimeHost`接口。 支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。  
  
 `ppv`  
 [out]指向的地址返回的接口的指针。  
  
## <a name="remarks"></a>备注  
 XML 文件的格式是标准的应用程序配置文件之后制定的。 有关 XML 文件的详细信息，请参阅[配置文件架构](../../../../docs/framework/configure-apps/file-schema/index.md)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [CorBindToRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [CorBindToRuntimeHost 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
