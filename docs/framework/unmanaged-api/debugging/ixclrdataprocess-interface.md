---
title: IXCLRDataProcess 接口
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178374"
---
# <a name="ixclrdataprocess-interface"></a>IXCLRDataProcess 接口

提供了查询有关进程的信息的方法。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>方法

| 方法                                                                                                                                               | 说明                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | 通过进程`AppDomain`的唯一 ID 获取 进程中的 。                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | 提供一个句柄来枚举进程的模块。                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | 枚举此过程的模块。                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | 释放模块枚举期间使用的内部迭代器使用的资源。               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | 提供一个句柄来枚举从给定地址`AppDomain`开始的方法实例。 |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | 枚举从地址偏移开始此过程的方法实例。                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | 释放实例枚举期间使用的内部迭代器使用的资源。             |

## <a name="remarks"></a>备注

此接口位于运行时内，不会通过任何标头或库文件公开。 但是，它是一个 COM 接口，派生自`IUnknown`GUID，`5c552ab6-fc09-4cb3-8e36-22fa03c798b7`可通过通常的 COM 机制获得。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。
**标题：** 没有  
**库：** 没有  
**.NET 框架版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>另请参阅

- [调试](index.md)
- [调试接口](debugging-interfaces.md)
