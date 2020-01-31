---
title: IMethodMalloc 接口
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: e9cbf4551c2f8b183e9e6c37a74b13aff3a19ec1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860951"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc 接口
提供一个方法，用于为新的 Microsoft 中间语言（MSIL）函数体分配内存。  
  
> [!NOTE]
> `IMethodMalloc` 接口是一个简单的内存分配器。 它允许您分配内存，但不能释放内存。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Alloc 方法](imethodmalloc-alloc-method.md)|尝试为新的 MSIL 函数体分配指定的内存量。|  
  
## <a name="remarks"></a>备注  
 每个分配器都是特定于模块的，并确保函数体与模块的基偏移为正偏移量。 超出模块基的内存可能非常宝贵，因此应使用分配器仅为函数体分配内存。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Profiling 接口](profiling-interfaces.md)
