---
title: ImportFile 方法
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69e48c6c3179ced167fdc39ae4df859f161727ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077246"
---
# <a name="importfile-method"></a><span data-ttu-id="d9503-102">ImportFile 方法</span><span class="sxs-lookup"><span data-stu-id="d9503-102">ImportFile Method</span></span>
<span data-ttu-id="d9503-103">导入程序集和未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="d9503-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9503-104">语法</span><span class="sxs-lookup"><span data-stu-id="d9503-104">Syntax</span></span>  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9503-105">参数</span><span class="sxs-lookup"><span data-stu-id="d9503-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="d9503-106">要导入文件的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="d9503-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="d9503-107">可用于重命名该文件并将其链接到该程序集的可选的输出文件名称。</span><span class="sxs-lookup"><span data-stu-id="d9503-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="d9503-108">如果为 TRUE，则使用 ImportTypes 时，必须手动执行否则导入。</span><span class="sxs-lookup"><span data-stu-id="d9503-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="d9503-109">用于令牌存储唯一的文件 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="d9503-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="d9503-110">文件可以是程序集或文件。</span><span class="sxs-lookup"><span data-stu-id="d9503-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="d9503-111">接收指向[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="d9503-111">Receives pointer to [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="d9503-112">如果该文件不是程序集，可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d9503-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="d9503-113">指向的文件和/或已导入的作用域的计数。</span><span class="sxs-lookup"><span data-stu-id="d9503-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9503-114">返回值</span><span class="sxs-lookup"><span data-stu-id="d9503-114">Return Value</span></span>  
 <span data-ttu-id="d9503-115">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="d9503-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9503-116">要求</span><span class="sxs-lookup"><span data-stu-id="d9503-116">Requirements</span></span>  
 <span data-ttu-id="d9503-117">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="d9503-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9503-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9503-118">See also</span></span>

- [<span data-ttu-id="d9503-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="d9503-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d9503-120">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="d9503-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d9503-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="d9503-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
