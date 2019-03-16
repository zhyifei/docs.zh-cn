---
title: x:Members 指令
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: d23e6b459af932e0a6f69309f26a1cce70a9d256
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58034504"
---
# <a name="xmembers-directive"></a><span data-ttu-id="67c8c-102">x:Members 指令</span><span class="sxs-lookup"><span data-stu-id="67c8c-102">x:Members Directive</span></span>
<span data-ttu-id="67c8c-103">包含一组在标记中，定义可应用于父元素的 x： 类的成员。</span><span class="sxs-lookup"><span data-stu-id="67c8c-103">Holds a set of members that are defined in markup, which apply to the x:Class of the parent element.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="67c8c-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="67c8c-104">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="67c8c-105">XAML 值</span><span class="sxs-lookup"><span data-stu-id="67c8c-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="67c8c-106">XAML 生产的备用类或分部类的名称。</span><span class="sxs-lookup"><span data-stu-id="67c8c-106">Name of the backing class or partial class for the XAML production.</span></span> <span data-ttu-id="67c8c-107">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="67c8c-107">See Remarks.</span></span>|  
|`oneOrMoreMembers`|<span data-ttu-id="67c8c-108">表示成员定义的一个或多个对象元素。</span><span class="sxs-lookup"><span data-stu-id="67c8c-108">One or more object elements that represent member definitions.</span></span> <span data-ttu-id="67c8c-109">通常情况下，这些是`x:Property`对象元素。</span><span class="sxs-lookup"><span data-stu-id="67c8c-109">Typically, these are `x:Property` object elements.</span></span> <span data-ttu-id="67c8c-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="67c8c-110">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67c8c-111">备注</span><span class="sxs-lookup"><span data-stu-id="67c8c-111">Remarks</span></span>  
 <span data-ttu-id="67c8c-112">在.NET Framework XAML 服务实现中，没有后备类或基础成员实现`x:Members`。</span><span class="sxs-lookup"><span data-stu-id="67c8c-112">In the .NET Framework XAML Services implementation, there is no backing class or underlying member implementation for `x:Members`.</span></span> <span data-ttu-id="67c8c-113">`x:Members` 是特殊的 XAML 成员可以为任何类型的成员存在。</span><span class="sxs-lookup"><span data-stu-id="67c8c-113">`x:Members` is a special XAML member that can exist as a member on any type.</span></span> <span data-ttu-id="67c8c-114">在 XAML 节点流中，`x:Members`表示为一个名为成员`Members`，从 XAML 语言 XAML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="67c8c-114">In a XAML node stream, `x:Members` is represented as a member named `Members`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="67c8c-115">该成员`Members`包含一个只读的泛型列表`Member`对象。</span><span class="sxs-lookup"><span data-stu-id="67c8c-115">The member `Members` contains a read-only generic list of `Member` objects.</span></span> <span data-ttu-id="67c8c-116">在典型的标记中的单个成员指定为`x:Property`属性元素。</span><span class="sxs-lookup"><span data-stu-id="67c8c-116">In typical markup the individual members are specified as `x:Property` property elements.</span></span> <span data-ttu-id="67c8c-117">`x:Property` 是专门为类型的属性的更精确的类型和可分配给`x:Member`。</span><span class="sxs-lookup"><span data-stu-id="67c8c-117">`x:Property` is a more precise type specifically for properties of types and is assignable to `x:Member`.</span></span> <span data-ttu-id="67c8c-118">有关详细信息，请参阅[X:property 指令](x-property-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="67c8c-118">For more information, see [x:Property Directive](x-property-directive.md).</span></span>  
  
 <span data-ttu-id="67c8c-119">若要支持将 `x:Members` 实际用作一种在标记中指定成员定义的方法，成员必须与可修改的类相关联。</span><span class="sxs-lookup"><span data-stu-id="67c8c-119">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="67c8c-120">预期模型是 `x:Members` 作为指定 `x:Class` 的类型的成员存在。</span><span class="sxs-lookup"><span data-stu-id="67c8c-120">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="67c8c-121">但是，.NET Framework XAML 服务级别不支持用于关联类型和成员或用于生成动态成员定义的机制。</span><span class="sxs-lookup"><span data-stu-id="67c8c-121">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="67c8c-122">此功能由具有支持 XAML 的成员定义的应用程序模型的单个框架实现。</span><span class="sxs-lookup"><span data-stu-id="67c8c-122">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="67c8c-123">通常，需要 MSBUILD 生成操来支持此功能，这些操作以标记编译 XAML 并将其与隐藏代码相集成或者从 XMAL 生成纯程序集。</span><span class="sxs-lookup"><span data-stu-id="67c8c-123">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xmembers-for-windows-workflow-foundation"></a><span data-ttu-id="67c8c-124">x： 用于 Windows Workflow Foundation 成员</span><span class="sxs-lookup"><span data-stu-id="67c8c-124">x:Members for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="67c8c-125">对于 Windows Workflow Foundation，`x:Members`包含组成完全在 XAML 或 XAML 中的自定义活动的成员 – 定义包含代码隐藏源文件的活动设计器的动态成员。</span><span class="sxs-lookup"><span data-stu-id="67c8c-125">For Windows Workflow Foundation, `x:Members` contains the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="67c8c-126">此外，必须在 XAML 生产的根元素上指定 `x:Class`。</span><span class="sxs-lookup"><span data-stu-id="67c8c-126">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="67c8c-127">这不是 .NET Framework XAML 服务级别上的要求，但在一般情况下当支持自定义活动和 Windows Workflow Foundation XAML 的 MSBUILD 生成操作加载 XAML 生产时将成为一项要求。</span><span class="sxs-lookup"><span data-stu-id="67c8c-127">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="67c8c-128">`x:Members` 必须在标记中声明的对象元素的第一个子元素`x:Class`。</span><span class="sxs-lookup"><span data-stu-id="67c8c-128">`x:Members` must be the first child element in markup of the object element that declares the `x:Class`.</span></span>
