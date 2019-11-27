---
title: ISymENCUnmanagedMethod 接口
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: 47477bb473df8b568844d07bea704df681c9b95d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448606"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="3b01b-102">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="3b01b-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="3b01b-103">提供 "编辑并继续" 功能的信息。</span><span class="sxs-lookup"><span data-stu-id="3b01b-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b01b-104">方法</span><span class="sxs-lookup"><span data-stu-id="3b01b-104">Methods</span></span>  
  
|<span data-ttu-id="3b01b-105">方法</span><span class="sxs-lookup"><span data-stu-id="3b01b-105">Method</span></span>|<span data-ttu-id="3b01b-106">说明</span><span class="sxs-lookup"><span data-stu-id="3b01b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b01b-107">GetDocumentsForMethod 方法</span><span class="sxs-lookup"><span data-stu-id="3b01b-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="3b01b-108">获取此方法在中具有线条的文档。</span><span class="sxs-lookup"><span data-stu-id="3b01b-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="3b01b-109">GetDocumentsForMethodCount 方法</span><span class="sxs-lookup"><span data-stu-id="3b01b-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="3b01b-110">获取此方法在中包含行的文档数。</span><span class="sxs-lookup"><span data-stu-id="3b01b-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="3b01b-111">GetFileNameFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="3b01b-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="3b01b-112">获取与偏移量关联的行的文件名。</span><span class="sxs-lookup"><span data-stu-id="3b01b-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="3b01b-113">GetLineFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="3b01b-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="3b01b-114">获取与偏移量关联的行信息。</span><span class="sxs-lookup"><span data-stu-id="3b01b-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="3b01b-115">GetSourceExtentInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="3b01b-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="3b01b-116">获取特定文档中该方法的最小起始行和最大结束行。</span><span class="sxs-lookup"><span data-stu-id="3b01b-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b01b-117">要求</span><span class="sxs-lookup"><span data-stu-id="3b01b-117">Requirements</span></span>  
 <span data-ttu-id="3b01b-118">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="3b01b-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b01b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b01b-119">See also</span></span>

- [<span data-ttu-id="3b01b-120">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="3b01b-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
