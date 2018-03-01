---
title: "LockClrVersion 函数"
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
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a58d7e99f545026f6f133901ef35a1f9b9fabc7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="lockclrversion-function"></a>LockClrVersion 函数
允许宿主确定在进行显式初始化 CLR 之前将在过程内使用的公共语言运行时 (CLR) 的版本。  
  
 此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a>参数  
 `hostCallback`  
 [in]要由 CLR 初始化时调用的函数。  
  
 `pBeginHostSetup`  
 [in]正在启动要宿主调用以通知 CLR 初始化的函数。  
  
 `pEndHostSetup`  
 [in]要初始化由要通知的 CLR 的主机调用的函数已完成。  
  
## <a name="return-value"></a>返回值  
 此方法返回标准的 COM 错误代码，除了以下值中 WinError.h，定义。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|一个或多个参数为 null。|  
  
## <a name="remarks"></a>备注  
 宿主调用`LockClrVersion`之前初始化 CLR。 `LockClrVersion`采用三个参数，这些全部都是类型的回调[FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)。 此类型定义，如下所示。  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 在运行时初始化时将执行以下步骤：  
  
1.  宿主调用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或其他运行时初始化函数之一。 或者，主机无法初始化运行时使用激活 COM 对象。  
  
2.  运行时调用指定函数的`hostCallback`参数。  
  
3.  所指定函数的`hostCallback`然后进行以下一系列的调用：  
  
    -   所指定函数的`pBeginHostSetup`参数。  
  
    -   `CorBindToRuntimeEx`（或另一个运行时初始化函数）。  
  
    -   [Iclrruntimehost:: Sethostcontrol](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)。  
  
    -   [Iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)。  
  
    -   所指定函数的`pEndHostSetup`参数。  
  
 从所有调用`pBeginHostSetup`到`pEndHostSetup`必须出现在单线程还是纤程中，具有相同的逻辑堆栈上。 此线程可以是不同于在其线程`hostCallback`调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
