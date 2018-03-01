---
title: "CorBindToCurrentRuntime 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0fed8829f8f14833724d1770273ff905d6f5eabf
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="corbindtocurrentruntime-function"></a>CorBindToCurrentRuntime 函数
通过使用版本信息存储在 XML 文件中，到的进程中加载公共语言运行时 (CLR)。 XML 文件的格式是标准的应用程序配置文件之后制定的。 有关配置文件的详细信息，请参阅[配置文件架构](../../../../docs/framework/configure-apps/file-schema/index.md)。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。 请参阅[公共语言运行时加载到进程中](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pwszFileName`  
 [in]指定要加载的 clr 版本的应用程序配置文件的名称。 如果不完全限定的文件名，则假定在进行调用的可执行文件所在的目录。  
  
 中的版本属性描述要加载的运行时版本[ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)配置文件元素。  
  
 如果没有指定版本，或如果`<requiredRuntime>`找不到元素，加载计算机安装的 CLR 的最新版本。  
  
 `rclsid`  
 [in]`CLSID`实现的组件类的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。 支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。  
  
 `riid`  
 [in]`IID`您请求的接口。 支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。  
  
 `ppv`  
 [out]返回的接口指针。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [CorBindToRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [CorBindToRuntimeByCfg 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [CorBindToRuntimeHost 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [ICorRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
