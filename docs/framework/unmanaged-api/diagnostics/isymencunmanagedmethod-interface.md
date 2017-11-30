---
title: "ISymENCUnmanagedMethod 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod
helpviewer_keywords: ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 68929dc30b029133c73f18c3749f39f014359c0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="ff833-102">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="ff833-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="ff833-103">提供的编辑并继续功能的信息。</span><span class="sxs-lookup"><span data-stu-id="ff833-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff833-104">方法</span><span class="sxs-lookup"><span data-stu-id="ff833-104">Methods</span></span>  
  
|<span data-ttu-id="ff833-105">方法</span><span class="sxs-lookup"><span data-stu-id="ff833-105">Method</span></span>|<span data-ttu-id="ff833-106">描述</span><span class="sxs-lookup"><span data-stu-id="ff833-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff833-107">GetDocumentsForMethod 方法</span><span class="sxs-lookup"><span data-stu-id="ff833-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="ff833-108">获取此方法的行中的文档。</span><span class="sxs-lookup"><span data-stu-id="ff833-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="ff833-109">GetDocumentsForMethodCount 方法</span><span class="sxs-lookup"><span data-stu-id="ff833-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="ff833-110">获取此方法的行中的文档数。</span><span class="sxs-lookup"><span data-stu-id="ff833-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="ff833-111">GetFileNameFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="ff833-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="ff833-112">获取与偏移量关联的行的文件名称。</span><span class="sxs-lookup"><span data-stu-id="ff833-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="ff833-113">GetLineFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="ff833-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="ff833-114">获取与某一偏移量关联的行信息。</span><span class="sxs-lookup"><span data-stu-id="ff833-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="ff833-115">GetSourceExtentInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="ff833-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="ff833-116">获取最小值中特定文档开始行和方法的最大结束行。</span><span class="sxs-lookup"><span data-stu-id="ff833-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff833-117">要求</span><span class="sxs-lookup"><span data-stu-id="ff833-117">Requirements</span></span>  
 <span data-ttu-id="ff833-118">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ff833-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff833-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff833-119">See Also</span></span>  
 [<span data-ttu-id="ff833-120">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="ff833-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
