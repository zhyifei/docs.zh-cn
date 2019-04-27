---
title: 数据协定名称
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], naming
ms.assetid: 31f87e6c-247b-48f5-8e94-b9e1e33d8d09
ms.openlocfilehash: 16a42a2808104a77e56e93564a679dfc578e73f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857269"
---
# <a name="data-contract-names"></a><span data-ttu-id="ba5fa-102">数据协定名称</span><span class="sxs-lookup"><span data-stu-id="ba5fa-102">Data Contract Names</span></span>

<span data-ttu-id="ba5fa-103">有时，客户端和服务不共享相同的类型。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-103">Sometimes a client and a service do not share the same types.</span></span> <span data-ttu-id="ba5fa-104">它们仍然可以将数据传递给对方，只要数据协定是双方等效的。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-104">They can still pass data to each other as long as the data contracts are equivalent on both sides.</span></span> <span data-ttu-id="ba5fa-105">[数据协定等效性](data-contract-equivalence.md)基于数据协定和数据成员名称，并因此提供一种机制，以将类型和成员映射到这些名称。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-105">[Data Contract Equivalence](data-contract-equivalence.md) is based on data contract and data member names, and therefore a mechanism is provided to map types and members to those names.</span></span> <span data-ttu-id="ba5fa-106">本主题介绍命名数据协定，以及 Windows Communication Foundation (WCF) 基础结构的默认行为，创建名称时的规则。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-106">This topic explains the rules for naming data contracts as well as the default behavior of the Windows Communication Foundation (WCF) infrastructure when creating names.</span></span>

## <a name="basic-rules"></a><span data-ttu-id="ba5fa-107">基本规则</span><span class="sxs-lookup"><span data-stu-id="ba5fa-107">Basic Rules</span></span>
<span data-ttu-id="ba5fa-108">有关数据协定命名的基本规则包括：</span><span class="sxs-lookup"><span data-stu-id="ba5fa-108">Basic rules regarding naming data contracts include:</span></span>

- <span data-ttu-id="ba5fa-109">完全限定的数据协定名称由命名空间和名称组成。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-109">A fully-qualified data contract name consists of a namespace and a name.</span></span>

- <span data-ttu-id="ba5fa-110">数据成员只有名称，而没有命名空间。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-110">Data members have only names, but no namespaces.</span></span>

- <span data-ttu-id="ba5fa-111">在处理数据协定，WCF 基础结构是区分大小写到命名空间和数据协定和数据成员的名称。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-111">When processing data contracts, the WCF infrastructure is case-sensitive to both the namespaces and the names of data contracts and data members.</span></span>

## <a name="data-contract-namespaces"></a><span data-ttu-id="ba5fa-112">数据协定命名空间</span><span class="sxs-lookup"><span data-stu-id="ba5fa-112">Data Contract Namespaces</span></span>
<span data-ttu-id="ba5fa-113">数据协定命名空间采用统一资源标识符 (URI) 的形式。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-113">A data contract namespace takes the form of a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="ba5fa-114">URI 可以是绝对的，也可以是相对的。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-114">The URI can be either absolute or relative.</span></span> <span data-ttu-id="ba5fa-115">默认情况下，会为特定类型的数据协定分配公共语言运行库 (CLR) 命名空间中该类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-115">By default, data contracts for a particular type are assigned a namespace that comes from the common language runtime (CLR) namespace of that type.</span></span>

<span data-ttu-id="ba5fa-116">默认情况下，任何给定的 CLR 命名空间 (采用格式*Clr.Namespace*) 映射到命名空间`http://schemas.datacontract.org/2004/07/Clr.Namespace`。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-116">By default, any given CLR namespace (in the format *Clr.Namespace*) is mapped to the namespace `http://schemas.datacontract.org/2004/07/Clr.Namespace`.</span></span> <span data-ttu-id="ba5fa-117">若要重写此默认值，请对整个模块或程序集应用 <xref:System.Runtime.Serialization.ContractNamespaceAttribute> 属性。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-117">To override this default, apply the <xref:System.Runtime.Serialization.ContractNamespaceAttribute> attribute to the entire module or assembly.</span></span> <span data-ttu-id="ba5fa-118">或者，若要控制每种类型的数据协定命名空间，请设置 <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> 的 <xref:System.Runtime.Serialization.DataContractAttribute> 属性。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-118">Alternatively, to control the data contract namespace for each type, set the <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> property of the <xref:System.Runtime.Serialization.DataContractAttribute>.</span></span>

