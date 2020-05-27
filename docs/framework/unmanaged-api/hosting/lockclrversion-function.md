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
ms.openlocfilehash: 09bcebfdcfea3d5728d404cdb6b5fb170a5432c3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008490"
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
  
|返回代码|说明|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|一个或多个参数为 null。|  
  
## <a name="remarks"></a>备注  
 宿主在 `LockClrVersion` 初始化 CLR 前调用。 `LockClrVersion`使用三个参数，所有这些参数都是[FLockClrVersionCallback](flockclrversioncallback-function-pointer.md)类型的回调。 此类型的定义如下。  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 在运行时初始化时执行以下步骤：  
  
1. 宿主调用[CorBindToRuntimeEx](corbindtoruntimeex-function.md)或其他运行时初始化函数之一。 或者，宿主可以使用 COM 对象激活来初始化运行时。  
  
2. 运行时调用由参数指定的函数 `hostCallback` 。  
  
3. 指定的函数将 `hostCallback` 执行以下序列调用：  
  
    - 由参数指定的函数 `pBeginHostSetup` 。  
  
    - `CorBindToRuntimeEx`（或另一个运行时初始化函数）。  
  
    - [ICLRRuntimeHost：： SetHostControl](iclrruntimehost-sethostcontrol-method.md)。  
  
    - [ICLRRuntimeHost：： Start](iclrruntimehost-start-method.md)。  
  
    - 由参数指定的函数 `pEndHostSetup` 。  
  
 从到的所有 `pBeginHostSetup` 调用 `pEndHostSetup` 都必须在具有相同逻辑堆栈的单个线程或纤程上发生。 此线程可以与调用的线程不同 `hostCallback` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](deprecated-clr-hosting-functions.md)
