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
ms.openlocfilehash: 2fe73bef50a32c3ff03f2a2754f665cc95018a4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402989"
---
# <a name="importfileex-method"></a><span data-ttu-id="56048-102">ImportFileEx 方法</span><span class="sxs-lookup"><span data-stu-id="56048-102">ImportFileEx Method</span></span>
<span data-ttu-id="56048-103">导入指定的程序集或未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="56048-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56048-104">语法</span><span class="sxs-lookup"><span data-stu-id="56048-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="56048-105">参数</span><span class="sxs-lookup"><span data-stu-id="56048-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="56048-106">要从中导入的文件的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="56048-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="56048-107">目标文件的可选名称。</span><span class="sxs-lookup"><span data-stu-id="56048-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="56048-108">如果为 TRUE，则使用 ImportTypes，必须手动执行否则导入。</span><span class="sxs-lookup"><span data-stu-id="56048-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="56048-109">要传递到标志[OpenScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)。</span><span class="sxs-lookup"><span data-stu-id="56048-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="56048-110">接收要导入的文件 ID。</span><span class="sxs-lookup"><span data-stu-id="56048-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="56048-111">接收程序集导入作用域[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="56048-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="56048-112">如果文件不是程序集，是设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="56048-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="56048-113">接收的导入的文件和/或作用域的数量。</span><span class="sxs-lookup"><span data-stu-id="56048-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56048-114">返回值</span><span class="sxs-lookup"><span data-stu-id="56048-114">Return Value</span></span>  
 <span data-ttu-id="56048-115">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="56048-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56048-116">要求</span><span class="sxs-lookup"><span data-stu-id="56048-116">Requirements</span></span>  
 <span data-ttu-id="56048-117">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="56048-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56048-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="56048-118">See Also</span></span>  
 [<span data-ttu-id="56048-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="56048-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="56048-120">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="56048-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="56048-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="56048-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
