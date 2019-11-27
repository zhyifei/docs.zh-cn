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
ms.openlocfilehash: 2063856389b122b150a2d2744169a4a567592287
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446446"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="9e0e1-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="9e0e1-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="9e0e1-103">在给定方法标记和编辑并继续版本号的情况下，获取符号读取器方法。</span><span class="sxs-lookup"><span data-stu-id="9e0e1-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="9e0e1-104">版本号从1开始，并在每次通过 "编辑并继续" 操作的结果更改方法时递增。</span><span class="sxs-lookup"><span data-stu-id="9e0e1-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e0e1-105">语法</span><span class="sxs-lookup"><span data-stu-id="9e0e1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e0e1-106">参数</span><span class="sxs-lookup"><span data-stu-id="9e0e1-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="9e0e1-107">中方法元数据标记。</span><span class="sxs-lookup"><span data-stu-id="9e0e1-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="9e0e1-108">中方法版本。</span><span class="sxs-lookup"><span data-stu-id="9e0e1-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9e0e1-109">弄指向返回的[ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="9e0e1-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e0e1-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9e0e1-110">Return Value</span></span>  
 <span data-ttu-id="9e0e1-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="9e0e1-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e0e1-112">要求</span><span class="sxs-lookup"><span data-stu-id="9e0e1-112">Requirements</span></span>  
 <span data-ttu-id="9e0e1-113">**标头：** CorSym。</span><span class="sxs-lookup"><span data-stu-id="9e0e1-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="9e0e1-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9e0e1-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e0e1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e0e1-115">See also</span></span>

- [<span data-ttu-id="9e0e1-116">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="9e0e1-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
