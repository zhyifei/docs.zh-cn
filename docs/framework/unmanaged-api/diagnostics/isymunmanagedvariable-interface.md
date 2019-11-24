---
title: ISymUnmanagedVariable 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: ee57ba14f048032e2cd9d0129089743c0f0304bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445975"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="30588-102">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="30588-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="30588-103">Represents a variable, such as a parameter, a local variable, or a field.</span><span class="sxs-lookup"><span data-stu-id="30588-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30588-104">方法</span><span class="sxs-lookup"><span data-stu-id="30588-104">Methods</span></span>  
  
|<span data-ttu-id="30588-105">方法</span><span class="sxs-lookup"><span data-stu-id="30588-105">Method</span></span>|<span data-ttu-id="30588-106">描述</span><span class="sxs-lookup"><span data-stu-id="30588-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30588-107">GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="30588-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="30588-108">Gets the first address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="30588-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="30588-109">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="30588-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="30588-110">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="30588-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="30588-111">Gets the second address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="30588-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="30588-112">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="30588-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="30588-113">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="30588-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="30588-114">Gets the third address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="30588-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="30588-115">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="30588-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="30588-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="30588-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="30588-117">Gets the kind of address of this variable.</span><span class="sxs-lookup"><span data-stu-id="30588-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="30588-118">GetAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="30588-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="30588-119">Gets the attribute flags for this variable.</span><span class="sxs-lookup"><span data-stu-id="30588-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="30588-120">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="30588-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="30588-121">Gets the end offset of this variable within its parent.</span><span class="sxs-lookup"><span data-stu-id="30588-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="30588-122">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="30588-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="30588-123">Gets the name of this variable.</span><span class="sxs-lookup"><span data-stu-id="30588-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="30588-124">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="30588-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="30588-125">Gets the signature of this variable.</span><span class="sxs-lookup"><span data-stu-id="30588-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="30588-126">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="30588-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="30588-127">Gets the start offset of this variable within its parent.</span><span class="sxs-lookup"><span data-stu-id="30588-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30588-128">要求</span><span class="sxs-lookup"><span data-stu-id="30588-128">Requirements</span></span>  
 <span data-ttu-id="30588-129">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="30588-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30588-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="30588-130">See also</span></span>

- [<span data-ttu-id="30588-131">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="30588-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
