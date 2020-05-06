---
title: ICLRDataTarget2 接口
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
ms.openlocfilehash: 6b2700b2f12e312f06640a06e5ec82fbc58f2ca9
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860463"
---
# <a name="iclrdatatarget2-interface"></a>ICLRDataTarget2 接口
数据访问服务层用于处理目标进程中的虚拟内存区域的[ICLRDataTarget](iclrdatatarget-interface.md)的子类。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[AllocVirtual 方法](iclrdatatarget2-allocvirtual-method.md)|在目标进程的地址空间中分配内存。|  
|[FreeVirtual 方法](iclrdatatarget2-freevirtual-method.md)|释放以前在目标进程的地址空间中分配的内存。|  
  
## <a name="remarks"></a>备注  
 API 客户端（即调试器）必须针对特定的目标进程实现此接口。 例如，活动进程的实现将不同于内存转储的。 目标可能不支持对其内存区域的修改。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** ClrData，ClrData  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRDataTarget 接口](iclrdatatarget-interface.md)
- [调试接口](debugging-interfaces.md)
