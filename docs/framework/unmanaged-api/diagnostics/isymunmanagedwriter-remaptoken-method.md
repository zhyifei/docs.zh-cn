---
title: ISymUnmanagedWriter::RemapToken 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 979d14b4c404c3bf12c427bd5b8b1d4997805e7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160675"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="f0a1c-102">ISymUnmanagedWriter::RemapToken 方法</span><span class="sxs-lookup"><span data-stu-id="f0a1c-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="f0a1c-103">通知的符号编写器元数据标记在发出元数据已被重新映射。</span><span class="sxs-lookup"><span data-stu-id="f0a1c-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="f0a1c-104">如果符号编写器已存储在符号存储区中旧的令牌，则它必须具有新值，或它的存储的令牌必须保存相应的符号读取器在读取阶段重新映射的映射更新。</span><span class="sxs-lookup"><span data-stu-id="f0a1c-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a1c-105">语法</span><span class="sxs-lookup"><span data-stu-id="f0a1c-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0a1c-106">参数</span><span class="sxs-lookup"><span data-stu-id="f0a1c-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="f0a1c-107">[in]已重新映射元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f0a1c-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="f0a1c-108">[in]向其新的元数据令牌`oldToken`已重新映射。</span><span class="sxs-lookup"><span data-stu-id="f0a1c-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0a1c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f0a1c-109">Return Value</span></span>  
 <span data-ttu-id="f0a1c-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="f0a1c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a1c-111">要求</span><span class="sxs-lookup"><span data-stu-id="f0a1c-111">Requirements</span></span>  
 <span data-ttu-id="f0a1c-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f0a1c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a1c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0a1c-113">See also</span></span>

- [<span data-ttu-id="f0a1c-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="f0a1c-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
