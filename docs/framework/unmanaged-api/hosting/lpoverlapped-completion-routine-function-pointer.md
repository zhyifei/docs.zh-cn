---
title: LPOVERLAPPED_COMPLETION_ROUTINE 函数指针
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dcf63000de549b42d92ba157a7e550ac605bbfcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768390"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a>LPOVERLAPPED_COMPLETION_ROUTINE 函数指针
指向通知主机时的重叠的函数 (即异步) 到设备的 I/O 已完成。  
  
 .NET Framework 4 中已弃用此函数指针。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a>参数  
 `dwErrorCode`  
 [in]一个值，如果设备已关闭; 是一个错误代码否则，此值为零。  
  
 关闭设备将导致所有挂起的设备对 i/o 操作立即完成。  
  
 `dwNumberOfBytesTransfered`  
 [in]I/O 操作传输的字节数。  
  
 `lpOverlapped`  
 [in]指向包含要用来完成 I/O 请求的信息的结构的指针。  
  
## <a name="remarks"></a>备注  
 该函数`LPOVERLAPPED_COMPLETION_ROUTINE`点是回调函数，必须由主机应用程序的编写器实现。 回调函数允许主机来处理已完成的 I/O 请求。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** MSCorWks.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