> [!NOTE]
> <span data-ttu-id="ba5fa-119">`http://schemas.microsoft.com/2003/10/Serialization`命名空间是保留，不能用作数据协定命名空间。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-119">The `http://schemas.microsoft.com/2003/10/Serialization` namespace is reserved and cannot be used as a data contract namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="ba5fa-120">不能重写包含 `delegate` 声明的数据协定类型中的默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-120">You cannot override the default namespace in data contract types that contain `delegate` declarations.</span></span>

## <a name="data-contract-names"></a><span data-ttu-id="ba5fa-121">数据协定名称</span><span class="sxs-lookup"><span data-stu-id="ba5fa-121">Data Contract Names</span></span>
<span data-ttu-id="ba5fa-122">给定类型的默认数据协定名称是该类型的名称。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-122">The default name of a data contract for a given type is the name of that type.</span></span> <span data-ttu-id="ba5fa-123">若要重写默认值，请将 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> 的 <xref:System.Runtime.Serialization.DataContractAttribute> 属性设置为其他名称。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-123">To override the default, set the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> property of the <xref:System.Runtime.Serialization.DataContractAttribute> to an alternative name.</span></span> <span data-ttu-id="ba5fa-124">本主题中后面的“泛型类型的数据协定名称”中说明了泛型类型的特殊规则。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-124">Special rules for generic types are described in "Data Contract Names for Generic Types" later in this topic.</span></span>

## <a name="data-member-names"></a><span data-ttu-id="ba5fa-125">数据成员名称</span><span class="sxs-lookup"><span data-stu-id="ba5fa-125">Data Member Names</span></span>
<span data-ttu-id="ba5fa-126">给定字段或属性的默认数据成员名称是该字段或属性的名称。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-126">The default name of a data member for a given field or property is the name of that field or property.</span></span> <span data-ttu-id="ba5fa-127">若要重写默认值，请将 <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> 的 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性设置为其他值。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-127">To override the default, set the <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> to an alternative value.</span></span>

### <a name="examples"></a><span data-ttu-id="ba5fa-128">示例</span><span class="sxs-lookup"><span data-stu-id="ba5fa-128">Examples</span></span>
<span data-ttu-id="ba5fa-129">下面的示例演示如何重写数据协定和数据成员的默认命名行为。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-129">The following example shows how you can override the default naming behavior of data contracts and data members.</span></span>

