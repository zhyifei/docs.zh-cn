---
title: ISymUnmanagedWriter::DefineConstant 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a04bf93a2b2809198673d15f29714f52c9435b68
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767838"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="e41da-102">ISymUnmanagedWriter::DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="e41da-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="e41da-103">定义常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="e41da-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e41da-104">语法</span><span class="sxs-lookup"><span data-stu-id="e41da-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e41da-105">参数</span><span class="sxs-lookup"><span data-stu-id="e41da-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e41da-106">[in]一个指向`WCHAR`，用于定义该常量的名称。</span><span class="sxs-lookup"><span data-stu-id="e41da-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="e41da-107">[in]常量的值。</span><span class="sxs-lookup"><span data-stu-id="e41da-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="e41da-108">[in] `signature` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="e41da-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="e41da-109">[in]常量类型签名。</span><span class="sxs-lookup"><span data-stu-id="e41da-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e41da-110">返回值</span><span class="sxs-lookup"><span data-stu-id="e41da-110">Return Value</span></span>  
 <span data-ttu-id="e41da-111">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e41da-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e41da-112">要求</span><span class="sxs-lookup"><span data-stu-id="e41da-112">Requirements</span></span>  
 <span data-ttu-id="e41da-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e41da-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41da-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e41da-114">See also</span></span>

- [<span data-ttu-id="e41da-115">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="e41da-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e41da-116">DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="e41da-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
