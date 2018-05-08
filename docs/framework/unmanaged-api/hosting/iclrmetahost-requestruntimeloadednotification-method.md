---
title: ICLRMetaHost::RequestRuntimeLoadedNotification 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ac041db64a874cc143657c601f30e4482dd2462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>ICLRMetaHost::RequestRuntimeLoadedNotification 方法
提供保证在首次加载，但尚未启动的公共语言运行时 (CLR) 版本时要调用的回调函数。 此方法取代[LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a>参数  
 `pCallbackFunction`  
 [in]当加载新的运行时调用的回调函数。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_POINTER|`pCallbackFunction` 为 null。|  
  
## <a name="remarks"></a>备注  
 回调的工作方式如下：  
  
-   仅当首次加载运行时，将调用回调。  
  
-   对同一个运行时的可重入负载不调用该回调。  
  
-   来进行非可重入运行时加载，序列化对回调函数的调用。  
  
 回调函数具有以下原型：  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 回调函数的原型如下所示：  
  
-   `pfnCallbackThreadSet`：  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   `pfnCallbackThreadUnset`：  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 如果宿主要加载或导致另一个运行时，才能加载到可重入的方式，`pfnCallbackThreadSet`和`pfnCallbackThreadUnset`提供在回调必须按以下方式使用函数的参数：  
  
-   `pfnCallbackThreadSet` 必须由尝试此类负载之前，可能会导致运行时负载的线程调用。  
  
-   `pfnCallbackThreadUnset` 必须调用时该线程将不再导致出现运行时负载 （和从初始回调返回之前）。  
  
-   `pfnCallbackThreadSet` 和`pfnCallbackThreadUnset`都是不可重入。  
  
> [!NOTE]
>  主机应用程序不能调用`pfnCallbackThreadSet`和`pfnCallbackThreadUnset`的范围之外`pCallbackFunction`参数。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRMetaHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
