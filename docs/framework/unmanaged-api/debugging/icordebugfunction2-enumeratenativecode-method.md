---
title: ICorDebugFunction2::EnumerateNativeCode 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb7e2ed7b076cfa20064902b3592c8f958efc0ee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917051"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="1f3fd-102">ICorDebugFunction2::EnumerateNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="1f3fd-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="1f3fd-103">获取一个指向 ICorDebugCodeEnum 对象的接口指针, 该对象包含此 ICorDebugFunction2 对象引用的函数中的本机代码语句。</span><span class="sxs-lookup"><span data-stu-id="1f3fd-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f3fd-104">`EnumerateNativeCode`在 .NET Framework 的当前版本中未实现。</span><span class="sxs-lookup"><span data-stu-id="1f3fd-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f3fd-105">语法</span><span class="sxs-lookup"><span data-stu-id="1f3fd-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1f3fd-106">要求</span><span class="sxs-lookup"><span data-stu-id="1f3fd-106">Requirements</span></span>  
 <span data-ttu-id="1f3fd-107">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="1f3fd-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
