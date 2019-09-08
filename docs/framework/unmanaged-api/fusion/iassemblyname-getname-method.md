---
title: IAssemblyName::GetName 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e471ee99af57ef980850c0a5d3e4f5f2973967ac
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796601"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="0fae9-102">IAssemblyName::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="0fae9-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="0fae9-103">获取此[IAssemblyName](iassemblyname-interface.md)对象所引用的程序集的简单、未加密名称。</span><span class="sxs-lookup"><span data-stu-id="0fae9-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fae9-104">语法</span><span class="sxs-lookup"><span data-stu-id="0fae9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fae9-105">参数</span><span class="sxs-lookup"><span data-stu-id="0fae9-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="0fae9-106">[in，out]宽字符的`pwzName`大小，包括 null 终止符。</span><span class="sxs-lookup"><span data-stu-id="0fae9-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="0fae9-107">弄用于保存所引用程序集的名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0fae9-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fae9-108">要求</span><span class="sxs-lookup"><span data-stu-id="0fae9-108">Requirements</span></span>  
 <span data-ttu-id="0fae9-109">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0fae9-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fae9-110">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="0fae9-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0fae9-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fae9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fae9-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fae9-112">See also</span></span>

- [<span data-ttu-id="0fae9-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="0fae9-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
