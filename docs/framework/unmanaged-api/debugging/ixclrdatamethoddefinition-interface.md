---
title: IXCLRDataMethodDefinition 接口
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790427"
---
# <a name="ixclrdatamethoddefinition-interface"></a>IXCLRDataMethodDefinition 接口

提供用于查询有关方法定义的信息的方法。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>方法

以下方法是接口中的一些可用方法。

| 方法                                                                                                                          | 描述                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [StartEnumInstances](ixclrdatamethoddefinition-startenuminstances-method.md) | 提供给定 `IXCLRDataAppDomain`的方法实例枚举的句柄。 |
| [EnumInstance](ixclrdatamethoddefinition-enuminstance-method.md)             | 枚举此方法定义的实例。                                         |
| [EndEnumInstances](ixclrdatamethoddefinition-endenuminstances-method.md)     | 释放实例枚举期间使用的内部迭代器所使用的资源。         |

## <a name="remarks"></a>备注

此接口在运行时中存在，不会通过任何标头或库文件公开。 不过，它是一个使用 GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` 派生的 COM 接口，可通过常用的 COM 机制来获取 `IUnknown`。

## <a name="requirements"></a>需求

**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** 内容  
**库：** 内容  
**.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>另请参阅

- [调试](index.md)
- [调试接口](debugging-interfaces.md)
