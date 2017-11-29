---
title: "ISymUnmanagedReader2::GetMethodByVersionPreRemap 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 69a203424320a176cd285c23d98111e71709042a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="c824c-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="c824c-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="c824c-103">获取符号读取器方法，在给定方法标记和编辑并继续的版本号。</span><span class="sxs-lookup"><span data-stu-id="c824c-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="c824c-104">版本号从 1 开始，并递增的编辑并继续操作后更改此方法每次。</span><span class="sxs-lookup"><span data-stu-id="c824c-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c824c-105">语法</span><span class="sxs-lookup"><span data-stu-id="c824c-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c824c-106">参数</span><span class="sxs-lookup"><span data-stu-id="c824c-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="c824c-107">[in]方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="c824c-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="c824c-108">[in]方法版本中。</span><span class="sxs-lookup"><span data-stu-id="c824c-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c824c-109">[out]指向返回的指针[ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="c824c-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c824c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c824c-110">Return Value</span></span>  
 <span data-ttu-id="c824c-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c824c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c824c-112">要求</span><span class="sxs-lookup"><span data-stu-id="c824c-112">Requirements</span></span>  
 <span data-ttu-id="c824c-113">**标头：** CorSym.idl。</span><span class="sxs-lookup"><span data-stu-id="c824c-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="c824c-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c824c-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c824c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c824c-115">See Also</span></span>  
 [<span data-ttu-id="c824c-116">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="c824c-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
