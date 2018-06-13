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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411783"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="0f776-102">ICorDebugFunction2::EnumerateNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="0f776-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="0f776-103">获取一个包含此 ICorDebugFunction2 对象引用的函数中的本机代码语句的 ICorDebugCodeEnum 对象的接口指针。</span><span class="sxs-lookup"><span data-stu-id="0f776-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f776-104">`EnumerateNativeCode` .NET Framework 的当前版本中未实现。</span><span class="sxs-lookup"><span data-stu-id="0f776-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f776-105">语法</span><span class="sxs-lookup"><span data-stu-id="0f776-105">Syntax</span></span>  
  
```  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="0f776-106">要求</span><span class="sxs-lookup"><span data-stu-id="0f776-106">Requirements</span></span>  
 <span data-ttu-id="0f776-107">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f776-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
