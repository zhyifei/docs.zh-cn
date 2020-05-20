---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPath 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
ms.openlocfilehash: d9431a533a32fd15931072cfbabd10bbc0e6d4ad
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610673"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="2a265-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath 方法</span><span class="sxs-lookup"><span data-stu-id="2a265-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="2a265-103">获取搜索路径。</span><span class="sxs-lookup"><span data-stu-id="2a265-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a265-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a265-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a265-105">参数</span><span class="sxs-lookup"><span data-stu-id="2a265-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="2a265-106">弄指向的指针， `ULONG32` 该指针接收包含搜索路径所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="2a265-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a265-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2a265-107">Return Value</span></span>  
 <span data-ttu-id="2a265-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="2a265-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a265-109">要求</span><span class="sxs-lookup"><span data-stu-id="2a265-109">Requirements</span></span>  
 <span data-ttu-id="2a265-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="2a265-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a265-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a265-111">See also</span></span>

- [<span data-ttu-id="2a265-112">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="2a265-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
