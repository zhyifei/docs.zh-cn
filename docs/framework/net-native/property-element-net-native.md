---
title: <Property> 元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20657e0a583890b851ab8e15c50bce791a3641b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094484"
---
# <a name="property-element-net-native"></a><span data-ttu-id="fb229-102">\<属性 > 元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="fb229-102">\<Property> Element (.NET Native)</span></span>
<span data-ttu-id="fb229-103">将运行时反射策略应用到一个属性。</span><span class="sxs-lookup"><span data-stu-id="fb229-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb229-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb229-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb229-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fb229-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fb229-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fb229-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb229-107">特性</span><span class="sxs-lookup"><span data-stu-id="fb229-107">Attributes</span></span>  
  
|<span data-ttu-id="fb229-108">特性</span><span class="sxs-lookup"><span data-stu-id="fb229-108">Attribute</span></span>|<span data-ttu-id="fb229-109">特性类型</span><span class="sxs-lookup"><span data-stu-id="fb229-109">Attribute type</span></span>|<span data-ttu-id="fb229-110">描述</span><span class="sxs-lookup"><span data-stu-id="fb229-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="fb229-111">常规</span><span class="sxs-lookup"><span data-stu-id="fb229-111">General</span></span>|<span data-ttu-id="fb229-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="fb229-112">Required attribute.</span></span> <span data-ttu-id="fb229-113">指定属性名称。</span><span class="sxs-lookup"><span data-stu-id="fb229-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="fb229-114">映像</span><span class="sxs-lookup"><span data-stu-id="fb229-114">Reflection</span></span>|<span data-ttu-id="fb229-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="fb229-115">Optional attribute.</span></span> <span data-ttu-id="fb229-116">制对该属性信息的查询或列举该属性，但并不在运行时间启用任何动态访问。</span><span class="sxs-lookup"><span data-stu-id="fb229-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="fb229-117">映像</span><span class="sxs-lookup"><span data-stu-id="fb229-117">Reflection</span></span>|<span data-ttu-id="fb229-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="fb229-118">Optional attribute.</span></span> <span data-ttu-id="fb229-119">控制运行时对该属性的访问，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="fb229-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="fb229-120">该策略确保一个属性可在运行时间内得到设置或动态检索。</span><span class="sxs-lookup"><span data-stu-id="fb229-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="fb229-121">序列化</span><span class="sxs-lookup"><span data-stu-id="fb229-121">Serialization</span></span>|<span data-ttu-id="fb229-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="fb229-122">Optional attribute.</span></span> <span data-ttu-id="fb229-123">控制运行时对一个属性的访问以启用类型实例，使其通过程序库得到序列化，例如通过 Newtonsoft JSON 序列化程序，或被用于绑定数据。</span><span class="sxs-lookup"><span data-stu-id="fb229-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="fb229-124">Name 特性</span><span class="sxs-lookup"><span data-stu-id="fb229-124">Name attribute</span></span>  
  
|<span data-ttu-id="fb229-125">“值”</span><span class="sxs-lookup"><span data-stu-id="fb229-125">Value</span></span>|<span data-ttu-id="fb229-126">描述</span><span class="sxs-lookup"><span data-stu-id="fb229-126">Description</span></span>|  
|-----------|-----------------|  
|*<span data-ttu-id="fb229-127">方法_名称</span><span class="sxs-lookup"><span data-stu-id="fb229-127">method_name</span></span>*|<span data-ttu-id="fb229-128">属性名称。</span><span class="sxs-lookup"><span data-stu-id="fb229-128">The property name.</span></span> <span data-ttu-id="fb229-129">该属性的类型由 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 或 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 父元素定义。</span><span class="sxs-lookup"><span data-stu-id="fb229-129">The type of the property is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="fb229-130">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="fb229-130">All other attributes</span></span>  
  
