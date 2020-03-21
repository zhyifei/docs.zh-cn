---
title: CreateCoreClrDebugTarget 函数
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: 0b210f105495fa3f5595adbcb0805e1d1fb62310
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179222"
---
# <a name="createcoreclrdebugtarget-function"></a>CreateCoreClrDebugTarget 函数
创建与在远程计算机上运行的调试器代理的连接，并返回一个[ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)对象，该对象可用于查询远程计算机上的正在运行的进程和加载的运行时。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a>parameters  
 `dwAddress`  
 [in] 远程目标计算机的 IPv4 地址。  
  
 `ppTarget`  
 [出]指向将创建的[ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)对象的指针。  
  
## <a name="return-value"></a>返回值  
 S_OK  
 已成功确定该进程中的 CLR 的数目，并已正确填写相应的句柄数组和路径数组。  
  
 E_OUTOFMEMORY  
 无法为 `ppTarget` 分配足够的内存。  
  
 E_FAIL（或其他 E_ 返回代码）  
 其他故障。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 核心Clr远程调试接口.h  
  
 **资料库：** mscordbi_macx86.dll  
  
 **.NET 框架版本：** 3.5 SP1
