---
title: 运行时指令 (rd.xml) 配置文件引用
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fed8097c472be487256840f289c1d8252d978a93
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637096"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="c44c5-102">运行时指令 (rd.xml) 配置文件引用</span><span class="sxs-lookup"><span data-stu-id="c44c5-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>
<span data-ttu-id="c44c5-103">运行时指令 (.rd.xml) 文件是一个 XML 配置文件，它指定了指定程序元素是否适用于反射。</span><span class="sxs-lookup"><span data-stu-id="c44c5-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="c44c5-104">运行时指令文件的示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="c44c5-104">Here’s an example of a runtime directives file:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
<Application>  
  <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />  
  <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />  
  <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />  
  <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />  
  
  <Namespace Name="System.Collections.ObjectModel" >  
    <TypeInstantiation Name="ObservableCollection"   
          Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />  
    <TypeInstantiation Name="ReadOnlyObservableCollection"   
          Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />  
  </Namespace>  
</Application>  
</Directives>  
```  
  
## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="c44c5-105">运行时指令文件的结构</span><span class="sxs-lookup"><span data-stu-id="c44c5-105">The structure of a runtime directives file</span></span>  
 <span data-ttu-id="c44c5-106">运行时指令文件使用 `http://schemas.microsoft.com/netfx/2013/01/metadata` 命名空间。</span><span class="sxs-lookup"><span data-stu-id="c44c5-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>  
  
 <span data-ttu-id="c44c5-107">根元素为 [Directives](../../../docs/framework/net-native/directives-element-net-native.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="c44c5-107">The root element is the [Directives](../../../docs/framework/net-native/directives-element-net-native.md) element.</span></span> <span data-ttu-id="c44c5-108">它可以包含零个或更多个 [Library](../../../docs/framework/net-native/library-element-net-native.md) 元素，以及零个或一个 [Application](../../../docs/framework/net-native/application-element-net-native.md) 元素，如以下结构中所示。</span><span class="sxs-lookup"><span data-stu-id="c44c5-108">It can contain zero or more [Library](../../../docs/framework/net-native/library-element-net-native.md) elements, and zero or one [Application](../../../docs/framework/net-native/application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="c44c5-109">[Application](../../../docs/framework/net-native/application-element-net-native.md) 元素的特性可定义应用程序范围的运行时反射策略，或可充当子元素的容器。</span><span class="sxs-lookup"><span data-stu-id="c44c5-109">The attributes of the [Application](../../../docs/framework/net-native/application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="c44c5-110">而 [Library](../../../docs/framework/net-native/library-element-net-native.md) 元素则仅仅是一个容器。</span><span class="sxs-lookup"><span data-stu-id="c44c5-110">The [Library](../../../docs/framework/net-native/library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="c44c5-111">[Application](../../../docs/framework/net-native/application-element-net-native.md) 和 [Library](../../../docs/framework/net-native/library-element-net-native.md) 元素的子级定义了适用于反射的类型、方法、字段、属性和事件。</span><span class="sxs-lookup"><span data-stu-id="c44c5-111">The children of the [Application](../../../docs/framework/net-native/application-element-net-native.md) and [Library](../../../docs/framework/net-native/library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>  
  
 <span data-ttu-id="c44c5-112">有关引用信息，请从以下结构中选择元素或参阅[运行时指令元素](../../../docs/framework/net-native/runtime-directive-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="c44c5-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](../../../docs/framework/net-native/runtime-directive-elements.md).</span></span> <span data-ttu-id="c44c5-113">在以下层次结构中，省略号表示递归结构。</span><span class="sxs-lookup"><span data-stu-id="c44c5-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="c44c5-114">括号中的信息表明元素是可选项还是必需项，以及如果使用该元素，将允许多少个实例（一个或多个）。</span><span class="sxs-lookup"><span data-stu-id="c44c5-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>  
  
 <span data-ttu-id="c44c5-115">[Directives](../../../docs/framework/net-native/directives-element-net-native.md) [1:1]</span><span class="sxs-lookup"><span data-stu-id="c44c5-115">[Directives](../../../docs/framework/net-native/directives-element-net-native.md) [1:1]</span></span>  
 <span data-ttu-id="c44c5-116">[Application](../../../docs/framework/net-native/application-element-net-native.md) [0:1]</span><span class="sxs-lookup"><span data-stu-id="c44c5-116">[Application](../../../docs/framework/net-native/application-element-net-native.md) [0:1]</span></span>  
 <span data-ttu-id="c44c5-117">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-117">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-118">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-118">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-119">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-119">.</span></span> <span data-ttu-id="c44c5-120">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-120">.</span></span> <span data-ttu-id="c44c5-121">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-121">.</span></span>  
 <span data-ttu-id="c44c5-122">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-122">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-123">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-123">.</span></span> <span data-ttu-id="c44c5-124">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-124">.</span></span> <span data-ttu-id="c44c5-125">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-125">.</span></span>  
 <span data-ttu-id="c44c5-126">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)（构造泛型类型）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-126">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="c44c5-127">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-127">.</span></span> <span data-ttu-id="c44c5-128">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-128">.</span></span> <span data-ttu-id="c44c5-129">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-129">.</span></span>  
 <span data-ttu-id="c44c5-130">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-130">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-131">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-131">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-132">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-132">.</span></span> <span data-ttu-id="c44c5-133">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-133">.</span></span> <span data-ttu-id="c44c5-134">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-134">.</span></span>  
 <span data-ttu-id="c44c5-135">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-135">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-136">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-136">.</span></span> <span data-ttu-id="c44c5-137">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-137">.</span></span> <span data-ttu-id="c44c5-138">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-138">.</span></span>  
 <span data-ttu-id="c44c5-139">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)（构造泛型类型）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-139">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="c44c5-140">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-140">.</span></span> <span data-ttu-id="c44c5-141">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-141">.</span></span> <span data-ttu-id="c44c5-142">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-142">.</span></span>  
 <span data-ttu-id="c44c5-143">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-143">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-144">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md)（包含类型的子类）[O:1]</span><span class="sxs-lookup"><span data-stu-id="c44c5-144">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>  
 <span data-ttu-id="c44c5-145">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-145">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-146">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-146">.</span></span> <span data-ttu-id="c44c5-147">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-147">.</span></span> <span data-ttu-id="c44c5-148">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-148">.</span></span>  
 <span data-ttu-id="c44c5-149">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)（构造泛型类型）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-149">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="c44c5-150">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-150">.</span></span> <span data-ttu-id="c44c5-151">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-151">.</span></span> <span data-ttu-id="c44c5-152">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-152">.</span></span>  
 <span data-ttu-id="c44c5-153">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md)（包含类型是一种特性）[O:1]</span><span class="sxs-lookup"><span data-stu-id="c44c5-153">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>  
 <span data-ttu-id="c44c5-154">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-154">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-155">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-155">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-156">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-156">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-157">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-157">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-158">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-158">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-159">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)（构造泛型方法）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-159">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="c44c5-160">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-160">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-161">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-161">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-162">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-162">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-163">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)（构造泛型类型）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-163">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="c44c5-164">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-164">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-165">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-165">.</span></span> <span data-ttu-id="c44c5-166">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-166">.</span></span> <span data-ttu-id="c44c5-167">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-167">.</span></span>  
 <span data-ttu-id="c44c5-168">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)（构造泛型类型）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-168">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="c44c5-169">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-169">.</span></span> <span data-ttu-id="c44c5-170">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-170">.</span></span> <span data-ttu-id="c44c5-171">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-171">.</span></span>  
 <span data-ttu-id="c44c5-172">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-172">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-173">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-173">[Parameter](../../../docs/framework/net-native/parameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-174">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-174">[TypeParameter](../../../docs/framework/net-native/typeparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-175">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-175">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-176">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)（构造泛型方法）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-176">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="c44c5-177">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-177">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-178">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-178">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-179">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-179">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-180">[Library](../../../docs/framework/net-native/library-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-180">[Library](../../../docs/framework/net-native/library-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-181">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-181">[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-182">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-182">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-183">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-183">.</span></span> <span data-ttu-id="c44c5-184">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-184">.</span></span> <span data-ttu-id="c44c5-185">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-185">.</span></span>  
 <span data-ttu-id="c44c5-186">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-186">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-187">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-187">.</span></span> <span data-ttu-id="c44c5-188">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-188">.</span></span> <span data-ttu-id="c44c5-189">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-189">.</span></span>  
 <span data-ttu-id="c44c5-190">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)（构造泛型类型）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-190">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="c44c5-191">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-191">.</span></span> <span data-ttu-id="c44c5-192">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-192">.</span></span> <span data-ttu-id="c44c5-193">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-193">.</span></span>  
 <span data-ttu-id="c44c5-194">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-194">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-195">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-195">[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-196">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-196">.</span></span> <span data-ttu-id="c44c5-197">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-197">.</span></span> <span data-ttu-id="c44c5-198">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-198">.</span></span>  
 <span data-ttu-id="c44c5-199">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-199">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-200">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-200">.</span></span> <span data-ttu-id="c44c5-201">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-201">.</span></span> <span data-ttu-id="c44c5-202">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-202">.</span></span>  
 <span data-ttu-id="c44c5-203">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)（构造泛型类型）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-203">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="c44c5-204">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-204">.</span></span> <span data-ttu-id="c44c5-205">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-205">.</span></span> <span data-ttu-id="c44c5-206">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-206">.</span></span>  
 <span data-ttu-id="c44c5-207">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-207">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-208">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md)（包含类型的子类）[O:1]</span><span class="sxs-lookup"><span data-stu-id="c44c5-208">[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>  
 <span data-ttu-id="c44c5-209">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-209">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-210">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-210">.</span></span> <span data-ttu-id="c44c5-211">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-211">.</span></span> <span data-ttu-id="c44c5-212">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-212">.</span></span>  
 <span data-ttu-id="c44c5-213">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)（构造泛型类型）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-213">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="c44c5-214">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-214">.</span></span> <span data-ttu-id="c44c5-215">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-215">.</span></span> <span data-ttu-id="c44c5-216">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-216">.</span></span>  
 <span data-ttu-id="c44c5-217">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md)（包含类型是一种特性）[O:1]</span><span class="sxs-lookup"><span data-stu-id="c44c5-217">[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>  
 <span data-ttu-id="c44c5-218">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-218">[GenericParameter](../../../docs/framework/net-native/genericparameter-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-219">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-219">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-220">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)（构造泛型方法）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-220">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="c44c5-221">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-221">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-222">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-222">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-223">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-223">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-224">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)（构造泛型类型）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-224">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="c44c5-225">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-225">[Type](../../../docs/framework/net-native/type-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-226">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-226">.</span></span> <span data-ttu-id="c44c5-227">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-227">.</span></span> <span data-ttu-id="c44c5-228">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-228">.</span></span>  
 <span data-ttu-id="c44c5-229">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)（构造泛型类型）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-229">[TypeInstantiation](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>  
 <span data-ttu-id="c44c5-230">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-230">.</span></span> <span data-ttu-id="c44c5-231">。</span><span class="sxs-lookup"><span data-stu-id="c44c5-231">.</span></span> <span data-ttu-id="c44c5-232">.</span><span class="sxs-lookup"><span data-stu-id="c44c5-232">.</span></span>  
 <span data-ttu-id="c44c5-233">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-233">[Method](../../../docs/framework/net-native/method-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-234">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)（构造泛型方法）[0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-234">[MethodInstantiation](../../../docs/framework/net-native/methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>  
 <span data-ttu-id="c44c5-235">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-235">[Property](../../../docs/framework/net-native/property-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-236">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-236">[Field](../../../docs/framework/net-native/field-element-net-native.md) [0:M]</span></span>  
 <span data-ttu-id="c44c5-237">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="c44c5-237">[Event](../../../docs/framework/net-native/event-element-net-native.md) [0:M]</span></span>  
  
 <span data-ttu-id="c44c5-238">[Application](../../../docs/framework/net-native/application-element-net-native.md) 元素可以不具任何属性，也可以具备在[“运行时指令和策略”部分](#Directives)中所讨论的策略属性。</span><span class="sxs-lookup"><span data-stu-id="c44c5-238">The [Application](../../../docs/framework/net-native/application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>  
  
 <span data-ttu-id="c44c5-239">[Library`Name` 元素具有单个属性 ](../../../docs/framework/net-native/library-element-net-native.md)，该属性指定了库名或程序集名（不带文件扩展名）。</span><span class="sxs-lookup"><span data-stu-id="c44c5-239">A [Library](../../../docs/framework/net-native/library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="c44c5-240">例如，以下 [Library](../../../docs/framework/net-native/library-element-net-native.md) 元素适用于名为 Extensions.dll 的程序集。</span><span class="sxs-lookup"><span data-stu-id="c44c5-240">For example, the following [Library](../../../docs/framework/net-native/library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <!-- Child elements go here -->    
  </Application>  
  <Library Name="Extensions">  
     <!-- Child elements go here -->    
  </Library>  
</Directives>  
```  
  
<a name="Directives"></a>   
## <a name="runtime-directives-and-policy"></a><span data-ttu-id="c44c5-241">运行时指令和策略</span><span class="sxs-lookup"><span data-stu-id="c44c5-241">Runtime directives and policy</span></span>  
 <span data-ttu-id="c44c5-242">[Application](../../../docs/framework/net-native/application-element-net-native.md) 元素本身以及 [Library](../../../docs/framework/net-native/library-element-net-native.md) 和 [Application](../../../docs/framework/net-native/application-element-net-native.md) 元素的子元素表示策略，也就是说，它们定义了应用可将反射应用于程序元素的方式。</span><span class="sxs-lookup"><span data-stu-id="c44c5-242">The [Application](../../../docs/framework/net-native/application-element-net-native.md) element itself and the child elements of the [Library](../../../docs/framework/net-native/library-element-net-native.md) and [Application](../../../docs/framework/net-native/application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="c44c5-243">策略类型由元素属性定义（例如，`Serialize`）。</span><span class="sxs-lookup"><span data-stu-id="c44c5-243">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="c44c5-244">策略值由属性值定义（例如，`Serialize="Required"`）。</span><span class="sxs-lookup"><span data-stu-id="c44c5-244">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>  
  
 <span data-ttu-id="c44c5-245">任何由元素属性指定的策略均适用于未对该策略指定值的子元素。</span><span class="sxs-lookup"><span data-stu-id="c44c5-245">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="c44c5-246">例如，如果策略由 [Type](../../../docs/framework/net-native/type-element-net-native.md) 元素指定，则该策略适用于包含的所有尚未显式指定策略的类型和成员。</span><span class="sxs-lookup"><span data-stu-id="c44c5-246">For example, if a policy is specified by a [Type](../../../docs/framework/net-native/type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>  
  
 <span data-ttu-id="c44c5-247">可通过 [Application](../../../docs/framework/net-native/application-element-net-native.md)、[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md)、[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md)、[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md)、[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) 和 [Type](../../../docs/framework/net-native/type-element-net-native.md) 元素表示的策略有别于可针对每个成员表示的策略（通过 [Method](../../../docs/framework/net-native/method-element-net-native.md)、[Property](../../../docs/framework/net-native/property-element-net-native.md)、[Field](../../../docs/framework/net-native/field-element-net-native.md) 和 [Event](../../../docs/framework/net-native/event-element-net-native.md) 元素来表示）。</span><span class="sxs-lookup"><span data-stu-id="c44c5-247">The policy that can be expressed by the [Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md), and [Type](../../../docs/framework/net-native/type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](../../../docs/framework/net-native/method-element-net-native.md), [Property](../../../docs/framework/net-native/property-element-net-native.md), [Field](../../../docs/framework/net-native/field-element-net-native.md), and [Event](../../../docs/framework/net-native/event-element-net-native.md) elements).</span></span>  
  
### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="c44c5-248">为程序集、命名空间和类型指定策略</span><span class="sxs-lookup"><span data-stu-id="c44c5-248">Specifying policy for assemblies, namespaces, and types</span></span>  
 <span data-ttu-id="c44c5-249">[Application](../../../docs/framework/net-native/application-element-net-native.md)、[Assembly](../../../docs/framework/net-native/assembly-element-net-native.md)、[AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md)、[Namespace](../../../docs/framework/net-native/namespace-element-net-native.md)、[Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md) 和 [Type](../../../docs/framework/net-native/type-element-net-native.md) 元素支持下列策略类型：</span><span class="sxs-lookup"><span data-stu-id="c44c5-249">The [Application](../../../docs/framework/net-native/application-element-net-native.md), [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md), [AttributeImplies](../../../docs/framework/net-native/attributeimplies-element-net-native.md), [Namespace](../../../docs/framework/net-native/namespace-element-net-native.md), [Subtypes](../../../docs/framework/net-native/subtypes-element-net-native.md), and [Type](../../../docs/framework/net-native/type-element-net-native.md) elements support the following policy types:</span></span>  
  
-   <span data-ttu-id="c44c5-250">`Activate`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-250">`Activate`.</span></span> <span data-ttu-id="c44c5-251">控制运行时对构造函数的访问，以启用实例激活。</span><span class="sxs-lookup"><span data-stu-id="c44c5-251">Controls runtime access to constructors, to enable activation of instances.</span></span>  
  
-   <span data-ttu-id="c44c5-252">`Browse`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-252">`Browse`.</span></span> <span data-ttu-id="c44c5-253">控制对有关程序元素信息的查询，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="c44c5-253">Controls querying for information about program elements but does not enable any runtime access.</span></span>  
  
-   <span data-ttu-id="c44c5-254">`Dynamic`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-254">`Dynamic`.</span></span> <span data-ttu-id="c44c5-255">控制运行时对所有类型成员的访问，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="c44c5-255">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>  
  
-   <span data-ttu-id="c44c5-256">`Serialize`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-256">`Serialize`.</span></span> <span data-ttu-id="c44c5-257">控制运行时对构造函数、字段和属性的访问，以便通过 Newtonsoft JSON 序列化程序等第三方库实现类型实例的序列化。</span><span class="sxs-lookup"><span data-stu-id="c44c5-257">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>  
  
-   <span data-ttu-id="c44c5-258">`DataContractSerializer`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-258">`DataContractSerializer`.</span></span> <span data-ttu-id="c44c5-259">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的序列化策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-259">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>  
  
-   <span data-ttu-id="c44c5-260">`DataContractJsonSerializer`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-260">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="c44c5-261">控制使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> 类的 JSON 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-261">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>  
  
-   <span data-ttu-id="c44c5-262">`XmlSerializer`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-262">`XmlSerializer`.</span></span> <span data-ttu-id="c44c5-263">控制使用 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> 类的 XML 序列化策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-263">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>  
  
-   <span data-ttu-id="c44c5-264">`MarshalObject`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-264">`MarshalObject`.</span></span> <span data-ttu-id="c44c5-265">控制将引用类型封送到 WinRT 和 COM 的策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-265">Controls policy for marshaling reference types to WinRT and COM.</span></span>  
  
-   <span data-ttu-id="c44c5-266">`MarshalDelegate`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-266">`MarshalDelegate`.</span></span> <span data-ttu-id="c44c5-267">控制将委托类型作为函数指针封送到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-267">Controls policy for marshaling delegate types as function pointers to native code.</span></span>  
  
-   <span data-ttu-id="c44c5-268">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="c44c5-268">`MarshalStructure` .</span></span> <span data-ttu-id="c44c5-269">控制封送结构到本机代码的策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-269">Controls policy for marshaling structures to native code.</span></span>  
  
 <span data-ttu-id="c44c5-270">与这些策略类型有关的设置如下：</span><span class="sxs-lookup"><span data-stu-id="c44c5-270">The settings associated with these policy types are:</span></span>  
  
-   <span data-ttu-id="c44c5-271">`All`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-271">`All`.</span></span> <span data-ttu-id="c44c5-272">为工具链未删除的所有类型和成员启用策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-272">Enable the policy for all types and members that the tool chain does not remove.</span></span>  
  
-   <span data-ttu-id="c44c5-273">`Auto`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-273">`Auto`.</span></span> <span data-ttu-id="c44c5-274">使用默认行为。</span><span class="sxs-lookup"><span data-stu-id="c44c5-274">Use the default behavior.</span></span> <span data-ttu-id="c44c5-275">（未指定策略等同于将该策略设置为 `Auto`，除非该策略被替代，例如被父元素替代。）</span><span class="sxs-lookup"><span data-stu-id="c44c5-275">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>  
  
-   <span data-ttu-id="c44c5-276">`Excluded`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-276">`Excluded`.</span></span> <span data-ttu-id="c44c5-277">禁用程序元素策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-277">Disable the policy for the program element.</span></span>  
  
-   <span data-ttu-id="c44c5-278">`Public`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-278">`Public`.</span></span> <span data-ttu-id="c44c5-279">启用公共类型或成员策略，除非工具链确定该成员为多余并因此将其删除。</span><span class="sxs-lookup"><span data-stu-id="c44c5-279">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="c44c5-280">（在后一种情况下，你必须使用 `Required Public`，以确保该成员已被保留并且具有反射功能。）</span><span class="sxs-lookup"><span data-stu-id="c44c5-280">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>  
  
-   <span data-ttu-id="c44c5-281">`PublicAndInternal`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-281">`PublicAndInternal`.</span></span> <span data-ttu-id="c44c5-282">如果工具链未将公共和内部类型或成员删除，则为它们启用策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-282">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>  
  
-   <span data-ttu-id="c44c5-283">`Required Public`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-283">`Required Public`.</span></span> <span data-ttu-id="c44c5-284">不管公共类型和成员是否处于占用状态，工具链均须将它们保留下来，并为它们启用策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-284">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>  
  
-   <span data-ttu-id="c44c5-285">`Required PublicAndInternal`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-285">`Required PublicAndInternal`.</span></span> <span data-ttu-id="c44c5-286">不管公共和内部类型和成员是否处于占用状态，工具链均须将它们保留下来，并为它们启用策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-286">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>  
  
-   <span data-ttu-id="c44c5-287">`Required All`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-287">`Required All`.</span></span> <span data-ttu-id="c44c5-288">不管所有类型和成员是否处于占用状态，工具链均须将它们保留下来，并为它们启用策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-288">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>  
  
 <span data-ttu-id="c44c5-289">例如，以下运行时指令文件为程序集 DataClasses.dll 中的所有类型和成员定义了策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-289">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="c44c5-290">借此可以实现对所有公共属性的序列化反射；可实现对所有类型和类型成员进行浏览；可实现对所有类型的激活（由于具有 `Dynamic` 属性）；还可实现对所有公共类型和成员的反射。</span><span class="sxs-lookup"><span data-stu-id="c44c5-290">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public"   
                Browse="All" Activate="PublicAndInternal"   
                Dynamic="Public"  />  
   </Application>  
   <Library Name="UtilityLibrary">  
     <!-- Child elements go here -->    
   </Library>  
</Directives>  
```  
  
### <a name="specifying-policy-for-members"></a><span data-ttu-id="c44c5-291">为成员指定策略</span><span class="sxs-lookup"><span data-stu-id="c44c5-291">Specifying policy for members</span></span>  
 <span data-ttu-id="c44c5-292">[Property](../../../docs/framework/net-native/property-element-net-native.md) 和 [Field](../../../docs/framework/net-native/field-element-net-native.md) 元素支持下列策略类型：</span><span class="sxs-lookup"><span data-stu-id="c44c5-292">The [Property](../../../docs/framework/net-native/property-element-net-native.md) and [Field](../../../docs/framework/net-native/field-element-net-native.md) elements support the following policy types:</span></span>  
  
-   <span data-ttu-id="c44c5-293">`Browse` - 控制查询有关此成员的信息，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="c44c5-293">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>  
  
-   <span data-ttu-id="c44c5-294">`Dynamic` - 控制运行时访问所有类型的成员，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="c44c5-294">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="c44c5-295">还控制查询有关包含类型的信息。</span><span class="sxs-lookup"><span data-stu-id="c44c5-295">Also controls querying for information about the containing type.</span></span>  
  
-   <span data-ttu-id="c44c5-296">`Serialize` - 控制运行时访问成员，以便通过 Newtonsoft JSON 序列化程序等库实现类型实例的序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="c44c5-296">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="c44c5-297">此策略可应用于构造函数、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="c44c5-297">This policy can be applied to constructors, fields, and properties.</span></span>  
  
 <span data-ttu-id="c44c5-298">[Method](../../../docs/framework/net-native/method-element-net-native.md) 和 [Event](../../../docs/framework/net-native/event-element-net-native.md) 元素支持下列策略类型：</span><span class="sxs-lookup"><span data-stu-id="c44c5-298">The [Method](../../../docs/framework/net-native/method-element-net-native.md) and [Event](../../../docs/framework/net-native/event-element-net-native.md) elements support the following policy types:</span></span>  
  
-   <span data-ttu-id="c44c5-299">`Browse` - 控制查询有关此成员的信息，但并不启用任何运行时访问。</span><span class="sxs-lookup"><span data-stu-id="c44c5-299">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>  
  
-   <span data-ttu-id="c44c5-300">`Dynamic` - 控制运行时访问所有类型的成员，包括构造函数、方法、字段、属性和事件，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="c44c5-300">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="c44c5-301">还控制查询有关包含类型的信息。</span><span class="sxs-lookup"><span data-stu-id="c44c5-301">Also controls querying for information about the containing type.</span></span>  
  
 <span data-ttu-id="c44c5-302">与这些策略类型有关的设置如下：</span><span class="sxs-lookup"><span data-stu-id="c44c5-302">The settings associated with these policy types are:</span></span>  
  
-   <span data-ttu-id="c44c5-303">`Auto` - 使用默认行为。</span><span class="sxs-lookup"><span data-stu-id="c44c5-303">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="c44c5-304">（未指定策略等同于将该策略设置为 `Auto`，除非某些内容将该策略替代。）</span><span class="sxs-lookup"><span data-stu-id="c44c5-304">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>  
  
-   <span data-ttu-id="c44c5-305">`Excluded` - 始终不包括成员的元数据。</span><span class="sxs-lookup"><span data-stu-id="c44c5-305">`Excluded` - Never include metadata for the member.</span></span>  
  
-   <span data-ttu-id="c44c5-306">`Included` - 如果输出中存在父类型，则启用策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-306">`Included` - Enable the policy if the parent type is present in the output.</span></span>  
  
-   <span data-ttu-id="c44c5-307">`Required` - 即便该成员显示为未使用，工具链也必须将它保留下来，并为它启用策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-307">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>  
  
## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="c44c5-308">运行时指令文件语义</span><span class="sxs-lookup"><span data-stu-id="c44c5-308">Runtime directives file semantics</span></span>  
 <span data-ttu-id="c44c5-309">可同时为较高级别和较低级别元素定义策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-309">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="c44c5-310">例如，我们可为程序集以及其中包含的一些类型定义策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-310">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="c44c5-311">如果无法表示特定的较低级别元素，则说明该元素继承了其父级的策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-311">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="c44c5-312">例如，如果存在 `Assembly` 元素却不存在 `Type` 元素，则说明在 `Assembly` 中指定的策略适用于数据集中的每一个类型。</span><span class="sxs-lookup"><span data-stu-id="c44c5-312">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="c44c5-313">多个元素也可将策略应用到同一个程序元素。</span><span class="sxs-lookup"><span data-stu-id="c44c5-313">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="c44c5-314">例如，不同的 [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) 元素可能会以不同的方式为同一个数据集定义同一个策略元素。</span><span class="sxs-lookup"><span data-stu-id="c44c5-314">For example, separate [Assembly](../../../docs/framework/net-native/assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="c44c5-315">以下部分将分别说明在下列情况下应如何处理特定类型策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-315">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>  
  
 <span data-ttu-id="c44c5-316">泛型类型或方法的一个 [Type](../../../docs/framework/net-native/type-element-net-native.md) 或 [Method](../../../docs/framework/net-native/method-element-net-native.md) 元素将它的策略应用到所有不具备自身策略的实例化。</span><span class="sxs-lookup"><span data-stu-id="c44c5-316">A [Type](../../../docs/framework/net-native/type-element-net-native.md) or [Method](../../../docs/framework/net-native/method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="c44c5-317">例如，为 `Type` 指定了策略的 <xref:System.Collections.Generic.List%601> 元素适用于该泛型类型的所有构造实例，除非 `List<Int32>` 元素将其替代为特殊构造的泛型类型（例如 `TypeInstantiation`）。</span><span class="sxs-lookup"><span data-stu-id="c44c5-317">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="c44c5-318">否则，元素将为指定的程序元素定义策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-318">Otherwise, elements define policy for the program element named.</span></span>  
  
 <span data-ttu-id="c44c5-319">元素不明确时，引擎将查找匹配项，如果发现完全匹配就将使用该条匹配。</span><span class="sxs-lookup"><span data-stu-id="c44c5-319">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="c44c5-320">如果发现多条匹配，将出现警告或错误。</span><span class="sxs-lookup"><span data-stu-id="c44c5-320">If it finds multiple matches, there will be a warning or error.</span></span>  
  
### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="c44c5-321">如果两条指令将策略应用于同一个程序元素</span><span class="sxs-lookup"><span data-stu-id="c44c5-321">If two directives apply policy to the same program element</span></span>  
 <span data-ttu-id="c44c5-322">如果不同运行时指令文件中的两个元素尝试将同一程序元素（例如程序集或类型）的同一策略类型设置为不同的值，则解决冲突的方法如下：</span><span class="sxs-lookup"><span data-stu-id="c44c5-322">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>  
  
1.  <span data-ttu-id="c44c5-323">如果存在 `Excluded` 元素，则该元素优先。</span><span class="sxs-lookup"><span data-stu-id="c44c5-323">If the `Excluded` element is present, it has precedence.</span></span>  
  
2.  <span data-ttu-id="c44c5-324">`Required` 优先于非 `Required`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-324">`Required` has precedence over not `Required`.</span></span>  
  
3.  <span data-ttu-id="c44c5-325">`All` 优先于 `PublicAndInternal`，而后者又优先于 `Public`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-325">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>  
  
4.  <span data-ttu-id="c44c5-326">任何显式设置均优先于 `Auto`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-326">Any explicit setting has precedence over `Auto`.</span></span>  
  
 <span data-ttu-id="c44c5-327">例如，如果单个项目包含以下两种运行时指令文件，DataClasses.dll 的序列化策略将设置为 `Required Public` 和 `All`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-327">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="c44c5-328">在此情况下，序列化策略将被处理为 `Required All`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-328">In this case, the serialization policy would be resolved as `Required All`.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public"/>  
   </Application>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="All" />  
   </Application>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
 <span data-ttu-id="c44c5-329">但如果单个运行时指令文件中的两个指令尝试设置同一程序元素的同一策略类型，则 XML Scheme Definition 工具将显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="c44c5-329">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>  
  
### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="c44c5-330">如果子元素和父元素应用的是同一策略类型</span><span class="sxs-lookup"><span data-stu-id="c44c5-330">If child and parent elements apply the same policy type</span></span>  
 <span data-ttu-id="c44c5-331">子元素将替代其父元素，包括 `Excluded` 设置。</span><span class="sxs-lookup"><span data-stu-id="c44c5-331">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="c44c5-332">你想要指定 `Auto` 的主要原因就是要执行替代操作。</span><span class="sxs-lookup"><span data-stu-id="c44c5-332">Overriding is the main reason you would want to specify `Auto`.</span></span>  
  
 <span data-ttu-id="c44c5-333">在以下示例中，`DataClasses` 中所有内容（`DataClasses.ViewModels` 中不含这些内容）的序列化策略设置将为 `Required Public`，而 `DataClasses` 和 `DataClasses.ViewModels` 中所有内容的序列化策略设置将为 `All`。</span><span class="sxs-lookup"><span data-stu-id="c44c5-333">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public" >  
         <Namespace Name="DataClasses.ViewModels" Seralize="All" />  
      </Assembly>  
   </Appliction>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="c44c5-334">如果开放式泛型元素和已实例化的元素应用的是同一策略类型</span><span class="sxs-lookup"><span data-stu-id="c44c5-334">If open generics and instantiated elements apply the same policy type</span></span>  
 <span data-ttu-id="c44c5-335">在以下示例中，只有当引擎出于其他原因提供 `Dictionary<int,int>` 策略时（亦可为默认行为），才会为 `Browse` 分配 `Browse` 策略；<xref:System.Collections.Generic.Dictionary%602> 的所有其他实例化将具有所有可浏览的成员。</span><span class="sxs-lookup"><span data-stu-id="c44c5-335">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="DataClasses" Serialize="Required Public" >  
         <Namespace Name="DataClasses.ViewModels" Seralize="All" />  
      </Assembly>  
      <Namespace Name="DataClasses.Generics" />  
      <Type Name="Dictionary" Browse="All" />  
      <TypeInstantiation Name="Dictionary"   
                         Arguments="System.Int32,System.Int32" Browse="Auto" />  
   </Application>  
   <Library Name="DataClasses">  
      <!-- any other elements -->  
   </Library>  
</Directives>  
```  
  
### <a name="how-policy-is-inferred"></a><span data-ttu-id="c44c5-336">如何推断出策略</span><span class="sxs-lookup"><span data-stu-id="c44c5-336">How policy is inferred</span></span>  
 <span data-ttu-id="c44c5-337">每个策略类型均具有一组不同的规则，这些规则决定了该策略类型的存在如何对其他构造造成影响。</span><span class="sxs-lookup"><span data-stu-id="c44c5-337">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>  
  
#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="c44c5-338">“浏览”策略的效果</span><span class="sxs-lookup"><span data-stu-id="c44c5-338">The effect of Browse policy</span></span>  
 <span data-ttu-id="c44c5-339">将 `Browse` 策略应用于类型涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-339">Applying the `Browse` policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="c44c5-340">类型的基类型标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-340">The base type of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-341">如果类型为实例化泛型类型，则该类型的未实例化版本将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-341">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-342">如果类型为委托类型，则针对该类型的 `Invoke` 方法将标有 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-342">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-343">每个类型接口将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-343">Each interface of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-344">应用于类型的每个属性类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-344">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-345">如果类型为泛型，则每个约束类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-345">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-346">如果类型为泛型，则实例化该类型所采用的类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-346">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>  
  
 <span data-ttu-id="c44c5-347">将 `Browse` 策略应用于方法涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-347">Applying the `Browse` policy to a method involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="c44c5-348">方法的每个参数类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-348">Each parameter type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-349">方法的返回类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-349">The return type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-350">方法的包含类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-350">The containing type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-351">如果方法为实例化泛型方法，则未实例化泛型方法将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-351">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-352">应用于方法的每个属性类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-352">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-353">如果方法为泛型，则每个约束类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-353">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-354">如果方法为泛型，则实例化该方法所采用的类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-354">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>  
  
 <span data-ttu-id="c44c5-355">将 `Browse` 策略应用于字段涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-355">Applying the `Browse` policy to a field involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="c44c5-356">应用于字段的每个属性类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-356">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-357">字段类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-357">The type of the field is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-358">字段从属的类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-358">The type to which the field belongs is marked with the `Browse` policy.</span></span>  
  
#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="c44c5-359">“动态”策略的效果</span><span class="sxs-lookup"><span data-stu-id="c44c5-359">The effect of Dynamic policy</span></span>  
 <span data-ttu-id="c44c5-360">将 `Dynamic` 策略应用于类型涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-360">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="c44c5-361">类型的基类型标有 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-361">The base type of the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-362">如果类型为实例化泛型类型，则该类型的未实例化版本将标有 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-362">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-363">如果类型为委托类型，则针对该类型的 `Invoke` 方法将标有 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-363">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-364">每个类型接口将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-364">Each interface of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-365">应用于类型的每个属性类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-365">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-366">如果类型为泛型，则每个约束类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-366">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-367">如果类型为泛型，则实例化该类型所采用的类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-367">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>  
  
 <span data-ttu-id="c44c5-368">将 `Dynamic` 策略应用于方法涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-368">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="c44c5-369">方法的每个参数类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-369">Each parameter type of the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-370">方法的返回类型将标有 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-370">The return type of the method is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-371">方法的包含类型将标有 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-371">The containing type of the method is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-372">如果方法为实例化泛型方法，则未实例化泛型方法将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-372">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-373">应用于方法的每个属性类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-373">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-374">如果方法为泛型，则每个约束类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-374">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-375">如果方法为泛型，则实例化该方法所采用的类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-375">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-376">`MethodInfo.Invoke` 可调用方法，并且可通过 <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType> 进行委托创建。</span><span class="sxs-lookup"><span data-stu-id="c44c5-376">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="c44c5-377">将 `Dynamic` 策略应用于字段涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-377">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="c44c5-378">应用于字段的每个属性类型将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-378">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-379">字段类型将标有 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-379">The type of the field is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-380">字段从属的类型将标有 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-380">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>  
  
#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="c44c5-381">“激活”策略的效果</span><span class="sxs-lookup"><span data-stu-id="c44c5-381">The effect of Activation policy</span></span>  
 <span data-ttu-id="c44c5-382">将“激活”策略应用于类型涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-382">Applying the Activation policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="c44c5-383">如果类型为实例化泛型类型，则该类型的未实例化版本将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-383">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-384">如果类型为委托类型，则针对该类型的 `Invoke` 方法将标有 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-384">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-385">类型的构造函数标有 `Activation` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-385">Constructors of the type are marked with the `Activation` policy.</span></span>  
  
 <span data-ttu-id="c44c5-386">将 `Activation` 策略应用于方法涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-386">Applying the `Activation` policy to a method involves the following policy change:</span></span>  
  
-   <span data-ttu-id="c44c5-387"><xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> 和 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 方法可调用构造函数。</span><span class="sxs-lookup"><span data-stu-id="c44c5-387">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="c44c5-388">对于方法而言，`Activation` 策略仅会影响构造函数。</span><span class="sxs-lookup"><span data-stu-id="c44c5-388">For methods, the `Activation` policy affects constructors only.</span></span>  
  
 <span data-ttu-id="c44c5-389">将 `Activation` 策略应用于字段未产生任何效果。</span><span class="sxs-lookup"><span data-stu-id="c44c5-389">Applying the `Activation` policy to a field has no effect.</span></span>  
  
#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="c44c5-390">“序列化”策略的效果</span><span class="sxs-lookup"><span data-stu-id="c44c5-390">The effect of Serialize policy</span></span>  
 <span data-ttu-id="c44c5-391">`Serialize` 策略可启用基于反射的常用序列化程序。</span><span class="sxs-lookup"><span data-stu-id="c44c5-391">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="c44c5-392">但由于 Microsoft 不清楚非 Microsoft 序列化程序的确切反射访问模式，该策略可能无法完全生效。</span><span class="sxs-lookup"><span data-stu-id="c44c5-392">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>  
  
 <span data-ttu-id="c44c5-393">将 `Serialize` 策略应用于类型涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-393">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="c44c5-394">类型的基类型标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-394">The base type of the type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-395">如果类型为实例化泛型类型，则该类型的未实例化版本将标有 `Browse` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-395">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-396">如果类型为委托类型，则针对该类型的 `Invoke` 方法将标有 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-396">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-397">如果类型为枚举，则类型数组将标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-397">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-398">如果类型实施 <xref:System.Collections.Generic.IEnumerable%601>，则 `T` 将标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-398">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-399">如果类型为 <xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.Generic.IList%601>、<xref:System.Collections.Generic.ICollection%601>、<xref:System.Collections.Generic.IReadOnlyCollection%601>或 <xref:System.Collections.Generic.IReadOnlyList%601>，则 `T[]` 和 <xref:System.Collections.Generic.List%601> 将标有 `Serialize` 策略，但接口类型的所有成员均未标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-399">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-400">如果类型为 <xref:System.Collections.Generic.List%601>，则该类型的所有成员均未标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-400">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-401">如果类型为 <xref:System.Collections.Generic.IDictionary%602>，则 <xref:System.Collections.Generic.Dictionary%602> 将标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-401">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="c44c5-402">但该类型的所有成员均未标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-402">but no members of the type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-403">如果类型为 <xref:System.Collections.Generic.Dictionary%602>，则该类型的所有成员均未标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-403">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-404">如果类型实施 <xref:System.Collections.Generic.IDictionary%602>，则 `TKey` 和 `TValue` 均标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-404">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-405">每个构造函数、属性访问器和字段均标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-405">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>  
  
 <span data-ttu-id="c44c5-406">将 `Serialize` 策略应用于方法涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-406">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="c44c5-407">包含类型将标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-407">The containing type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-408">方法的返回类型将标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-408">The return type of the method is marked with the `Serialize` policy.</span></span>  
  
 <span data-ttu-id="c44c5-409">将 `Serialize` 策略应用于字段涉及下列策略更改：</span><span class="sxs-lookup"><span data-stu-id="c44c5-409">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>  
  
-   <span data-ttu-id="c44c5-410">包含类型将标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-410">The containing type is marked with the `Serialize` policy.</span></span>  
  
-   <span data-ttu-id="c44c5-411">字段类型将标有 `Serialize` 策略。</span><span class="sxs-lookup"><span data-stu-id="c44c5-411">The type of the field is marked with the `Serialize` policy.</span></span>  
  
#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserialier-policies"></a><span data-ttu-id="c44c5-412">XmlSerializer、DataContractSerializer 和 DataContractJsonSerialier 策略的效果</span><span class="sxs-lookup"><span data-stu-id="c44c5-412">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerialier policies</span></span>  
 <span data-ttu-id="c44c5-413">`Serialize` 策略适用于基于反射的序列化程序，而 `XmlSerializer`、`DataContractSerializer` 和 `DataContractJsonSerializer` 策略则用于启用一组 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 工具链已知的序列化程序。</span><span class="sxs-lookup"><span data-stu-id="c44c5-413">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the `XmlSerializer`, `DataContractSerializer`, and `DataContractJsonSerializer` policies are used to enable a set of serializers that are known to the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain.</span></span> <span data-ttu-id="c44c5-414">这些序列化程序并非通过反射实施，但却按照与确定可反射类型的设置类似的方式来确定可在运行时实现序列化的类型的设置。</span><span class="sxs-lookup"><span data-stu-id="c44c5-414">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>  
  
 <span data-ttu-id="c44c5-415">将这些策略之一应用于类型，该类型便可借助匹配的序列化程序实现序列化。</span><span class="sxs-lookup"><span data-stu-id="c44c5-415">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="c44c5-416">同样，任何序列化引擎可静态确定为需要序列化的类型也可实现序列化。</span><span class="sxs-lookup"><span data-stu-id="c44c5-416">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>  
  
 <span data-ttu-id="c44c5-417">这些策略对方法或字段无效。</span><span class="sxs-lookup"><span data-stu-id="c44c5-417">These policies have no effect on methods or fields.</span></span>  
  
 <span data-ttu-id="c44c5-418">有关详细信息，请参阅[将 Windows 应用商店应用迁移到 .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md) 中的“序列化程序的差异”一节。</span><span class="sxs-lookup"><span data-stu-id="c44c5-418">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44c5-419">请参阅</span><span class="sxs-lookup"><span data-stu-id="c44c5-419">See also</span></span>
- [<span data-ttu-id="c44c5-420">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="c44c5-420">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="c44c5-421">反射和 .NET Native</span><span class="sxs-lookup"><span data-stu-id="c44c5-421">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)
