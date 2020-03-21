---
title: ClrCreateManagedInstance 函数
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: 7fbe0cf3e93d75749fa3f463f3f97dbd1bfe27a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176534"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance 函数
创建指定托管类型的实例。  
  
 此功能已在 .NET 框架 4 中弃用。 使用 COM 激活创建托管类型的实例，或使用托管（请参阅[在 .NET 框架 4 和 4.5 中添加的 CLR 托管接口](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>parameters  
 `pTypeName`  
 [在]指向要请求的实例类型的名称的指针。  
  
 `riid`  
 [在]要`IID`请求的实例类型的 。  
  
 `ppObject`  
 [出]指向调用方请求的托管类型的实例的指针。  
  
## <a name="remarks"></a>备注  
 公共语言运行时应已加载到进程中。 例如，在调用`ClrCreateManagedInstance`函数之前，可以使用对[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数的调用来加载它。 如果未加载运行时，`ClrCreateManagedInstance`则首先尝试加载运行时的 v1.0.3705。 如果失败，它将尝试加载最新版本的运行时。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)
