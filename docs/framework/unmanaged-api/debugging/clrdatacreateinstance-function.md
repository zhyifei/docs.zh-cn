---
title: CLRDataCreateInstance 函数
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
ms.openlocfilehash: c24963a6e56adfb9f763c6521027744db82cc357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179364"
---
# <a name="clrdatacreateinstance-function"></a>CLRDataCreateInstance 函数
为指定的目标项创建接口对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a>parameters  
 `iid`  
 [在]要实例化的接口的标识符。  
  
 `target`  
 [在]指向用户实现的[ICLRDataTarget](iclrdatatarget-interface.md)对象的指针，该对象表示要为其创建接口对象的目标项。  
  
 `iface`  
 [出]指向返回接口对象地址的指针。  
  
## <a name="remarks"></a>备注  
 该`ICLRDataTarget`对象由调试应用程序的编写器实现。 实现取决于表示的目标项的类型。 目标项可以是进程、内存转储、远程计算机等。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** ClrData.idl  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试全局静态函数](debugging-global-static-functions.md)
