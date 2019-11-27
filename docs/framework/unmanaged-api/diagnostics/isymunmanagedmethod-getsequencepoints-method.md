---
title: ISymUnmanagedMethod::GetSequencePoints 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
ms.openlocfilehash: 75d477af7395a9b7d3328b2a5787f810733f3749
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448872"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="3bf56-102">ISymUnmanagedMethod::GetSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="3bf56-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="3bf56-103">获取此方法中的所有序列点。</span><span class="sxs-lookup"><span data-stu-id="3bf56-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bf56-104">语法</span><span class="sxs-lookup"><span data-stu-id="3bf56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bf56-105">参数</span><span class="sxs-lookup"><span data-stu-id="3bf56-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="3bf56-106">中接收 `offsets`、`documents`、`lines`、`columns`、`endLines`和 `endColumns` 数组大小的 `ULONG32`。</span><span class="sxs-lookup"><span data-stu-id="3bf56-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="3bf56-107">弄指向 `ULONG32` 的指针，该指针接收包含序列点所需的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="3bf56-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="3bf56-108">中一个数组，在其中存储序列点从方法的开头开始的 Microsoft 中间语言（MSIL）偏移量。</span><span class="sxs-lookup"><span data-stu-id="3bf56-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="3bf56-109">中要在其中存储序列点所在的文档的数组。</span><span class="sxs-lookup"><span data-stu-id="3bf56-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="3bf56-110">中要在其中存储序列点所在的文档中的行的数组。</span><span class="sxs-lookup"><span data-stu-id="3bf56-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="3bf56-111">中要在其中存储序列点所在的文档中的列的数组。</span><span class="sxs-lookup"><span data-stu-id="3bf56-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="3bf56-112">中序列点结束的文档中的行的数组。</span><span class="sxs-lookup"><span data-stu-id="3bf56-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="3bf56-113">中序列点结束的文档中的列的数组。</span><span class="sxs-lookup"><span data-stu-id="3bf56-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bf56-114">返回值</span><span class="sxs-lookup"><span data-stu-id="3bf56-114">Return Value</span></span>  
 <span data-ttu-id="3bf56-115">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="3bf56-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bf56-116">要求</span><span class="sxs-lookup"><span data-stu-id="3bf56-116">Requirements</span></span>  
 <span data-ttu-id="3bf56-117">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="3bf56-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf56-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bf56-118">See also</span></span>

- [<span data-ttu-id="3bf56-119">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="3bf56-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
