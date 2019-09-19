---
title: x:Members 指令
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: ca42079c1c40a8fb3b1ddfc8f4a6f742768fa9e1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053770"
---
# <a name="xmembers-directive"></a><span data-ttu-id="2ad10-102">x:Members 指令</span><span class="sxs-lookup"><span data-stu-id="2ad10-102">x:Members Directive</span></span>
<span data-ttu-id="2ad10-103">保存一组在标记中定义的成员，这些成员应用于父元素的 X：Class。</span><span class="sxs-lookup"><span data-stu-id="2ad10-103">Holds a set of members that are defined in markup, which apply to the x:Class of the parent element.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2ad10-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="2ad10-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2ad10-105">XAML 值</span><span class="sxs-lookup"><span data-stu-id="2ad10-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="2ad10-106">XAML 生产的备用类或分部类的名称。</span><span class="sxs-lookup"><span data-stu-id="2ad10-106">Name of the backing class or partial class for the XAML production.</span></span> <span data-ttu-id="2ad10-107">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="2ad10-107">See Remarks.</span></span>|  
|`oneOrMoreMembers`|<span data-ttu-id="2ad10-108">一个或多个表示成员定义的对象元素。</span><span class="sxs-lookup"><span data-stu-id="2ad10-108">One or more object elements that represent member definitions.</span></span> <span data-ttu-id="2ad10-109">通常，这些是`x:Property`对象元素。</span><span class="sxs-lookup"><span data-stu-id="2ad10-109">Typically, these are `x:Property` object elements.</span></span> <span data-ttu-id="2ad10-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="2ad10-110">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ad10-111">备注</span><span class="sxs-lookup"><span data-stu-id="2ad10-111">Remarks</span></span>  
 <span data-ttu-id="2ad10-112">在 .NET Framework XAML 服务实现中，没有适用于的`x:Members`支持类或基础成员实现。</span><span class="sxs-lookup"><span data-stu-id="2ad10-112">In the .NET Framework XAML Services implementation, there is no backing class or underlying member implementation for `x:Members`.</span></span> <span data-ttu-id="2ad10-113">`x:Members`是一个特殊的 XAML 成员，可作为任何类型的成员存在。</span><span class="sxs-lookup"><span data-stu-id="2ad10-113">`x:Members` is a special XAML member that can exist as a member on any type.</span></span> <span data-ttu-id="2ad10-114">在 xaml 节点流中， `x:Members`表示为来自 XAML 语言 xaml `Members`命名空间的名为的成员。</span><span class="sxs-lookup"><span data-stu-id="2ad10-114">In a XAML node stream, `x:Members` is represented as a member named `Members`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="2ad10-115">成员`Members`包含`Member`对象的只读泛型列表。</span><span class="sxs-lookup"><span data-stu-id="2ad10-115">The member `Members` contains a read-only generic list of `Member` objects.</span></span> <span data-ttu-id="2ad10-116">在典型标记中，将各个成员指定`x:Property`为属性元素。</span><span class="sxs-lookup"><span data-stu-id="2ad10-116">In typical markup the individual members are specified as `x:Property` property elements.</span></span> <span data-ttu-id="2ad10-117">`x:Property`是特定于类型的属性的更精确的类型，可分配`x:Member`给。</span><span class="sxs-lookup"><span data-stu-id="2ad10-117">`x:Property` is a more precise type specifically for properties of types and is assignable to `x:Member`.</span></span> <span data-ttu-id="2ad10-118">有关详细信息，请参阅[X:Property 指令](x-property-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="2ad10-118">For more information, see [x:Property Directive](x-property-directive.md).</span></span>  
  
 <span data-ttu-id="2ad10-119">若要支持将 `x:Members` 实际用作一种在标记中指定成员定义的方法，成员必须与可修改的类相关联。</span><span class="sxs-lookup"><span data-stu-id="2ad10-119">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="2ad10-120">预期模型是 `x:Members` 作为指定 `x:Class` 的类型的成员存在。</span><span class="sxs-lookup"><span data-stu-id="2ad10-120">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="2ad10-121">但是，.NET Framework XAML 服务级别不支持用于关联类型和成员或用于生成动态成员定义的机制。</span><span class="sxs-lookup"><span data-stu-id="2ad10-121">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="2ad10-122">此功能由具有支持 XAML 的成员定义的应用程序模型的单个框架实现。</span><span class="sxs-lookup"><span data-stu-id="2ad10-122">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="2ad10-123">通常，需要 MSBUILD 生成操来支持此功能，这些操作以标记编译 XAML 并将其与隐藏代码相集成或者从 XMAL 生成纯程序集。</span><span class="sxs-lookup"><span data-stu-id="2ad10-123">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xmembers-for-windows-workflow-foundation"></a><span data-ttu-id="2ad10-124">用于 Windows Workflow Foundation 的 x:Members</span><span class="sxs-lookup"><span data-stu-id="2ad10-124">x:Members for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="2ad10-125">对于 "Windows Workflow Foundation `x:Members` "，包含完全在 xaml 中组成的自定义活动的成员，或包含代码隐藏的活动设计器的 XAML 定义的动态成员。</span><span class="sxs-lookup"><span data-stu-id="2ad10-125">For Windows Workflow Foundation, `x:Members` contains the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="2ad10-126">此外，必须在 XAML 生产的根元素上指定 `x:Class`。</span><span class="sxs-lookup"><span data-stu-id="2ad10-126">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="2ad10-127">这不是 .NET Framework XAML 服务级别上的要求，但在一般情况下当支持自定义活动和 Windows Workflow Foundation XAML 的 MSBUILD 生成操作加载 XAML 生产时将成为一项要求。</span><span class="sxs-lookup"><span data-stu-id="2ad10-127">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="2ad10-128">`x:Members`必须是声明`x:Class`的对象元素的标记中的第一个子元素。</span><span class="sxs-lookup"><span data-stu-id="2ad10-128">`x:Members` must be the first child element in markup of the object element that declares the `x:Class`.</span></span>
