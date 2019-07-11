---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 06b8ebf26794baa1d957cc47d1179283611b62d5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736682"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="10cef-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="10cef-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="10cef-103">获取符号读取器方法，给定一个方法标记和编辑并继续的版本号。</span><span class="sxs-lookup"><span data-stu-id="10cef-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="10cef-104">版本号从 1 开始，并会在每的次递增的方法更改因执行编辑并继续操作。</span><span class="sxs-lookup"><span data-stu-id="10cef-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10cef-105">语法</span><span class="sxs-lookup"><span data-stu-id="10cef-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10cef-106">参数</span><span class="sxs-lookup"><span data-stu-id="10cef-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="10cef-107">[in]方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="10cef-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="10cef-108">[in]方法版本。</span><span class="sxs-lookup"><span data-stu-id="10cef-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="10cef-109">[out]指向返回的指针[ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="10cef-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10cef-110">返回值</span><span class="sxs-lookup"><span data-stu-id="10cef-110">Return Value</span></span>  
 <span data-ttu-id="10cef-111">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="10cef-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10cef-112">要求</span><span class="sxs-lookup"><span data-stu-id="10cef-112">Requirements</span></span>  
 <span data-ttu-id="10cef-113">**标头：** CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="10cef-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="10cef-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="10cef-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10cef-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="10cef-115">See also</span></span>

- [<span data-ttu-id="10cef-116">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="10cef-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
