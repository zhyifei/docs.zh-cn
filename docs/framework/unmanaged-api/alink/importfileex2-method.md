---
title: ImportFileEx2 方法
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 784e58e0c5c2329705671580d53763f2ac30f0b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753474"
---
# <a name="importfileex2-method"></a><span data-ttu-id="f0858-102">ImportFileEx2 方法</span><span class="sxs-lookup"><span data-stu-id="f0858-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="f0858-103">导入程序集和未绑定的模块。</span><span class="sxs-lookup"><span data-stu-id="f0858-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="f0858-104">此方法就像[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)，但仍可正常工作磁盘上不存在要导入的文件。</span><span class="sxs-lookup"><span data-stu-id="f0858-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0858-105">语法</span><span class="sxs-lookup"><span data-stu-id="f0858-105">Syntax</span></span>  
  
```  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0858-106">参数</span><span class="sxs-lookup"><span data-stu-id="f0858-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="f0858-107">要导入文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f0858-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="f0858-108">可选目标文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f0858-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="f0858-109">可选的导入作用域[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f0858-109">Optional import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="f0858-110">如果为 TRUE，则使用 ImportTypes 时，必须手动执行否则导入。</span><span class="sxs-lookup"><span data-stu-id="f0858-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="f0858-111">要传递到标志[OpenScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)。</span><span class="sxs-lookup"><span data-stu-id="f0858-111">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="f0858-112">接收的程序集或文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f0858-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="f0858-113">接收程序集导入范围[IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f0858-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="f0858-114">如果该文件不是程序集，可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f0858-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="f0858-115">接收文件和/或导入的作用域的数。</span><span class="sxs-lookup"><span data-stu-id="f0858-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0858-116">返回值</span><span class="sxs-lookup"><span data-stu-id="f0858-116">Return Value</span></span>  
 <span data-ttu-id="f0858-117">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f0858-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0858-118">要求</span><span class="sxs-lookup"><span data-stu-id="f0858-118">Requirements</span></span>  
 <span data-ttu-id="f0858-119">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="f0858-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0858-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0858-120">See also</span></span>

- [<span data-ttu-id="f0858-121">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="f0858-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f0858-122">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="f0858-122">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f0858-123">ALink API</span><span class="sxs-lookup"><span data-stu-id="f0858-123">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
