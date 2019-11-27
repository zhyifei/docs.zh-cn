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
ms.openlocfilehash: 8477f53bec44675d7cb0a9bc6c4f11097a4fcc87
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446155"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="a8513-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath 方法</span><span class="sxs-lookup"><span data-stu-id="a8513-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="a8513-103">获取搜索路径。</span><span class="sxs-lookup"><span data-stu-id="a8513-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8513-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8513-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8513-105">参数</span><span class="sxs-lookup"><span data-stu-id="a8513-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="a8513-106">弄指向 `ULONG32` 的指针，该指针接收包含搜索路径所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="a8513-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8513-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a8513-107">Return Value</span></span>  
 <span data-ttu-id="a8513-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="a8513-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8513-109">要求</span><span class="sxs-lookup"><span data-stu-id="a8513-109">Requirements</span></span>  
 <span data-ttu-id="a8513-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="a8513-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8513-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8513-111">See also</span></span>

- [<span data-ttu-id="a8513-112">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="a8513-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
