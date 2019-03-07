---
title: AddFile2 方法
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c595f59905a369c206da2fa011038d0d95041fa4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500676"
---
# <a name="addfile2-method"></a><span data-ttu-id="de08a-102">AddFile2 方法</span><span class="sxs-lookup"><span data-stu-id="de08a-102">AddFile2 Method</span></span>
<span data-ttu-id="de08a-103">将文件添加到该程序集。</span><span class="sxs-lookup"><span data-stu-id="de08a-103">Adds files to the assembly.</span></span> <span data-ttu-id="de08a-104">此外可以用于创建未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="de08a-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de08a-105">语法</span><span class="sxs-lookup"><span data-stu-id="de08a-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="de08a-106">参数</span><span class="sxs-lookup"><span data-stu-id="de08a-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="de08a-107">向其中添加文件的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="de08a-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="de08a-108">要添加的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="de08a-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="de08a-109">COM +`FileDef`标志，如`ffContainsNoMetaData`和`ffWriteable`。</span><span class="sxs-lookup"><span data-stu-id="de08a-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="de08a-110">`dwFlags` 传递给[DefineFile 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="de08a-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="de08a-111">接口[IMetaDataEmit2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="de08a-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="de08a-112">接收要添加的文件 ID。</span><span class="sxs-lookup"><span data-stu-id="de08a-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de08a-113">返回值</span><span class="sxs-lookup"><span data-stu-id="de08a-113">Return Value</span></span>  
 <span data-ttu-id="de08a-114">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="de08a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de08a-115">要求</span><span class="sxs-lookup"><span data-stu-id="de08a-115">Requirements</span></span>  
 <span data-ttu-id="de08a-116">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="de08a-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de08a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="de08a-117">See also</span></span>
- [<span data-ttu-id="de08a-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="de08a-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="de08a-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="de08a-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="de08a-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="de08a-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
