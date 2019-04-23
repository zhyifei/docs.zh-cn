---
title: AssemblyOptions 枚举
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293787d7798768ff2b4e2fb8fec9ed201fdb85ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085410"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="88b6e-102">AssemblyOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="88b6e-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="88b6e-103">枚举的程序集选项。</span><span class="sxs-lookup"><span data-stu-id="88b6e-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88b6e-104">语法</span><span class="sxs-lookup"><span data-stu-id="88b6e-104">Syntax</span></span>  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="88b6e-105">字段</span><span class="sxs-lookup"><span data-stu-id="88b6e-105">Fields</span></span>  
  
|<span data-ttu-id="88b6e-106">字段</span><span class="sxs-lookup"><span data-stu-id="88b6e-106">Field</span></span>|<span data-ttu-id="88b6e-107">描述</span><span class="sxs-lookup"><span data-stu-id="88b6e-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="88b6e-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="88b6e-108">optAssemTitle</span></span>|<span data-ttu-id="88b6e-109">字符串--表示程序集标题。</span><span class="sxs-lookup"><span data-stu-id="88b6e-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="88b6e-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="88b6e-110">optAssemDescription</span></span>|<span data-ttu-id="88b6e-111">字符串--包含程序集说明。</span><span class="sxs-lookup"><span data-stu-id="88b6e-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="88b6e-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="88b6e-112">optAssemConfig</span></span>|<span data-ttu-id="88b6e-113">字符串--包含程序集配置。</span><span class="sxs-lookup"><span data-stu-id="88b6e-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="88b6e-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="88b6e-114">optAssemOS</span></span>|<span data-ttu-id="88b6e-115">字符串-编码为:"dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion"。</span><span class="sxs-lookup"><span data-stu-id="88b6e-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="88b6e-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="88b6e-116">optAssemProcessor</span></span>|<span data-ttu-id="88b6e-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="88b6e-117">ULONG</span></span>|  
|<span data-ttu-id="88b6e-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="88b6e-118">optAssemLocale</span></span>|<span data-ttu-id="88b6e-119">字符串--包含程序集的区域设置。</span><span class="sxs-lookup"><span data-stu-id="88b6e-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="88b6e-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="88b6e-120">optAssemVersion</span></span>|<span data-ttu-id="88b6e-121">字符串-编码为："Major.Minor.Build.Revision"。</span><span class="sxs-lookup"><span data-stu-id="88b6e-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="88b6e-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="88b6e-122">optAssemCompany</span></span>|<span data-ttu-id="88b6e-123">字符串--包含公司。</span><span class="sxs-lookup"><span data-stu-id="88b6e-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="88b6e-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="88b6e-124">optAssemProduct</span></span>|<span data-ttu-id="88b6e-125">字符串--包含产品名称。</span><span class="sxs-lookup"><span data-stu-id="88b6e-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="88b6e-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="88b6e-126">optAssemProductVersion</span></span>|<span data-ttu-id="88b6e-127">字符串 (也称为 InformationalVersion)。</span><span class="sxs-lookup"><span data-stu-id="88b6e-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="88b6e-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="88b6e-128">optAssemCopyright</span></span>|<span data-ttu-id="88b6e-129">字符串--包含的版权信息。</span><span class="sxs-lookup"><span data-stu-id="88b6e-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="88b6e-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="88b6e-130">optAssemTrademark</span></span>|<span data-ttu-id="88b6e-131">字符串--包含商标信息。</span><span class="sxs-lookup"><span data-stu-id="88b6e-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="88b6e-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="88b6e-132">optAssemKeyFile</span></span>|<span data-ttu-id="88b6e-133">字符串 （文件名）。</span><span class="sxs-lookup"><span data-stu-id="88b6e-133">String (file name).</span></span>|  
|<span data-ttu-id="88b6e-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="88b6e-134">optAssemKeyName</span></span>|<span data-ttu-id="88b6e-135">字符串 （项名）。</span><span class="sxs-lookup"><span data-stu-id="88b6e-135">String (The key name).</span></span>|  
|<span data-ttu-id="88b6e-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="88b6e-136">optAssemAlgID</span></span>|<span data-ttu-id="88b6e-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="88b6e-137">ULONG</span></span>|  
|<span data-ttu-id="88b6e-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="88b6e-138">optAssemFlags</span></span>|<span data-ttu-id="88b6e-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="88b6e-139">ULONG</span></span>|  
|<span data-ttu-id="88b6e-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="88b6e-140">optAssemHalfSign</span></span>|<span data-ttu-id="88b6e-141">Bool （也称为 DelaySign）。</span><span class="sxs-lookup"><span data-stu-id="88b6e-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="88b6e-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="88b6e-142">optAssemFileVersion</span></span>|<span data-ttu-id="88b6e-143">字符串-编码为"Major.Minor.Build.Revision"-ProductVersion 相同。</span><span class="sxs-lookup"><span data-stu-id="88b6e-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="88b6e-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="88b6e-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="88b6e-145">字符串-编码为"Major.Minor.Build.Revision"。</span><span class="sxs-lookup"><span data-stu-id="88b6e-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="88b6e-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="88b6e-146">optLastAssemOption</span></span>|<span data-ttu-id="88b6e-147">元素数的计数器。</span><span class="sxs-lookup"><span data-stu-id="88b6e-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88b6e-148">要求</span><span class="sxs-lookup"><span data-stu-id="88b6e-148">Requirements</span></span>  
 <span data-ttu-id="88b6e-149">**标头：** alink.h</span><span class="sxs-lookup"><span data-stu-id="88b6e-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="88b6e-150">**库**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="88b6e-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b6e-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="88b6e-151">See also</span></span>

- [<span data-ttu-id="88b6e-152">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="88b6e-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
