---
title: ISymUnmanagedWriter::DefineField 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5fd9798b3681d66e71d5703f4d16564b153da07b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789625"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="0dee2-102">ISymUnmanagedWriter::DefineField 方法</span><span class="sxs-lookup"><span data-stu-id="0dee2-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="0dee2-103">定义一个不在方法内的变量。</span><span class="sxs-lookup"><span data-stu-id="0dee2-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="0dee2-104">此方法是使用类中的某些字段、 位域等。</span><span class="sxs-lookup"><span data-stu-id="0dee2-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dee2-105">语法</span><span class="sxs-lookup"><span data-stu-id="0dee2-105">Syntax</span></span>  
  
```  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dee2-106">参数</span><span class="sxs-lookup"><span data-stu-id="0dee2-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="0dee2-107">[in]元数据类型或方法令牌。</span><span class="sxs-lookup"><span data-stu-id="0dee2-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="0dee2-108">[in]字段名称。</span><span class="sxs-lookup"><span data-stu-id="0dee2-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="0dee2-109">[in]字段特性。</span><span class="sxs-lookup"><span data-stu-id="0dee2-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="0dee2-110">[in]一个`ULONG32`，它是大小，以字符为单位，包含字段签名所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0dee2-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="0dee2-111">[in]字段签名的数组。</span><span class="sxs-lookup"><span data-stu-id="0dee2-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="0dee2-112">[in]地址类型。</span><span class="sxs-lookup"><span data-stu-id="0dee2-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="0dee2-113">[in]字段规格的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="0dee2-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="0dee2-114">[in]字段规格的第二个地址。</span><span class="sxs-lookup"><span data-stu-id="0dee2-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="0dee2-115">[in]字段规格的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="0dee2-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0dee2-116">返回值</span><span class="sxs-lookup"><span data-stu-id="0dee2-116">Return Value</span></span>  
 <span data-ttu-id="0dee2-117">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="0dee2-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dee2-118">要求</span><span class="sxs-lookup"><span data-stu-id="0dee2-118">Requirements</span></span>  
 <span data-ttu-id="0dee2-119">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0dee2-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dee2-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0dee2-120">See also</span></span>

- [<span data-ttu-id="0dee2-121">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="0dee2-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
