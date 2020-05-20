---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument 方法
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
ms.openlocfilehash: 3ac8bb3a20ce82b734a572832a9cbb75fa2568c4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441898"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="c9b54-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="c9b54-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="c9b54-103">获取特定文档中该方法的最小起始行和最大结束行。</span><span class="sxs-lookup"><span data-stu-id="c9b54-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9b54-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9b54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9b54-105">参数</span><span class="sxs-lookup"><span data-stu-id="c9b54-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="c9b54-106">中指向文档的指针。</span><span class="sxs-lookup"><span data-stu-id="c9b54-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="c9b54-107">弄指向的指针 `ULONG32` ，该指针接收起始行。</span><span class="sxs-lookup"><span data-stu-id="c9b54-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="c9b54-108">弄指向 `ULONG32` 的指针，该指针接收结束行。</span><span class="sxs-lookup"><span data-stu-id="c9b54-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9b54-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c9b54-109">Return Value</span></span>  
 <span data-ttu-id="c9b54-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="c9b54-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9b54-111">要求</span><span class="sxs-lookup"><span data-stu-id="c9b54-111">Requirements</span></span>  
 <span data-ttu-id="c9b54-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="c9b54-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9b54-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9b54-113">See also</span></span>

- [<span data-ttu-id="c9b54-114">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="c9b54-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
