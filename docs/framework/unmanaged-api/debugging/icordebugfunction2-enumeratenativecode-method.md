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
ms.openlocfilehash: a4d15d9ae63e63f98ab73e250df558dfa16002a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959960"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="e99d5-102">ICorDebugFunction2::EnumerateNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="e99d5-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="e99d5-103">ICorDebugCodeEnum 对象，包含此 ICorDebugFunction2 对象引用的函数中的本机代码语句获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="e99d5-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e99d5-104">`EnumerateNativeCode` .NET Framework 的当前版本中未实现。</span><span class="sxs-lookup"><span data-stu-id="e99d5-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e99d5-105">语法</span><span class="sxs-lookup"><span data-stu-id="e99d5-105">Syntax</span></span>  
  
```  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e99d5-106">要求</span><span class="sxs-lookup"><span data-stu-id="e99d5-106">Requirements</span></span>  
 <span data-ttu-id="e99d5-107">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e99d5-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
