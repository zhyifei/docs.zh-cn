---
title: ICeeGen 接口
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c5dadbe757464b24ef532fdd8abe5457fa995348
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555058"
---
# <a name="iceegen-interface"></a><span data-ttu-id="8bf7c-102">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="8bf7c-102">ICeeGen Interface</span></span>
<span data-ttu-id="8bf7c-103">提供用于动态代码编译的方法。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="8bf7c-104">此接口已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8bf7c-105">方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-105">Methods</span></span>  
  
|<span data-ttu-id="8bf7c-106">方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-106">Method</span></span>|<span data-ttu-id="8bf7c-107">描述</span><span class="sxs-lookup"><span data-stu-id="8bf7c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8bf7c-108">AddSectionReloc 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-108">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|<span data-ttu-id="8bf7c-109">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-109">Obsolete.</span></span> <span data-ttu-id="8bf7c-110">将.reloc 指令添加到基本代码。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="8bf7c-111">AllocateMethodBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-111">AllocateMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="8bf7c-112">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-112">Obsolete.</span></span> <span data-ttu-id="8bf7c-113">创建一个方法，为指定的大小的缓冲区并获取该方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="8bf7c-114">ComputePointer 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-114">ComputePointer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|<span data-ttu-id="8bf7c-115">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-115">Obsolete.</span></span> <span data-ttu-id="8bf7c-116">确定指定的代码部分的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="8bf7c-117">EmitString 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-117">EmitString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|<span data-ttu-id="8bf7c-118">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-118">Obsolete.</span></span> <span data-ttu-id="8bf7c-119">将指定的字符串发出到基本代码。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="8bf7c-120">GenerateCeeFile 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-120">GenerateCeeFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|<span data-ttu-id="8bf7c-121">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-121">Obsolete.</span></span> <span data-ttu-id="8bf7c-122">生成包含当前加载到此代码的基本代码文件`ICeeGen`。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="8bf7c-123">GenerateCeeMemoryImage 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-123">GenerateCeeMemoryImage Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|<span data-ttu-id="8bf7c-124">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-124">Obsolete.</span></span> <span data-ttu-id="8bf7c-125">在基本代码的内存中生成的映像。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="8bf7c-126">GetIlSection 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-126">GetIlSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|<span data-ttu-id="8bf7c-127">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-127">Obsolete.</span></span> <span data-ttu-id="8bf7c-128">获取由指定句柄引用的基的中间语言代码的节。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="8bf7c-129">GetIMapTokenIface 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-129">GetIMapTokenIface Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|<span data-ttu-id="8bf7c-130">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-130">Obsolete.</span></span> <span data-ttu-id="8bf7c-131">获取指定的标记所引用的接口。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="8bf7c-132">GetMethodBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-132">GetMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|<span data-ttu-id="8bf7c-133">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-133">Obsolete.</span></span> <span data-ttu-id="8bf7c-134">获取在指定的相对虚拟地址的方法的适当大小的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="8bf7c-135">GetSectionBlock 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-135">GetSectionBlock Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|<span data-ttu-id="8bf7c-136">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-136">Obsolete.</span></span> <span data-ttu-id="8bf7c-137">获取基本代码的部分块。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="8bf7c-138">GetSectionCreate 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-138">GetSectionCreate Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|<span data-ttu-id="8bf7c-139">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-139">Obsolete.</span></span> <span data-ttu-id="8bf7c-140">生成并获取使用指定的名称和标记值的代码节。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="8bf7c-141">GetSectionDataLen 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-141">GetSectionDataLen Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|<span data-ttu-id="8bf7c-142">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-142">Obsolete.</span></span> <span data-ttu-id="8bf7c-143">获取指定的节的长度。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="8bf7c-144">GetString 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-144">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|<span data-ttu-id="8bf7c-145">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-145">Obsolete.</span></span> <span data-ttu-id="8bf7c-146">获取存储在指定的相对虚拟地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="8bf7c-147">GetStringSection 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-147">GetStringSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|<span data-ttu-id="8bf7c-148">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-148">Obsolete.</span></span> <span data-ttu-id="8bf7c-149">获取由指定句柄引用的代码部分的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="8bf7c-150">TruncateSection 方法</span><span class="sxs-lookup"><span data-stu-id="8bf7c-150">TruncateSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|<span data-ttu-id="8bf7c-151">已过时。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-151">Obsolete.</span></span> <span data-ttu-id="8bf7c-152">通过指定长度截断指定的代码部分。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8bf7c-153">要求</span><span class="sxs-lookup"><span data-stu-id="8bf7c-153">Requirements</span></span>  
 <span data-ttu-id="8bf7c-154">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8bf7c-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bf7c-155">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8bf7c-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bf7c-156">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8bf7c-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8bf7c-157">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bf7c-157">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf7c-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bf7c-158">See also</span></span>
- [<span data-ttu-id="8bf7c-159">元数据接口</span><span class="sxs-lookup"><span data-stu-id="8bf7c-159">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
