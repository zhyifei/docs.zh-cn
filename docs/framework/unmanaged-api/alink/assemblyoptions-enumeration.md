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
ms.openlocfilehash: 49e7b73559e8def890f8df8f596fbe8ad5bb5d3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777483"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="eb224-102">AssemblyOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="eb224-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="eb224-103">枚举程序集选项。</span><span class="sxs-lookup"><span data-stu-id="eb224-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb224-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb224-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="fields"></a><span data-ttu-id="eb224-105">字段</span><span class="sxs-lookup"><span data-stu-id="eb224-105">Fields</span></span>  
  
|<span data-ttu-id="eb224-106">字段</span><span class="sxs-lookup"><span data-stu-id="eb224-106">Field</span></span>|<span data-ttu-id="eb224-107">描述</span><span class="sxs-lookup"><span data-stu-id="eb224-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb224-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="eb224-108">optAssemTitle</span></span>|<span data-ttu-id="eb224-109">String-表示程序集标题。</span><span class="sxs-lookup"><span data-stu-id="eb224-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="eb224-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="eb224-110">optAssemDescription</span></span>|<span data-ttu-id="eb224-111">String-包含程序集说明。</span><span class="sxs-lookup"><span data-stu-id="eb224-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="eb224-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="eb224-112">optAssemConfig</span></span>|<span data-ttu-id="eb224-113">String-包含程序集配置。</span><span class="sxs-lookup"><span data-stu-id="eb224-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="eb224-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="eb224-114">optAssemOS</span></span>|<span data-ttu-id="eb224-115">字符串编码为： "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion"。</span><span class="sxs-lookup"><span data-stu-id="eb224-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="eb224-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="eb224-116">optAssemProcessor</span></span>|<span data-ttu-id="eb224-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="eb224-117">ULONG</span></span>|  
|<span data-ttu-id="eb224-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="eb224-118">optAssemLocale</span></span>|<span data-ttu-id="eb224-119">String-包含程序集的区域设置。</span><span class="sxs-lookup"><span data-stu-id="eb224-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="eb224-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="eb224-120">optAssemVersion</span></span>|<span data-ttu-id="eb224-121">字符串编码为："主要版本. 次要版本. 内部版本. 修订版本"。</span><span class="sxs-lookup"><span data-stu-id="eb224-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="eb224-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="eb224-122">optAssemCompany</span></span>|<span data-ttu-id="eb224-123">String-包含公司。</span><span class="sxs-lookup"><span data-stu-id="eb224-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="eb224-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="eb224-124">optAssemProduct</span></span>|<span data-ttu-id="eb224-125">String-包含产品名称。</span><span class="sxs-lookup"><span data-stu-id="eb224-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="eb224-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="eb224-126">optAssemProductVersion</span></span>|<span data-ttu-id="eb224-127">String （也称为 InformationalVersion）。</span><span class="sxs-lookup"><span data-stu-id="eb224-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="eb224-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="eb224-128">optAssemCopyright</span></span>|<span data-ttu-id="eb224-129">String-包含版权信息。</span><span class="sxs-lookup"><span data-stu-id="eb224-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="eb224-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="eb224-130">optAssemTrademark</span></span>|<span data-ttu-id="eb224-131">String-包含商标信息。</span><span class="sxs-lookup"><span data-stu-id="eb224-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="eb224-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="eb224-132">optAssemKeyFile</span></span>|<span data-ttu-id="eb224-133">字符串（文件名）。</span><span class="sxs-lookup"><span data-stu-id="eb224-133">String (file name).</span></span>|  
|<span data-ttu-id="eb224-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="eb224-134">optAssemKeyName</span></span>|<span data-ttu-id="eb224-135">String （项名称）。</span><span class="sxs-lookup"><span data-stu-id="eb224-135">String (The key name).</span></span>|  
|<span data-ttu-id="eb224-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="eb224-136">optAssemAlgID</span></span>|<span data-ttu-id="eb224-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="eb224-137">ULONG</span></span>|  
|<span data-ttu-id="eb224-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="eb224-138">optAssemFlags</span></span>|<span data-ttu-id="eb224-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="eb224-139">ULONG</span></span>|  
|<span data-ttu-id="eb224-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="eb224-140">optAssemHalfSign</span></span>|<span data-ttu-id="eb224-141">Bool （也称为 DelaySign）。</span><span class="sxs-lookup"><span data-stu-id="eb224-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="eb224-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="eb224-142">optAssemFileVersion</span></span>|<span data-ttu-id="eb224-143">编码为 "ProductVersion" 的字符串，与 "" 相同。</span><span class="sxs-lookup"><span data-stu-id="eb224-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="eb224-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="eb224-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="eb224-145">字符串编码为 "主要版本. 次要版本. 内部版本. 内部版本. 修订版本"。</span><span class="sxs-lookup"><span data-stu-id="eb224-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="eb224-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="eb224-146">optLastAssemOption</span></span>|<span data-ttu-id="eb224-147">元素数的计数器。</span><span class="sxs-lookup"><span data-stu-id="eb224-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb224-148">要求</span><span class="sxs-lookup"><span data-stu-id="eb224-148">Requirements</span></span>  
 <span data-ttu-id="eb224-149">**标头：** alink。h</span><span class="sxs-lookup"><span data-stu-id="eb224-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="eb224-150">**库**： alink</span><span class="sxs-lookup"><span data-stu-id="eb224-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb224-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb224-151">See also</span></span>

- [<span data-ttu-id="eb224-152">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="eb224-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
