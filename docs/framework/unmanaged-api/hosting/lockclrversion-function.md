---
title: LockClrVersion 函数
ms.date: 03/30/2017
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
ms.openlocfilehash: 216852f8f051440b2814619b843a1f25013e4042
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133774"
---
# <a name="lockclrversion-function"></a>LockClrVersion 函数
允许宿主在显式初始化 CLR 之前确定将在进程内使用的公共语言运行时（CLR）的版本。  
  
 此函数已在 .NET Framework 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a>参数  
 `hostCallback`  
 中CLR 在初始化时调用的函数。  
  
 `pBeginHostSetup`  
 中由宿主调用以通知 CLR 初始化正在启动的函数。  
  
 `pEndHostSetup`  
 中由宿主调用以通知 CLR 初始化已完成的函数。  
  
## <a name="return-value"></a>返回值  
 除以下值外，此方法还返回 Winerror.h 中定义的标准 COM 错误代码。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|一个或多个参数为 null。|  
  
## <a name="remarks"></a>备注  
 宿主在初始化 CLR 之前调用 `LockClrVersion`。 `LockClrVersion` 采用三个参数，所有这些参数都是[FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)类型的回调。 此类型的定义如下。  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 在运行时初始化时执行以下步骤：  
  
1. 宿主调用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或其他运行时初始化函数之一。 或者，宿主可以使用 COM 对象激活来初始化运行时。  
  
2. 运行时调用由 `hostCallback` 参数指定的函数。  
  
3. 然后 `hostCallback` 指定的函数将执行以下一系列调用：  
  
    - 由 `pBeginHostSetup` 参数指定的函数。  
  
    - `CorBindToRuntimeEx` （或另一个运行时初始化函数）。  
  
    - [ICLRRuntimeHost：： SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)。  
  
    - [ICLRRuntimeHost：： Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)。  
  
    - 由 `pEndHostSetup` 参数指定的函数。  
  
 从 `pBeginHostSetup` 到 `pEndHostSetup` 的所有调用都必须在具有相同逻辑堆栈的单个线程或纤程上发生。 此线程可以与调用 `hostCallback` 的线程不同。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