|<span data-ttu-id="fb229-131">“值”</span><span class="sxs-lookup"><span data-stu-id="fb229-131">Value</span></span>|<span data-ttu-id="fb229-132">描述</span><span class="sxs-lookup"><span data-stu-id="fb229-132">Description</span></span>|  
|-----------|-----------------|  
|*<span data-ttu-id="fb229-133">策略_设置</span><span class="sxs-lookup"><span data-stu-id="fb229-133">policy_setting</span></span>*|<span data-ttu-id="fb229-134">该设置将应用到这个属性的策略类型。</span><span class="sxs-lookup"><span data-stu-id="fb229-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="fb229-135">可能值为 `Auto`、`Excluded`、`Included` 和 `Required`。</span><span class="sxs-lookup"><span data-stu-id="fb229-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="fb229-136">有关详细信息，请参阅[运行时指令策略设置](../../../docs/framework/net-native/runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="fb229-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb229-137">子元素</span><span class="sxs-lookup"><span data-stu-id="fb229-137">Child Elements</span></span>  
 <span data-ttu-id="fb229-138">无。</span><span class="sxs-lookup"><span data-stu-id="fb229-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb229-139">父元素</span><span class="sxs-lookup"><span data-stu-id="fb229-139">Parent Elements</span></span>  
  
|<span data-ttu-id="fb229-140">元素</span><span class="sxs-lookup"><span data-stu-id="fb229-140">Element</span></span>|<span data-ttu-id="fb229-141">描述</span><span class="sxs-lookup"><span data-stu-id="fb229-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb229-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="fb229-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="fb229-143">将反射策略应用到一种类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="fb229-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="fb229-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="fb229-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="fb229-145">将反射策略应用到一种构造泛型类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="fb229-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb229-146">备注</span><span class="sxs-lookup"><span data-stu-id="fb229-146">Remarks</span></span>  
 <span data-ttu-id="fb229-147">如果一个属性的策略没有得到显式定义，它将继承其父元素的运行时间策略。</span><span class="sxs-lookup"><span data-stu-id="fb229-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb229-148">示例</span><span class="sxs-lookup"><span data-stu-id="fb229-148">Example</span></span>  
 <span data-ttu-id="fb229-149">以下实例使用反射实例化了一个 `Book` 对象并显示了其属性值。</span><span class="sxs-lookup"><span data-stu-id="fb229-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="fb229-150">该项目的原始 default.rd.xml 文件显示如下：</span><span class="sxs-lookup"><span data-stu-id="fb229-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="fb229-151">该文件将 `All` 值应用到允许通过反射访问类构造函数的 `Activate` 的类的 `Book` 策略。</span><span class="sxs-lookup"><span data-stu-id="fb229-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="fb229-152">`Browse` 类的 `Book` 策略是从其父命名空间继承的。</span><span class="sxs-lookup"><span data-stu-id="fb229-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="fb229-153">这已设置为 `Required Public`，这使得元数据在运行时可用。</span><span class="sxs-lookup"><span data-stu-id="fb229-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="fb229-154">以下是该实例的源代码。</span><span class="sxs-lookup"><span data-stu-id="fb229-154">The following is the source code for the example.</span></span> <span data-ttu-id="fb229-155">`outputBlock`变量表示<xref:Windows.UI.Xaml.Controls.TextBlock>控件。</span><span class="sxs-lookup"><span data-stu-id="fb229-155">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="fb229-156">然而，编译和执行此示例将引发 [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) 异常。</span><span class="sxs-lookup"><span data-stu-id="fb229-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="fb229-157">尽管我们已经使 `Book` 类型的元数据变得可用，我们却未使属性获取者的实施变得动态可用。</span><span class="sxs-lookup"><span data-stu-id="fb229-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="fb229-158">我们可通过以下方法之一纠正这个错误：</span><span class="sxs-lookup"><span data-stu-id="fb229-158">We can correct this error by either in one of two ways:</span></span>  
  
-   <span data-ttu-id="fb229-159">通过在其 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) 元素中为 `Book` 类型定义 `Dynamic` 策略。</span><span class="sxs-lookup"><span data-stu-id="fb229-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element.</span></span>  
  
-   <span data-ttu-id="fb229-160">通过为我们想要调用其 getter 的每个属性添加一个嵌套 [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) 元素，如以下 default.rd.xml 文件所示。</span><span class="sxs-lookup"><span data-stu-id="fb229-160">By adding a nested [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fb229-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb229-161">See also</span></span>

- [<span data-ttu-id="fb229-162">运行时指令 (rd.xml) 配置文件引用</span><span class="sxs-lookup"><span data-stu-id="fb229-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="fb229-163">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="fb229-163">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="fb229-164">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="fb229-164">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
