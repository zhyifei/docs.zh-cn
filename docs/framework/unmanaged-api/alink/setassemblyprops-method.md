---
title: SetAssemblyProps 方法
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 589bd7b2132693c89dc10ae1a5c8d0bf52ed481e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218987"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="b2c59-102">SetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="b2c59-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="b2c59-103">将分配的程序集级别的属性。</span><span class="sxs-lookup"><span data-stu-id="b2c59-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c59-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2c59-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2c59-105">参数</span><span class="sxs-lookup"><span data-stu-id="b2c59-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b2c59-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="b2c59-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b2c59-107">定义属性的文件。</span><span class="sxs-lookup"><span data-stu-id="b2c59-107">File that defines the property.</span></span> <span data-ttu-id="b2c59-108">可以为 NULL，如果`AssemblyID`并不表示未绑定的 netmodule。</span><span class="sxs-lookup"><span data-stu-id="b2c59-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="b2c59-109">指示要修改的选项。</span><span class="sxs-lookup"><span data-stu-id="b2c59-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="b2c59-110">选项的新值。</span><span class="sxs-lookup"><span data-stu-id="b2c59-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2c59-111">返回值</span><span class="sxs-lookup"><span data-stu-id="b2c59-111">Return Value</span></span>  
 <span data-ttu-id="b2c59-112">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b2c59-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2c59-113">要求</span><span class="sxs-lookup"><span data-stu-id="b2c59-113">Requirements</span></span>  
 <span data-ttu-id="b2c59-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="b2c59-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2c59-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2c59-115">See also</span></span>

- [<span data-ttu-id="b2c59-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="b2c59-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b2c59-117">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="b2c59-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b2c59-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="b2c59-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
