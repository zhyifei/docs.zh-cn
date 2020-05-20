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
ms.openlocfilehash: ecd618ecf08836ea5e38ce738f97fc91ee6426f4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616806"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance 函数
创建指定托管类型的实例。  
  
 此函数已在 .NET Framework 4 中弃用。 使用 COM 激活创建托管类型的实例，或使用宿主（请参阅[.NET Framework 4 和4.5 中添加的 CLR 承载接口](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>参数  
 `pTypeName`  
 中一个指针，指向所请求的实例类型的名称。  
  
 `riid`  
 中`IID`请求的实例类型的。  
  
 `ppObject`  
 弄指向调用方请求的托管类型实例的指针的指针。  
  
## <a name="remarks"></a>备注  
 公共语言运行时应已加载到进程中。 例如，在调用函数之前，可以使用对[CorBindToRuntimeEx](corbindtoruntimeex-function.md)函数的调用来加载该 `ClrCreateManagedInstance` 函数。 如果未加载运行时，则 `ClrCreateManagedInstance` 首先尝试加载运行时的 v v1.0.3705。 如果失败，它将尝试加载最新版本的运行时。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](deprecated-clr-hosting-functions.md)
- [承载](index.md)
