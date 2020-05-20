---
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: bba0fc039c403d45e8a5b60f2b0231eb24226280
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614950"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="e40f9-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition 方法</span><span class="sxs-lookup"><span data-stu-id="e40f9-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="e40f9-103">返回一组方法，其中每个方法都包含文档中给定位置处的断点。</span><span class="sxs-lookup"><span data-stu-id="e40f9-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e40f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="e40f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e40f9-105">参数</span><span class="sxs-lookup"><span data-stu-id="e40f9-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="e40f9-106">中指定的文档。</span><span class="sxs-lookup"><span data-stu-id="e40f9-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="e40f9-107">中指定文档的行。</span><span class="sxs-lookup"><span data-stu-id="e40f9-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="e40f9-108">中指定文档的列。</span><span class="sxs-lookup"><span data-stu-id="e40f9-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="e40f9-109">[in] `pRetVal` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="e40f9-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="e40f9-110">弄指向一个变量的指针，该变量接收数组中返回的元素的数目 `pRetVal` 。</span><span class="sxs-lookup"><span data-stu-id="e40f9-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e40f9-111">弄指针的数组，其中每个都指向表示包含断点的方法的[ISymUnmanagedMethod](isymunmanagedmethod-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="e40f9-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e40f9-112">返回值</span><span class="sxs-lookup"><span data-stu-id="e40f9-112">Return Value</span></span>  
 <span data-ttu-id="e40f9-113">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="e40f9-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e40f9-114">要求</span><span class="sxs-lookup"><span data-stu-id="e40f9-114">Requirements</span></span>  
 <span data-ttu-id="e40f9-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="e40f9-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e40f9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e40f9-116">See also</span></span>

- [<span data-ttu-id="e40f9-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="e40f9-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
