---
title: ImportFileEx 方法
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b3cf91ad4e048ddfccb4086f36923f33d754ac0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131035"
---
# <a name="importfileex-method"></a><span data-ttu-id="e6000-102">ImportFileEx 方法</span><span class="sxs-lookup"><span data-stu-id="e6000-102">ImportFileEx Method</span></span>
<span data-ttu-id="e6000-103">导入指定的程序集或未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="e6000-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6000-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6000-104">Syntax</span></span>  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6000-105">参数</span><span class="sxs-lookup"><span data-stu-id="e6000-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="e6000-106">要从中导入的文件的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="e6000-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="e6000-107">可选目标文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e6000-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="e6000-108">如果为 TRUE，则使用 ImportTypes 时，必须手动执行否则导入。</span><span class="sxs-lookup"><span data-stu-id="e6000-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="e6000-109">要传递到标志[OpenScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)。</span><span class="sxs-lookup"><span data-stu-id="e6000-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="e6000-110">接收要导入的文件 ID。</span><span class="sxs-lookup"><span data-stu-id="e6000-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="e6000-111">接收程序集导入范围[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e6000-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="e6000-112">如果文件不是程序集，则设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e6000-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="e6000-113">接收数量的导入的文件和/或作用域。</span><span class="sxs-lookup"><span data-stu-id="e6000-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6000-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e6000-114">Return Value</span></span>  
 <span data-ttu-id="e6000-115">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="e6000-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6000-116">要求</span><span class="sxs-lookup"><span data-stu-id="e6000-116">Requirements</span></span>  
 <span data-ttu-id="e6000-117">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="e6000-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6000-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6000-118">See also</span></span>

- [<span data-ttu-id="e6000-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="e6000-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e6000-120">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="e6000-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e6000-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="e6000-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
