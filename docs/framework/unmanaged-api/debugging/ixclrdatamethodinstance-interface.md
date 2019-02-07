---
title: IXCLRDataMethodInstance 接口
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7185802a3857fcd73c63d097090a2a7809f65279
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825922"
---
# <a name="ixclrdatamethodinstance-interface"></a>IXCLRDataMethodInstance 接口

提供用于查询方法实例的信息的方法。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>方法

| 方法                                                                                                                  | 描述                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [GetILAddressMap](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | 获取到地址映射信息的 IL。 |
| [GetRepresentativeEntryAddress](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | 获取用于本机编译的方法的所有可能的入口点的最具代表性的入口点地址... |


## <a name="remarks"></a>备注

此接口存在于运行时内并不通过任何标头或库文件公开。 但是，它是一个 COM 接口派生`IUnknown`具有 GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` ，可以通过常用的 COM 机制获取。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
**标头：** 无  
**库：** 无  
**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>请参阅

- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
