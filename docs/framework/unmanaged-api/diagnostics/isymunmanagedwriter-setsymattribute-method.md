---
title: ISymUnmanagedWriter::SetSymAttribute 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd1a55d4100d74b769b2bc1b8fe33d2042f5e739
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428296"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="645d4-102">ISymUnmanagedWriter::SetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="645d4-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="645d4-103">定义基于其名称的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="645d4-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="645d4-104">这些属性保存在符号存储区，与元数据自定义特性不同。</span><span class="sxs-lookup"><span data-stu-id="645d4-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="645d4-105">语法</span><span class="sxs-lookup"><span data-stu-id="645d4-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="645d4-106">参数</span><span class="sxs-lookup"><span data-stu-id="645d4-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="645d4-107">[in]正在为其定义的属性元数据标记。</span><span class="sxs-lookup"><span data-stu-id="645d4-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="645d4-108">[in]指向的指针`WCHAR`，其中包含属性名称。</span><span class="sxs-lookup"><span data-stu-id="645d4-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="645d4-109">[in]A `ULONG32` ，该值指示的大小`data`数组。</span><span class="sxs-lookup"><span data-stu-id="645d4-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="645d4-110">[in]特性值。</span><span class="sxs-lookup"><span data-stu-id="645d4-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="645d4-111">返回值</span><span class="sxs-lookup"><span data-stu-id="645d4-111">Return Value</span></span>  
 <span data-ttu-id="645d4-112">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="645d4-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="645d4-113">要求</span><span class="sxs-lookup"><span data-stu-id="645d4-113">Requirements</span></span>  
 <span data-ttu-id="645d4-114">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="645d4-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645d4-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="645d4-115">See Also</span></span>  
 [<span data-ttu-id="645d4-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="645d4-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
