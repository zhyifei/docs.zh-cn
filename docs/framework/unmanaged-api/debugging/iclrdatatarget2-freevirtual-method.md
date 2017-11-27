---
title: "ICLRDataTarget2::FreeVirtual 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2.FreeVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1619e9eb02eec1985c3c550626ef955162d1b984
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget2freevirtual-method"></a>ICLRDataTarget2::FreeVirtual 方法
由为以前分配目标进程的地址空间中的可用内存到公共语言运行时 (CLR) 数据访问服务调用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `addr`  
 [in]A`CLRDATA_ADDRESS`值，该值指定要释放的内存的起始地址。  
  
 `size`  
 [in]以字节为单位，要被释放的内存的大小。  
  
 `typeFlags`  
 [in]控制释放内存的标志。 请参阅 Win32`VirtualFree`函数。  
  
## <a name="remarks"></a>备注  
 `FreeVirtual`方法用作的逻辑包装为 Win32`VirtualFree`函数。  
  
 此方法由调试应用程序的编写器实现。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** ClrData.idl、 ClrData.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICLRDataTarget2 接口](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [AllocVirtual 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
