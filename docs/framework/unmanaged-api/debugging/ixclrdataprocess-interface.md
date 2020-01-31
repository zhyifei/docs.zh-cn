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
ms.openlocfilehash: a5d707d61513b030e5968af28db3c2a606e4419b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790375"
---
# <a name="ixclrdataprocess-interface"></a>IXCLRDataProcess 接口

提供用于查询有关进程的信息的方法。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>方法

| 方法                                                                                                                                               | 描述                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | 按唯一 id 获取进程中的 `AppDomain`。                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | 提供枚举进程的模块的句柄。                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | 枚举此进程的模块。                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | 释放模块枚举期间使用的内部迭代器所使用的资源。               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | 提供一个句柄，用于枚举从给定地址开始 `AppDomain` 的方法实例。 |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | 枚举此进程的方法实例（从地址偏移量开始）。                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | 释放实例枚举期间使用的内部迭代器所使用的资源。             |

## <a name="remarks"></a>备注

此接口在运行时中存在，不会通过任何标头或库文件公开。 不过，它是一个使用 GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` 派生的 COM 接口，可通过常用的 COM 机制来获取 `IUnknown`。

## <a name="requirements"></a>需求

**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。   
**标头：** 内容  
**库：** 内容  
**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>另请参阅

- [调试](index.md)
- [调试接口](debugging-interfaces.md)
