---
title: ISymUnmanagedWriter::DefineParameter 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b552ef39c7f73aaa5cfeae4a313e329b267abf98
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643381"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="9d2c6-102">ISymUnmanagedWriter::DefineParameter 方法</span><span class="sxs-lookup"><span data-stu-id="9d2c6-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="9d2c6-103">当前方法中定义的单个参数。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="9d2c6-104">从参数的位置 （序列） 的方法签名中获取参数类型。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="9d2c6-105">如果给定方法的元数据中定义参数，则无需再次使用此方法定义。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="9d2c6-106">符号读取器必须检查符号存储区之前检查参数的普通元数据。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d2c6-107">语法</span><span class="sxs-lookup"><span data-stu-id="9d2c6-107">Syntax</span></span>  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d2c6-108">参数</span><span class="sxs-lookup"><span data-stu-id="9d2c6-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9d2c6-109">[in]参数名称。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="9d2c6-110">[in]参数属性。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="9d2c6-111">[in]参数签名。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="9d2c6-112">[in]地址类型。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="9d2c6-113">[in]参数规格的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="9d2c6-114">[in]参数规格的第二个地址。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="9d2c6-115">[in]参数规格的第三个地址。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d2c6-116">返回值</span><span class="sxs-lookup"><span data-stu-id="9d2c6-116">Return Value</span></span>  
 <span data-ttu-id="9d2c6-117">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="9d2c6-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d2c6-118">要求</span><span class="sxs-lookup"><span data-stu-id="9d2c6-118">Requirements</span></span>  
 <span data-ttu-id="9d2c6-119">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9d2c6-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d2c6-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d2c6-120">See also</span></span>
- [<span data-ttu-id="9d2c6-121">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="9d2c6-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
