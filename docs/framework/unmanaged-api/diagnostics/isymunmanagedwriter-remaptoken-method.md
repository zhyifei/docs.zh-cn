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
ms.openlocfilehash: 9e441d4ff39632d9381e445ee99249d04539ad87
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427883"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="bec4f-102">ISymUnmanagedWriter::RemapToken 方法</span><span class="sxs-lookup"><span data-stu-id="bec4f-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="bec4f-103">通知符号编写器在发出元数据时已重新映射元数据标记。</span><span class="sxs-lookup"><span data-stu-id="bec4f-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="bec4f-104">如果符号编写器已将旧标记存储在符号存储区中，则必须用新值更新已存储的标记，或者必须将相应符号读取器的映射保存到读取阶段中重新映射。</span><span class="sxs-lookup"><span data-stu-id="bec4f-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bec4f-105">语法</span><span class="sxs-lookup"><span data-stu-id="bec4f-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bec4f-106">参数</span><span class="sxs-lookup"><span data-stu-id="bec4f-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="bec4f-107">中重新映射的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="bec4f-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="bec4f-108">中`oldToken` 重新映射到的新的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="bec4f-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bec4f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bec4f-109">Return Value</span></span>  
 <span data-ttu-id="bec4f-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="bec4f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bec4f-111">要求</span><span class="sxs-lookup"><span data-stu-id="bec4f-111">Requirements</span></span>  
 <span data-ttu-id="bec4f-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="bec4f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec4f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bec4f-113">See also</span></span>

- [<span data-ttu-id="bec4f-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="bec4f-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
