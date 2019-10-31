---
title: ICLRDataTarget2::AllocVirtual 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
ms.openlocfilehash: 7640f7fafd0bf52a302ac0da1e5df39b5da22d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091146"
---
# <a name="iclrdatatarget2allocvirtual-method"></a>ICLRDataTarget2::AllocVirtual 方法
由公共语言运行时（CLR）数据访问服务调用，以在此目标进程的地址空间中分配内存。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a>参数  
 `addr`  
 中一个 `CLRDATA_ADDRESS` 值，该值指定要分配的内存的起始地址。  
  
 `size`  
 中要分配的内存的大小（以字节为单位）。  
  
 `typeFlags`  
 中控制内存分配的标志。 请参阅 Win32 `VirtualAlloc` 函数。  
  
 `protectFlags`  
 中已分配内存的保护特性。 请参阅 Win32 `VirtualAlloc` 函数。  
  
 `virt`  
 弄一个指向 `CLRDATA_ADDRESS` 值的指针，该值指定分配的内存的实际起始地址。  
  
## <a name="remarks"></a>备注  
 `AllocVirtual` 方法用作 Win32 `VirtualAlloc` 函数的逻辑包装。  
  
 此方法由调试应用程序的编写器实现。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** ClrData，ClrData  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRDataTarget2 接口](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [FreeVirtual 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
