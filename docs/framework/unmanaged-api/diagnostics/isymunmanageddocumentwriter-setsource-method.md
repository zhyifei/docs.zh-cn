---
title: ISymUnmanagedDocumentWriter::SetSource 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
ms.openlocfilehash: 06c6f9b05d34ea98dde437393ded289cbab2f61d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615522"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="fa7da-102">ISymUnmanagedDocumentWriter::SetSource 方法</span><span class="sxs-lookup"><span data-stu-id="fa7da-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="fa7da-103">为正在编写的文档设置嵌入源。</span><span class="sxs-lookup"><span data-stu-id="fa7da-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7da-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa7da-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa7da-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa7da-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="fa7da-106">中一个 `ULONG32` 包含缓冲区大小的 `source` 。</span><span class="sxs-lookup"><span data-stu-id="fa7da-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="fa7da-107">中存储嵌入源的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="fa7da-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa7da-108">返回值</span><span class="sxs-lookup"><span data-stu-id="fa7da-108">Return Value</span></span>  
 <span data-ttu-id="fa7da-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="fa7da-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa7da-110">要求</span><span class="sxs-lookup"><span data-stu-id="fa7da-110">Requirements</span></span>  
 <span data-ttu-id="fa7da-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="fa7da-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa7da-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa7da-112">See also</span></span>

- [<span data-ttu-id="fa7da-113">ISymUnmanagedDocumentWriter 接口</span><span class="sxs-lookup"><span data-stu-id="fa7da-113">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