[!code-csharp[C_DataContractNames#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#1)]
[!code-vb[C_DataContractNames#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#1)]

## <a name="data-contract-names-for-generic-types"></a><span data-ttu-id="ba5fa-130">泛型类型的数据协定名称</span><span class="sxs-lookup"><span data-stu-id="ba5fa-130">Data Contract Names for Generic Types</span></span>
<span data-ttu-id="ba5fa-131">确定泛型类型的数据协定名称具有特殊的规则。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-131">Special rules exist for determining data contract names for generic types.</span></span> <span data-ttu-id="ba5fa-132">这些规则有助于避免在同一泛型类型的两个封闭式泛型之间发生数据协定名称冲突。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-132">These rules help avoid data contract name collisions between two closed generics of the same generic type.</span></span>

<span data-ttu-id="ba5fa-133">默认情况下的数据协定名称为泛型类型的类型，字符串"Of"后, 跟的名称后跟数据协定名称的泛型参数后, 跟*哈希*使用数据协定命名空间的计算泛型参数。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-133">By default, the data contract name for a generic type is the name of the type, followed by the string "Of", followed by the data contract names of the generic parameters, followed by a *hash* computed using the data contract namespaces of the generic parameters.</span></span> <span data-ttu-id="ba5fa-134">哈希值是作为唯一标识数据片段的“指纹”的数学函数的计算结果。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-134">A hash is the result of a mathematical function that acts as a "fingerprint" that uniquely identifies a piece of data.</span></span> <span data-ttu-id="ba5fa-135">当所有的泛型参数都是基元类型时，将忽略哈希值。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-135">When all of the generic parameters are primitive types, the hash is omitted.</span></span>

<span data-ttu-id="ba5fa-136">有关示例，请参见以下示例中的类型。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-136">For example, see the types in the following example.</span></span>

[!code-csharp[C_DataContractNames#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#2)]
[!code-vb[C_DataContractNames#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#2)]

<span data-ttu-id="ba5fa-137">在此示例中，`Drawing<Square,RegularRedBrush>` 类型具有数据协定名称“DrawingOfSquareRedBrush5HWGAU6h”，其中“5HWGAU6h”是“urn:shapes”和“urn:default”命名空间的哈希值。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-137">In this example, the type `Drawing<Square,RegularRedBrush>` has the data contract name "DrawingOfSquareRedBrush5HWGAU6h", where "5HWGAU6h" is a hash of the "urn:shapes" and "urn:default" namespaces.</span></span> <span data-ttu-id="ba5fa-138">`Drawing<Square,SpecialRedBrush>` 类型具有数据协定名称“DrawingOfSquareRedBrushjpB5LgQ_S”，其中“jpB5LgQ_S”是“urn:shapes”和“urn:special”命名空间的哈希值。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-138">The type `Drawing<Square,SpecialRedBrush>` has the data contract name "DrawingOfSquareRedBrushjpB5LgQ_S", where "jpB5LgQ_S" is a hash of the "urn:shapes" and the "urn:special" namespaces.</span></span> <span data-ttu-id="ba5fa-139">请注意，如果不使用哈希值，则这两个名称将完全相同，因此会发生名称冲突。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-139">Note that if the hash is not used, the two names are identical, and thus a name collision occurs.</span></span>

## <a name="customizing-data-contract-names-for-generic-types"></a><span data-ttu-id="ba5fa-140">泛型类型的自定义数据协定名称</span><span class="sxs-lookup"><span data-stu-id="ba5fa-140">Customizing data contract names for generic types</span></span>

<span data-ttu-id="ba5fa-141">有时不允许为泛型类型生成数据协定名称，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-141">Sometimes, the data contract names generated for generic types, as described previously, are unacceptable.</span></span> <span data-ttu-id="ba5fa-142">例如，您可能事先知道不会遇到名称冲突并且想删除哈希值。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-142">For example, you may know in advance that you will not run into name collisions and may want to remove the hash.</span></span> <span data-ttu-id="ba5fa-143">在这种情况下，可以使用<xref:System.Runtime.Serialization.DataContractAttribute.Name%2A?displayProperty=nameWithType>属性来指定不同的方式生成名称。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-143">In this case, you can use the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A?displayProperty=nameWithType> property to specify a different way to generate names.</span></span> <span data-ttu-id="ba5fa-144">您可以在 `Name` 属性内的大括号中使用数字来引用泛型参数的数据协定名称。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-144">You can use numbers in curly braces inside of the `Name` property to refer to data contract names of the generic parameters.</span></span> <span data-ttu-id="ba5fa-145">（0 指第一个参数，1 指第二个参数，依此类推。）可以在大括号内使用数字符号 (#) 来引用哈希值。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-145">(0 refers to the first parameter, 1 refers to the second, and so on.) You can use a number (#) sign inside curly braces to refer to the hash.</span></span> <span data-ttu-id="ba5fa-146">您可以多次使用这些引用，也可以不使用引用。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-146">You can use each of these references multiple times or not at all.</span></span>

<span data-ttu-id="ba5fa-147">例如，可能对前面的泛型 `Drawing` 类型进行了声明，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-147">For example, the preceding generic `Drawing` type could have been declared as shown in the following example.</span></span>

[!code-csharp[c_DataContractNames#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#3)]
[!code-vb[c_DataContractNames#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#3)]

<span data-ttu-id="ba5fa-148">在这种情况下，`Drawing<Square,RegularRedBrush>` 类型具有数据协定名称“Drawing_using_RedBrush_brush_and_Square_shape”。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-148">In this case, the type `Drawing<Square,RegularRedBrush>` has the data contract name "Drawing_using_RedBrush_brush_and_Square_shape".</span></span> <span data-ttu-id="ba5fa-149">请注意，因为 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> 属性中有一个“{#}”，哈希值不是名称的一部分，因此该类型容易发生命名冲突；例如，`Drawing<Square,SpecialRedBrush>` 类型将具有完全相同的数据协定名称。</span><span class="sxs-lookup"><span data-stu-id="ba5fa-149">Note that because there is a "{#}" in the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> property, the hash is not a part of the name, and thus the type is susceptible to naming collisions; for example, the type `Drawing<Square,SpecialRedBrush>` would have exactly the same data contract name.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba5fa-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba5fa-150">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.ContractNamespaceAttribute>
- [<span data-ttu-id="ba5fa-151">使用数据协定</span><span class="sxs-lookup"><span data-stu-id="ba5fa-151">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="ba5fa-152">数据协定等效性</span><span class="sxs-lookup"><span data-stu-id="ba5fa-152">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="ba5fa-153">数据协定名称</span><span class="sxs-lookup"><span data-stu-id="ba5fa-153">Data Contract Names</span></span>](data-contract-names.md)
- [<span data-ttu-id="ba5fa-154">数据协定版本控制</span><span class="sxs-lookup"><span data-stu-id="ba5fa-154">Data Contract Versioning</span></span>](data-contract-versioning.md)
