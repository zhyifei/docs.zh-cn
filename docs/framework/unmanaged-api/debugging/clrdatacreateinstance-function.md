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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5d44f9b5dc42147959d3f1d127a64d39258f515
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274268"
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
  
## <a name="parameters"></a>参数  
 `iid`  
 中要实例化的接口的标识符。  
  
 `target`  
 中一个指向用户实现的[ICLRDataTarget](iclrdatatarget-interface.md)对象的指针，该对象表示要为其创建 interface 对象的目标项。  
  
 `iface`  
 弄指向返回的接口对象地址的指针。  
  
## <a name="remarks"></a>备注  
 `ICLRDataTarget`对象由调试应用程序的编写器实现。 实现取决于所表示的目标项的类型。 目标项可以是进程、内存转储、远程计算机，等等。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** ClrData.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试全局静态函数](debugging-global-static-functions.md)
