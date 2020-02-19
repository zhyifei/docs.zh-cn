---
title: ICorProfilerInfo9 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 431a546fb4a3b92b379e273553f0caf540ba1473
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449723"
---
# <a name="icorprofilerinfo9-interface"></a>ICorProfilerInfo9 接口

[ICorProfilerInfo8](icorprofilerinfo8-interface.md)的子类，提供用于查询有关具有多个本机代码版本的函数的信息的方法。  

## <a name="methods"></a>方法  

| 方法|说明|  
| ------------|-----------------|  
|[GetNativeCodeStartAddresses 方法](icorprofilerinfo9-getnativecodestartaddresses-method.md)| 给定一个 functionId 和 rejitId，枚举此代码当前存在的所有实时编译版本的本机代码起始地址。 |
|[GetILToNativeMapping3 方法](icorprofilerinfo9-getiltonativemapping3-method.md)| 给定本机代码起始地址，返回此实时编译版本的代码的本机到 IL 映射信息。 |
|[GetCodeInfo4 方法](icorprofilerinfo9-getcodeinfo4-method.md)| 给定本机代码起始地址，返回存储此代码的虚拟内存块。 |

## <a name="requirements"></a>要求  
**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。  
**头文件：** CorProf.idl、CorProf.h  
**.Net 版本：** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>另请参阅

- [Profiling 接口](profiling-interfaces.md)
