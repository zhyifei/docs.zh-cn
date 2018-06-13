---
title: CorTypeAttr 枚举
ms.date: 03/30/2017
api_name:
- CorTypeAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTypeAttr
helpviewer_keywords:
- CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f71e59eb13321517de61315d3ba06b96c5458f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449268"
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="0584a-102">CorTypeAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="0584a-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="0584a-103">包含一些值，用于指示类型元数据。</span><span class="sxs-lookup"><span data-stu-id="0584a-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0584a-104">语法</span><span class="sxs-lookup"><span data-stu-id="0584a-104">Syntax</span></span>  
  
```  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="0584a-105">成员</span><span class="sxs-lookup"><span data-stu-id="0584a-105">Members</span></span>  
  
|<span data-ttu-id="0584a-106">成员</span><span class="sxs-lookup"><span data-stu-id="0584a-106">Member</span></span>|<span data-ttu-id="0584a-107">描述</span><span class="sxs-lookup"><span data-stu-id="0584a-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="0584a-108">用于类型可见性信息。</span><span class="sxs-lookup"><span data-stu-id="0584a-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="0584a-109">指定的类型不是在公共范围内。</span><span class="sxs-lookup"><span data-stu-id="0584a-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="0584a-110">指定的类型是公共的作用域中。</span><span class="sxs-lookup"><span data-stu-id="0584a-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="0584a-111">指定该类型嵌套用公共可见性。</span><span class="sxs-lookup"><span data-stu-id="0584a-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="0584a-112">指定该类型嵌套用私有可见性。</span><span class="sxs-lookup"><span data-stu-id="0584a-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="0584a-113">指定该类型用族可见性嵌套。</span><span class="sxs-lookup"><span data-stu-id="0584a-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="0584a-114">指定该类型嵌套具有程序集可见性。</span><span class="sxs-lookup"><span data-stu-id="0584a-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="0584a-115">指定该类型用族和程序集可见性嵌套。</span><span class="sxs-lookup"><span data-stu-id="0584a-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="0584a-116">指定该类型用族或程序集可见性嵌套。</span><span class="sxs-lookup"><span data-stu-id="0584a-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="0584a-117">获取类型的布局信息。</span><span class="sxs-lookup"><span data-stu-id="0584a-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="0584a-118">指定此类型的字段自动布局。</span><span class="sxs-lookup"><span data-stu-id="0584a-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="0584a-119">指定此类型的字段按顺序放置。</span><span class="sxs-lookup"><span data-stu-id="0584a-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="0584a-120">指定显式提供该字段布局。</span><span class="sxs-lookup"><span data-stu-id="0584a-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="0584a-121">获取有关类型的语义信息。</span><span class="sxs-lookup"><span data-stu-id="0584a-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="0584a-122">指定该类型为一个类。</span><span class="sxs-lookup"><span data-stu-id="0584a-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="0584a-123">指定该类型为一个接口。</span><span class="sxs-lookup"><span data-stu-id="0584a-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="0584a-124">指定该类型为抽象类型。</span><span class="sxs-lookup"><span data-stu-id="0584a-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="0584a-125">指定类型不能进行扩展。</span><span class="sxs-lookup"><span data-stu-id="0584a-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="0584a-126">指定的类名称是特殊。</span><span class="sxs-lookup"><span data-stu-id="0584a-126">Specifies that the class name is special.</span></span> <span data-ttu-id="0584a-127">其名称描述的方式。</span><span class="sxs-lookup"><span data-stu-id="0584a-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="0584a-128">指定的类型导入。</span><span class="sxs-lookup"><span data-stu-id="0584a-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="0584a-129">指定的类型是可序列化。</span><span class="sxs-lookup"><span data-stu-id="0584a-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="0584a-130">指定此类型是[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型。</span><span class="sxs-lookup"><span data-stu-id="0584a-130">Specifies that this type is a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="0584a-131">获取有关字符串编码和格式化的方式的信息。</span><span class="sxs-lookup"><span data-stu-id="0584a-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="0584a-132">指定此类型解释为 ANSI LPTSTR。</span><span class="sxs-lookup"><span data-stu-id="0584a-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="0584a-133">指定此类型解释为 Unicode LPTSTR。</span><span class="sxs-lookup"><span data-stu-id="0584a-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="0584a-134">指定此类型会 LPTSTR 自动解释。</span><span class="sxs-lookup"><span data-stu-id="0584a-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="0584a-135">指定的类型具有非标准编码，所指定的`CustomFormatMask`。</span><span class="sxs-lookup"><span data-stu-id="0584a-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="0584a-136">使用此掩码获取本机互操作的非标准编码信息。</span><span class="sxs-lookup"><span data-stu-id="0584a-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="0584a-137">未指定这两个位的值的含义。</span><span class="sxs-lookup"><span data-stu-id="0584a-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="0584a-138">指定必须在第一次尝试访问的静态字段之前初始化的类型。</span><span class="sxs-lookup"><span data-stu-id="0584a-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="0584a-139">指定导出类型和类型转发器。</span><span class="sxs-lookup"><span data-stu-id="0584a-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="0584a-140">此标志及其以下标志由公共语言运行库内部使用。</span><span class="sxs-lookup"><span data-stu-id="0584a-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="0584a-141">指定公共语言运行时，应检查名称编码。</span><span class="sxs-lookup"><span data-stu-id="0584a-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="0584a-142">指定该类型具有与之关联的安全。</span><span class="sxs-lookup"><span data-stu-id="0584a-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0584a-143">要求</span><span class="sxs-lookup"><span data-stu-id="0584a-143">Requirements</span></span>  
 <span data-ttu-id="0584a-144">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0584a-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0584a-145">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="0584a-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0584a-146">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0584a-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0584a-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="0584a-147">See Also</span></span>  
 [<span data-ttu-id="0584a-148">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="0584a-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
