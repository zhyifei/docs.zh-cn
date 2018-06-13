---
title: CreateALink 函数
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e29c9c246649229900beba2fcc9ab482071ae46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400661"
---
# <a name="createalink-function"></a><span data-ttu-id="6c6d2-102">CreateALink 函数</span><span class="sxs-lookup"><span data-stu-id="6c6d2-102">CreateALink Function</span></span>
<span data-ttu-id="6c6d2-103">创建的程序集链接器实例并设置为指定接口的指针。</span><span class="sxs-lookup"><span data-stu-id="6c6d2-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c6d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="6c6d2-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c6d2-105">参数</span><span class="sxs-lookup"><span data-stu-id="6c6d2-105">Parameters</span></span>  
  
|<span data-ttu-id="6c6d2-106">参数</span><span class="sxs-lookup"><span data-stu-id="6c6d2-106">Parameter</span></span>|<span data-ttu-id="6c6d2-107">描述</span><span class="sxs-lookup"><span data-stu-id="6c6d2-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="6c6d2-108">一个程序集链接器接口的物理名称。</span><span class="sxs-lookup"><span data-stu-id="6c6d2-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="6c6d2-109">在成功完成，包含的指针的位置`riid`接口。</span><span class="sxs-lookup"><span data-stu-id="6c6d2-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c6d2-110">要求</span><span class="sxs-lookup"><span data-stu-id="6c6d2-110">Requirements</span></span>  
 <span data-ttu-id="6c6d2-111">**库**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="6c6d2-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c6d2-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c6d2-112">See Also</span></span>  
 [<span data-ttu-id="6c6d2-113">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="6c6d2-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
