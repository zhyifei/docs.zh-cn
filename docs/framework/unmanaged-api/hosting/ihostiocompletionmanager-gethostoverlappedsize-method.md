---
title: IHostIoCompletionManager::GetHostOverlappedSize 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
ms.openlocfilehash: a97009a4ebc834d867dddcc350033c550364ea42
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804750"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a>IHostIoCompletionManager::GetHostOverlappedSize 方法
获取宿主打算追加到 i/o 请求的任何自定义数据的大小。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a>参数  
 `pcbSize`  
 弄一个指针，指向公共语言运行时（CLR）除 Win32 对象的大小外应分配的字节数 `OVERLAPPED` 。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时，该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 对 Windows 平台 Api 的所有异步 i/o 调用都采用 Win32 `OVERLAPPED` 对象，后者提供了文件指针位置等信息。 若要维护状态，执行异步 i/o 调用的应用程序通常会将自定义数据添加到该结构中。 `GetHostOverlappedSize`和[IHostIoCompletionManager：： InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md)为主机提供了一个机会，使其包括此类自定义数据。  
  
 CLR 调用 `GetHostOverlappedSize` 方法来确定宿主打算追加到对象的自定义数据的大小 `OVERLAPPED` 。  
  
> [!NOTE]
> `GetHostOverlappedSize`只调用一次。 主机的自定义数据必须与每个 i/o 请求的大小相同。  
  
> [!IMPORTANT]
> 对象本身的大小 `OVERLAPPED` 不包含在的值中 `pcbSize` 。  
  
 有关结构的详细信息 `OVERLAPPED` ，请参阅 Windows 平台文档。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Threading.NativeOverlapped>
- [ICLRIoCompletionManager 接口](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager 接口](ihostiocompletionmanager-interface.md)
