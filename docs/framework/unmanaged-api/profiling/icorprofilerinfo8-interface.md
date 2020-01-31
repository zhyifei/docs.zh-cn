---
title: ICorProfilerInfo8 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 476bcbd91188e3ff9eb63f50cfa2118a440b1a69
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868312"
---
# <a name="icorprofilerinfo8-interface"></a>ICorProfilerInfo8 接口

[ICorProfilerInfo7](icorprofilerinfo7-interface.md)的子类，提供查询有关动态方法的信息的方法。

## <a name="methods"></a>方法  

| 方法|描述|  
| ------------|-----------------|  
|[IsFunctionDynamic 方法](icorprofilerinfo8-isfunctiondynamic-method.md)| 确定函数是否没有关联的元数据。|
|[GetFunctionFromIP3 方法](icorprofilerinfo8-getfunctionfromip3-method.md)| 将托管代码指令指针映射到 FunctionID。 此方法适用于动态和非动态方法。 |
|[GetDynamicFunctionInfo 方法](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| 检索有关动态方法的信息。 |

## <a name="requirements"></a>需求  
**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
**头文件：** CorProf.idl、CorProf.h  
**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>另请参阅

- [Profiling 接口](profiling-interfaces.md)
