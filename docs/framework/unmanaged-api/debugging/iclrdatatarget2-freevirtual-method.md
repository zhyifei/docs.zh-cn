---
title: ICLRDataTarget2::FreeVirtual 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
ms.openlocfilehash: 7eda9bfff6de6b386c16ad0a188931d9d3adcb93
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793663"
---
# <a name="iclrdatatarget2freevirtual-method"></a>ICLRDataTarget2::FreeVirtual 方法
由公共语言运行时（CLR）数据访问服务调用，以释放以前在目标进程的地址空间中分配的内存。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `addr`  
 中一个 `CLRDATA_ADDRESS` 值，该值指定要释放的内存的起始地址。  
  
 `size`  
 中要释放的内存的大小（以字节为单位）。  
  
 `typeFlags`  
 中控制释放内存的标志。 请参阅 Win32 `VirtualFree` 函数。  
  
## <a name="remarks"></a>备注  
 `FreeVirtual` 方法用作 Win32 `VirtualFree` 函数的逻辑包装。  
  
 此方法由调试应用程序的编写器实现。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** ClrData，ClrData  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRDataTarget2 接口](iclrdatatarget2-interface.md)
- [AllocVirtual 方法](iclrdatatarget2-allocvirtual-method.md)
