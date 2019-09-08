---
title: CreateAssemblyNameObject 函数
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb53014a28fb291b8463535addfb61e62d32d7d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795353"
---
# <a name="createassemblynameobject-function"></a>CreateAssemblyNameObject 函数
获取一个接口指针，该指针指向表示具有指定名称的程序集的唯一标识的[IAssemblyName](iassemblyname-interface.md)实例。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a>参数  
 `ppAssemblyNameObj`  
 弄返回`IAssemblyName`的。  
  
 `szAssemblyName`  
 中要为其创建新`IAssemblyName`实例的程序集的名称。  
  
 `dwFlags`  
 中要传递给对象构造函数的标志。  
  
 `pvReserved`  
 中保留以供将来进行扩展。 `pvReserved`必须为空引用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IAssemblyName 接口](iassemblyname-interface.md)
- [合成全局静态函数](fusion-global-static-functions.md)
