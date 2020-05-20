---
title: ISymUnmanagedScope::GetEndOffset 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: 4d6bd239a15bd196f840007af120cb062499f4c9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614846"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="9fbf3-102">ISymUnmanagedScope::GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="9fbf3-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="9fbf3-103">获取此范围的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="9fbf3-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fbf3-104">语法</span><span class="sxs-lookup"><span data-stu-id="9fbf3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fbf3-105">参数</span><span class="sxs-lookup"><span data-stu-id="9fbf3-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="9fbf3-106">弄指向的指针 `ULONG32` ，该指针接收结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="9fbf3-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fbf3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="9fbf3-107">Return Value</span></span>  
 <span data-ttu-id="9fbf3-108">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="9fbf3-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fbf3-109">要求</span><span class="sxs-lookup"><span data-stu-id="9fbf3-109">Requirements</span></span>  
 <span data-ttu-id="9fbf3-110">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="9fbf3-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fbf3-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fbf3-111">See also</span></span>

- [<span data-ttu-id="9fbf3-112">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="9fbf3-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="9fbf3-113">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="9fbf3-113">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)
