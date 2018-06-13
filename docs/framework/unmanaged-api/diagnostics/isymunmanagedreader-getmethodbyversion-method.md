---
title: ISymUnmanagedReader::GetMethodByVersion 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef5888c33e9532e5fc132fe571d59699d6f80c49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425165"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="bc058-102">ISymUnmanagedReader::GetMethodByVersion 方法</span><span class="sxs-lookup"><span data-stu-id="bc058-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="bc058-103">获取符号读取器方法，在给定方法标记和编辑复制版本号。</span><span class="sxs-lookup"><span data-stu-id="bc058-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="bc058-104">版本号从 1 开始，而递增因编辑复制操作而更改方法每次。</span><span class="sxs-lookup"><span data-stu-id="bc058-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc058-105">语法</span><span class="sxs-lookup"><span data-stu-id="bc058-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc058-106">参数</span><span class="sxs-lookup"><span data-stu-id="bc058-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="bc058-107">[in]方法标记中。</span><span class="sxs-lookup"><span data-stu-id="bc058-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="bc058-108">[in]方法版本中。</span><span class="sxs-lookup"><span data-stu-id="bc058-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="bc058-109">[out]指向返回的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="bc058-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc058-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bc058-110">Return Value</span></span>  
 <span data-ttu-id="bc058-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="bc058-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc058-112">要求</span><span class="sxs-lookup"><span data-stu-id="bc058-112">Requirements</span></span>  
 <span data-ttu-id="bc058-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bc058-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc058-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc058-114">See Also</span></span>  
 [<span data-ttu-id="bc058-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="bc058-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
