---
title: "数据协定架构参考"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 261d6e41ca79ca245b104513a92306ab8833c905
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="data-contract-schema-reference"></a><span data-ttu-id="6c70a-102">数据协定架构参考</span><span class="sxs-lookup"><span data-stu-id="6c70a-102">Data Contract Schema Reference</span></span>
<span data-ttu-id="6c70a-103">本主题介绍 <xref:System.Runtime.Serialization.DataContractSerializer> 用来描述 XML 序列化的公共语言运行库 (CLR) 类型的 XML 架构 (XSD) 的子集。</span><span class="sxs-lookup"><span data-stu-id="6c70a-103">This topic describes the subset of the XML Schema (XSD) used by <xref:System.Runtime.Serialization.DataContractSerializer> to describe common language runtime (CLR) types for XML serialization.</span></span>  
  
## <a name="datacontractserializer-mappings"></a><span data-ttu-id="6c70a-104">DataContractSerializer 映射</span><span class="sxs-lookup"><span data-stu-id="6c70a-104">DataContractSerializer Mappings</span></span>  
 <span data-ttu-id="6c70a-105">在使用元数据终结点或 `DataContractSerializer` 从 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务中导出元数据时， [DataContractSerializer](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)将 CLR 类型映射到 XSD。</span><span class="sxs-lookup"><span data-stu-id="6c70a-105">The `DataContractSerializer` maps CLR types to XSD when metadata is exported from a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service using a metadata endpoint or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="6c70a-106">[数据协定序列化程序](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)。</span><span class="sxs-lookup"><span data-stu-id="6c70a-106"> [Data Contract Serializer](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md).</span></span>  
  
 <span data-ttu-id="6c70a-107">在使用 Svcutil.exe 访问 Web 服务描述语言 (WSDL) 或 XSD 并生成服务或客户端的数据协定时， `DataContractSerializer` 还会将 XSD 映射到 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-107">The `DataContractSerializer` also maps XSD to CLR types when Svcutil.exe is used to access Web Services Description Language (WSDL) or XSD documents and generate data contracts for services or clients.</span></span>  
  
 <span data-ttu-id="6c70a-108">只有符合此文档中所述需要的 XML 架构实例才可以使用 `DataContractSerializer`映射到 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-108">Only XML Schema instances that conform to requirements stated in this document can be mapped to CLR types using `DataContractSerializer`.</span></span>  
  
### <a name="support-levels"></a><span data-ttu-id="6c70a-109">支持级别</span><span class="sxs-lookup"><span data-stu-id="6c70a-109">Support Levels</span></span>  
 <span data-ttu-id="6c70a-110">`DataContractSerializer` 提供对于给定的 XML 架构功能提供以下支持级别：</span><span class="sxs-lookup"><span data-stu-id="6c70a-110">The `DataContractSerializer` provides the following levels of support for a given XML Schema feature:</span></span>  
  
-   <span data-ttu-id="6c70a-111">**支持**。</span><span class="sxs-lookup"><span data-stu-id="6c70a-111">**Supported**.</span></span> <span data-ttu-id="6c70a-112">从此功能到使用 `DataContractSerializer`的 CLR 类型或属性（或二者）具有显式映射。</span><span class="sxs-lookup"><span data-stu-id="6c70a-112">There is explicit mapping from this feature to CLR types or attributes (or both) using `DataContractSerializer`.</span></span>  
  
-   <span data-ttu-id="6c70a-113">**已忽略**。</span><span class="sxs-lookup"><span data-stu-id="6c70a-113">**Ignored**.</span></span> <span data-ttu-id="6c70a-114">在 `DataContractSerializer`导入的架构中允许此功能，当对代码生成无任何影响。</span><span class="sxs-lookup"><span data-stu-id="6c70a-114">The feature is allowed in schemas imported by the `DataContractSerializer`, but has no effect on code generation.</span></span>  
  
-   <span data-ttu-id="6c70a-115">**已禁止**。</span><span class="sxs-lookup"><span data-stu-id="6c70a-115">**Forbidden**.</span></span> <span data-ttu-id="6c70a-116">`DataContractSerializer` 不支持导入使用此功能的架构。</span><span class="sxs-lookup"><span data-stu-id="6c70a-116">The `DataContractSerializer` does not support importing a schema using the feature.</span></span> <span data-ttu-id="6c70a-117">例如，Svcutil.exe 在访问带有使用这类功能的架构的 WSDL 时会转而改用 <xref:System.Xml.Serialization.XmlSerializer> 。</span><span class="sxs-lookup"><span data-stu-id="6c70a-117">For example, Svcutil.exe, when accessing a WSDL with a schema that uses such a feature, falls back to using the <xref:System.Xml.Serialization.XmlSerializer> instead.</span></span> <span data-ttu-id="6c70a-118">这是默认情况。</span><span class="sxs-lookup"><span data-stu-id="6c70a-118">This is by default.</span></span>  
  
## <a name="general-information"></a><span data-ttu-id="6c70a-119">常规信息</span><span class="sxs-lookup"><span data-stu-id="6c70a-119">General Information</span></span>  
  
-   <span data-ttu-id="6c70a-120">架构命名空间在 [XML 架构](http://go.microsoft.com/fwlink/?LinkId=95475)中描述。</span><span class="sxs-lookup"><span data-stu-id="6c70a-120">The schema namespace is described at [XML Schema](http://go.microsoft.com/fwlink/?LinkId=95475).</span></span> <span data-ttu-id="6c70a-121">在此文档中使用前缀“xs”。</span><span class="sxs-lookup"><span data-stu-id="6c70a-121">The prefix "xs" is used in this document.</span></span>  
  
-   <span data-ttu-id="6c70a-122">将忽略具有非架构命名空间的任何属性。</span><span class="sxs-lookup"><span data-stu-id="6c70a-122">Any attributes with a non-schema namespace are ignored.</span></span>  
  
-   <span data-ttu-id="6c70a-123">将忽略任何批注（在此文档中描述的批注除外）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-123">Any annotations (except for those described in this document) are ignored.</span></span>  
  
### <a name="xsschema-attributes"></a><span data-ttu-id="6c70a-124">\<xs:schema >： 属性</span><span class="sxs-lookup"><span data-stu-id="6c70a-124">\<xs:schema>: attributes</span></span>  
  
|<span data-ttu-id="6c70a-125">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-125">Attribute</span></span>|<span data-ttu-id="6c70a-126">DataContract</span><span class="sxs-lookup"><span data-stu-id="6c70a-126">DataContract</span></span>|  
|---------------|------------------|  
|`attributeFormDefault`|<span data-ttu-id="6c70a-127">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-127">Ignored.</span></span>|  
|`blockDefault`|<span data-ttu-id="6c70a-128">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-128">Ignored.</span></span>|  
|`elementFormDefault`|<span data-ttu-id="6c70a-129">必须进行限定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-129">Must be qualified.</span></span> <span data-ttu-id="6c70a-130">必须对一个架构的所有元素进行限定才能得到 `DataContractSerializer`的支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-130">All elements must be qualified for a schema to be supported by `DataContractSerializer`.</span></span> <span data-ttu-id="6c70a-131">这可以通过这两个设置xs:schema/@elementFormDefault到"限定"或通过设置xs:element/@form为"限定"上每个单独元素声明。</span><span class="sxs-lookup"><span data-stu-id="6c70a-131">This can be accomplished by either setting xs:schema/@elementFormDefault to "qualified" or by setting xs:element/@form to "qualified" on each individual element declaration.</span></span>|  
|`finalDefault`|<span data-ttu-id="6c70a-132">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-132">Ignored.</span></span>|  
|`Id`|<span data-ttu-id="6c70a-133">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-133">Ignored.</span></span>|  
|`targetNamespace`|<span data-ttu-id="6c70a-134">支持，并已映射到数据协定命名空间。</span><span class="sxs-lookup"><span data-stu-id="6c70a-134">Supported and mapped to the data contract namespace.</span></span> <span data-ttu-id="6c70a-135">如果未指定此属性，则使用空白命名空间。</span><span class="sxs-lookup"><span data-stu-id="6c70a-135">If this attribute is not specified, the blank namespace is used.</span></span> <span data-ttu-id="6c70a-136">不可以是保留的命名空间 http://schemas.microsoft.com/2003/10/Serialization/。</span><span class="sxs-lookup"><span data-stu-id="6c70a-136">Cannot be the reserved namespace http://schemas.microsoft.com/2003/10/Serialization/.</span></span>|  
|`version`|<span data-ttu-id="6c70a-137">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-137">Ignored.</span></span>|  
  
### <a name="xsschema-contents"></a><span data-ttu-id="6c70a-138">\<xs:schema >： 内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-138">\<xs:schema>: contents</span></span>  
  
|<span data-ttu-id="6c70a-139">内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-139">Contents</span></span>|<span data-ttu-id="6c70a-140">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-140">Schema</span></span>|  
|--------------|------------|  
|`include`|<span data-ttu-id="6c70a-141">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-141">Supported.</span></span> <span data-ttu-id="6c70a-142">`DataContractSerializer` 支持 xs:include 和 xs:import。</span><span class="sxs-lookup"><span data-stu-id="6c70a-142">`DataContractSerializer` supports xs:include and xs:import.</span></span> <span data-ttu-id="6c70a-143">但是，从本地文件加载元数据时，Svcutil.exe 会限制下面的 `xs:include/@schemaLocation` 和 `xs:import/@location` 引用。</span><span class="sxs-lookup"><span data-stu-id="6c70a-143">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="6c70a-144">在这种情况下，必须通过带外机制而非通过 `include` 来传递架构文件的列表；将忽略 `include`架构文档。</span><span class="sxs-lookup"><span data-stu-id="6c70a-144">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|  
|`redefine`|<span data-ttu-id="6c70a-145">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-145">Forbidden.</span></span> <span data-ttu-id="6c70a-146">出于安全方面的原因， `xs:redefine` 禁止使用 `DataContractSerializer` ： `x:redefine` 要求后跟 `schemaLocation` 。</span><span class="sxs-lookup"><span data-stu-id="6c70a-146">The use of `xs:redefine` is forbidden by `DataContractSerializer` for security reasons: `x:redefine` requires `schemaLocation` to be followed.</span></span> <span data-ttu-id="6c70a-147">在某些情况下，使用 DataContract 的 Svcutil.exe 会限制 `schemaLocation`的使用。</span><span class="sxs-lookup"><span data-stu-id="6c70a-147">In certain circumstances, Svcutil.exe using DataContract restricts use of `schemaLocation`.</span></span>|  
|`import`|<span data-ttu-id="6c70a-148">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-148">Supported.</span></span> <span data-ttu-id="6c70a-149">`DataContractSerializer` 支持 `xs:include` 和 `xs:import`。</span><span class="sxs-lookup"><span data-stu-id="6c70a-149">`DataContractSerializer` supports `xs:include` and `xs:import`.</span></span> <span data-ttu-id="6c70a-150">但是，从本地文件加载元数据时，Svcutil.exe 会限制下面的 `xs:include/@schemaLocation` 和 `xs:import/@location` 引用。</span><span class="sxs-lookup"><span data-stu-id="6c70a-150">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="6c70a-151">在这种情况下，必须通过带外机制而非通过 `include` 来传递架构文件的列表；将忽略 `include`架构文档。</span><span class="sxs-lookup"><span data-stu-id="6c70a-151">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|  
|`simpleType`|<span data-ttu-id="6c70a-152">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-152">Supported.</span></span> <span data-ttu-id="6c70a-153">请参见“ `xs:simpleType` ”一节。</span><span class="sxs-lookup"><span data-stu-id="6c70a-153">See the `xs:simpleType` section.</span></span>|  
|`complexType`|<span data-ttu-id="6c70a-154">支持，将映射到数据协定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-154">Supported, maps to data contracts.</span></span> <span data-ttu-id="6c70a-155">请参见“ `xs:complexType` ”一节。</span><span class="sxs-lookup"><span data-stu-id="6c70a-155">See the `xs:complexType` section.</span></span>|  
|`group`|<span data-ttu-id="6c70a-156">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-156">Ignored.</span></span> <span data-ttu-id="6c70a-157">`DataContractSerializer` 不支持使用 `xs:group`、 `xs:attributeGroup`和 `xs:attribute`。</span><span class="sxs-lookup"><span data-stu-id="6c70a-157">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="6c70a-158">这些声明将作为 `xs:schema`子级被忽略，但无法从 `complexType` 或其他支持的结构内引用。</span><span class="sxs-lookup"><span data-stu-id="6c70a-158">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`attributeGroup`|<span data-ttu-id="6c70a-159">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-159">Ignored.</span></span> <span data-ttu-id="6c70a-160">`DataContractSerializer` 不支持使用 `xs:group`、 `xs:attributeGroup`和 `xs:attribute`。</span><span class="sxs-lookup"><span data-stu-id="6c70a-160">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="6c70a-161">这些声明将作为 `xs:schema`子级被忽略，但无法从 `complexType` 或其他支持的结构内引用。</span><span class="sxs-lookup"><span data-stu-id="6c70a-161">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`element`|<span data-ttu-id="6c70a-162">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-162">Supported.</span></span> <span data-ttu-id="6c70a-163">请参见“全局元素声明 (GED)”。</span><span class="sxs-lookup"><span data-stu-id="6c70a-163">See Global Element Declaration (GED).</span></span>|  
|`attribute`|<span data-ttu-id="6c70a-164">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-164">Ignored.</span></span> <span data-ttu-id="6c70a-165">`DataContractSerializer` 不支持使用 `xs:group`、 `xs:attributeGroup`和 `xs:attribute`。</span><span class="sxs-lookup"><span data-stu-id="6c70a-165">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="6c70a-166">这些声明将作为 `xs:schema`子级被忽略，但无法从 `complexType` 或其他支持的结构内引用。</span><span class="sxs-lookup"><span data-stu-id="6c70a-166">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|  
|`notation`|<span data-ttu-id="6c70a-167">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-167">Ignored.</span></span>|  
  
## <a name="complex-types--xscomplextype"></a><span data-ttu-id="6c70a-168">复杂类型 – \<xs:complexType ></span><span class="sxs-lookup"><span data-stu-id="6c70a-168">Complex Types – \<xs:complexType></span></span>  
  
### <a name="general-information"></a><span data-ttu-id="6c70a-169">常规信息</span><span class="sxs-lookup"><span data-stu-id="6c70a-169">General Information</span></span>  
 <span data-ttu-id="6c70a-170">每个复杂类型\<xs:complexType > 映射到数据协定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-170">Each complex type \<xs:complexType> maps to a data contract.</span></span>  
  
### <a name="xscomplextype-attributes"></a><span data-ttu-id="6c70a-171">\<xs:complexType >： 属性</span><span class="sxs-lookup"><span data-stu-id="6c70a-171">\<xs:complexType>: attributes</span></span>  
  
|<span data-ttu-id="6c70a-172">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-172">Attribute</span></span>|<span data-ttu-id="6c70a-173">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-173">Schema</span></span>|  
|---------------|------------|  
|`abstract`|<span data-ttu-id="6c70a-174">必须是 false（默认值）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-174">Must be false (default).</span></span>|  
|`block`|<span data-ttu-id="6c70a-175">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-175">Forbidden.</span></span>|  
|`final`|<span data-ttu-id="6c70a-176">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-176">Ignored.</span></span>|  
|`id`|<span data-ttu-id="6c70a-177">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-177">Ignored.</span></span>|  
|`mixed`|<span data-ttu-id="6c70a-178">必须是 false（默认值）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-178">Must be false (default).</span></span>|  
|`name`|<span data-ttu-id="6c70a-179">支持，并已映射到数据协定名称。</span><span class="sxs-lookup"><span data-stu-id="6c70a-179">Supported and mapped to the data contract name.</span></span> <span data-ttu-id="6c70a-180">如果名称中有句点，则尝试将类型映射到内部类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-180">If there are periods in the name, an attempt is made to map the type to an inner type.</span></span> <span data-ttu-id="6c70a-181">例如，名为 `A.B` 的复杂类型将映射到一个数据协定类型，该数据协定类型是具有数据协定名称 `A`的类型的内部类型，但前提是这种数据协定类型存在。</span><span class="sxs-lookup"><span data-stu-id="6c70a-181">For example, a complex type named `A.B` maps to a data contract type that is an inner type of a type with the data contract name `A`, but only if such a data contract type exists.</span></span> <span data-ttu-id="6c70a-182">嵌套可能有多个级别：例如， `A.B.C` 可以是内部类型，但前提是 `A` 和 `A.B` 两者都存在。</span><span class="sxs-lookup"><span data-stu-id="6c70a-182">More than one level of nesting is possible: for example, `A.B.C` can be an inner type, but only if `A` and `A.B` both exist.</span></span>|  
  
### <a name="xscomplextype-contents"></a><span data-ttu-id="6c70a-183">\<xs:complexType >： 内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-183">\<xs:complexType>: contents</span></span>  
  
|<span data-ttu-id="6c70a-184">内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-184">Contents</span></span>|<span data-ttu-id="6c70a-185">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-185">Schema</span></span>|  
|--------------|------------|  
|`simpleContent`|<span data-ttu-id="6c70a-186">禁止扩展。</span><span class="sxs-lookup"><span data-stu-id="6c70a-186">Extensions are forbidden.</span></span><br /><br /> <span data-ttu-id="6c70a-187">仅允许从 `anySimpleType`进行限制。</span><span class="sxs-lookup"><span data-stu-id="6c70a-187">Restriction is allowed only from `anySimpleType`.</span></span>|  
|`complexContent`|<span data-ttu-id="6c70a-188">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-188">Supported.</span></span> <span data-ttu-id="6c70a-189">请参见“继承”。</span><span class="sxs-lookup"><span data-stu-id="6c70a-189">See "Inheritance".</span></span>|  
|`group`|<span data-ttu-id="6c70a-190">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-190">Forbidden.</span></span>|  
|`all`|<span data-ttu-id="6c70a-191">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-191">Forbidden.</span></span>|  
|`choice`|<span data-ttu-id="6c70a-192">已禁止</span><span class="sxs-lookup"><span data-stu-id="6c70a-192">Forbidden</span></span>|  
|`sequence`|<span data-ttu-id="6c70a-193">支持，将映射到数据协定的数据成员。</span><span class="sxs-lookup"><span data-stu-id="6c70a-193">Supported, maps to data members of a data contract.</span></span>|  
|`attribute`|<span data-ttu-id="6c70a-194">已禁止，即使 use="prohibited"（但有一个例外）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-194">Forbidden, even if use="prohibited" (with one exception).</span></span> <span data-ttu-id="6c70a-195">只支持标准序列化架构命名空间中的可选属性。</span><span class="sxs-lookup"><span data-stu-id="6c70a-195">Only optional attributes from the Standard Serialization Schema namespace are supported.</span></span> <span data-ttu-id="6c70a-196">这些属性不映射到数据协定编程模型中的数据成员。</span><span class="sxs-lookup"><span data-stu-id="6c70a-196">They do not map to data members in the data contract programming model.</span></span> <span data-ttu-id="6c70a-197">当前，仅有一个这样的属性有意义，将在“ISerializable”一节讨论。</span><span class="sxs-lookup"><span data-stu-id="6c70a-197">Currently, only one such attribute has meaning and is discussed in the ISerializable section.</span></span> <span data-ttu-id="6c70a-198">将忽略所有其他成员。</span><span class="sxs-lookup"><span data-stu-id="6c70a-198">All others are ignored.</span></span>|  
|`attributeGroup`|<span data-ttu-id="6c70a-199">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-199">Forbidden.</span></span> <span data-ttu-id="6c70a-200">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] v1 版本中， `DataContractSerializer` 将忽略 `attributeGroup` 内是否存在 `xs:complexType`。</span><span class="sxs-lookup"><span data-stu-id="6c70a-200">In the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] v1 release, `DataContractSerializer` ignores the presence of `attributeGroup` inside `xs:complexType`.</span></span>|  
|`anyAttribute`|<span data-ttu-id="6c70a-201">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-201">Forbidden.</span></span>|  
|<span data-ttu-id="6c70a-202">（空）</span><span class="sxs-lookup"><span data-stu-id="6c70a-202">(empty)</span></span>|<span data-ttu-id="6c70a-203">映射到没有数据成员的数据协定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-203">Maps to a data contract with no data members.</span></span>|  
  
### <a name="xssequence-in-a-complex-type-attributes"></a><span data-ttu-id="6c70a-204">\<xs:sequence > 复杂类型中： 属性</span><span class="sxs-lookup"><span data-stu-id="6c70a-204">\<xs:sequence> in a complex type: attributes</span></span>  
  
|<span data-ttu-id="6c70a-205">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-205">Attribute</span></span>|<span data-ttu-id="6c70a-206">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-206">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="6c70a-207">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-207">Ignored.</span></span>|  
|`maxOccurs`|<span data-ttu-id="6c70a-208">必须是 1（默认值）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-208">Must be 1 (default).</span></span>|  
|`minOccurs`|<span data-ttu-id="6c70a-209">必须是 1（默认值）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-209">Must be 1 (default).</span></span>|  
  
### <a name="xssequence-in-a-complex-type-contents"></a><span data-ttu-id="6c70a-210">\<xs:sequence > 复杂类型中： 内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-210">\<xs:sequence> in a complex type: contents</span></span>  
  
|<span data-ttu-id="6c70a-211">内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-211">Contents</span></span>|<span data-ttu-id="6c70a-212">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-212">Schema</span></span>|  
|--------------|------------|  
|`element`|<span data-ttu-id="6c70a-213">每个实例都映射到一个数据成员。</span><span class="sxs-lookup"><span data-stu-id="6c70a-213">Each instance maps to a data member.</span></span>|  
|`group`|<span data-ttu-id="6c70a-214">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-214">Forbidden.</span></span>|  
|`choice`|<span data-ttu-id="6c70a-215">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-215">Forbidden.</span></span>|  
|`sequence`|<span data-ttu-id="6c70a-216">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-216">Forbidden.</span></span>|  
|`any`|<span data-ttu-id="6c70a-217">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-217">Forbidden.</span></span>|  
|<span data-ttu-id="6c70a-218">（空）</span><span class="sxs-lookup"><span data-stu-id="6c70a-218">(empty)</span></span>|<span data-ttu-id="6c70a-219">映射到没有数据成员的数据协定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-219">Maps to a data contract with no data members.</span></span>|  
  
## <a name="elements--xselement"></a><span data-ttu-id="6c70a-220">元素 – \<xs:element ></span><span class="sxs-lookup"><span data-stu-id="6c70a-220">Elements – \<xs:element></span></span>  
  
### <a name="general-information"></a><span data-ttu-id="6c70a-221">常规信息</span><span class="sxs-lookup"><span data-stu-id="6c70a-221">General Information</span></span>  
 <span data-ttu-id="6c70a-222">`<xs:element>` 会在以下上下文中发生：</span><span class="sxs-lookup"><span data-stu-id="6c70a-222">`<xs:element>` can occur in the following contexts:</span></span>  
  
-   <span data-ttu-id="6c70a-223">在描述常规（非集合）数据协定的数据成员的 `<xs:sequence>`内发生。</span><span class="sxs-lookup"><span data-stu-id="6c70a-223">It can occur within an `<xs:sequence>`, which describes a data member of a regular (non-collection) data contract.</span></span> <span data-ttu-id="6c70a-224">在这种情况下， `maxOccurs` 属性必须为 1。</span><span class="sxs-lookup"><span data-stu-id="6c70a-224">In this case, the `maxOccurs` attribute must be 1.</span></span> <span data-ttu-id="6c70a-225">（不允许值为 0。）</span><span class="sxs-lookup"><span data-stu-id="6c70a-225">(A value of 0 is not allowed).</span></span>  
  
-   <span data-ttu-id="6c70a-226">在描述集合数据协定的数据成员的 `<xs:sequence>`内发生。</span><span class="sxs-lookup"><span data-stu-id="6c70a-226">It can occur within an `<xs:sequence>`, which describes a data member of a collection data contract.</span></span> <span data-ttu-id="6c70a-227">在这种情况下， `maxOccurs` 属性必须大于 1 或为“unbounded”。</span><span class="sxs-lookup"><span data-stu-id="6c70a-227">In this case, the `maxOccurs` attribute must be greater than 1 or "unbounded".</span></span>  
  
-   <span data-ttu-id="6c70a-228">在作为全局元素声明 (GED) 的 `<xs:schema>` 内发生。</span><span class="sxs-lookup"><span data-stu-id="6c70a-228">It can occur within an `<xs:schema>` as a Global Element Declaration (GED).</span></span>  
  
### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a><span data-ttu-id="6c70a-229">\<xs:element > maxOccurs = 1 内的\<xs:sequence > （数据成员）</span><span class="sxs-lookup"><span data-stu-id="6c70a-229">\<xs:element> with maxOccurs=1 within an \<xs:sequence> (Data Members)</span></span>  
  
|<span data-ttu-id="6c70a-230">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-230">Attribute</span></span>|<span data-ttu-id="6c70a-231">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-231">Schema</span></span>|  
|---------------|------------|  
|`ref`|<span data-ttu-id="6c70a-232">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-232">Forbidden.</span></span>|  
|`name`|<span data-ttu-id="6c70a-233">支持，映射到数据成员名称。</span><span class="sxs-lookup"><span data-stu-id="6c70a-233">Supported, maps to the data member name.</span></span>|  
|`type`|<span data-ttu-id="6c70a-234">支持，映射到数据成员类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-234">Supported, maps to the data member type.</span></span> <span data-ttu-id="6c70a-235">有关更多信息，请参见“类型/基元映射”。</span><span class="sxs-lookup"><span data-stu-id="6c70a-235">For more information, see Type/primitive mapping.</span></span> <span data-ttu-id="6c70a-236">如果未指定（并且元素不包含匿名类型），则假定 `xs:anyType` 。</span><span class="sxs-lookup"><span data-stu-id="6c70a-236">If not specified (and the element does not contain an anonymous type), `xs:anyType` is assumed.</span></span>|  
|`block`|<span data-ttu-id="6c70a-237">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-237">Ignored.</span></span>|  
|`default`|<span data-ttu-id="6c70a-238">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-238">Forbidden.</span></span>|  
|`fixed`|<span data-ttu-id="6c70a-239">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-239">Forbidden.</span></span>|  
|`form`|<span data-ttu-id="6c70a-240">必须进行限定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-240">Must be qualified.</span></span> <span data-ttu-id="6c70a-241">可以通过 `elementFormDefault` 上的 `xs:schema`来设置此特性。</span><span class="sxs-lookup"><span data-stu-id="6c70a-241">This attribute can be set through `elementFormDefault` on `xs:schema`.</span></span>|  
|`id`|<span data-ttu-id="6c70a-242">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-242">Ignored.</span></span>|  
|`maxOccurs`|<span data-ttu-id="6c70a-243">1</span><span class="sxs-lookup"><span data-stu-id="6c70a-243">1</span></span>|  
|`minOccurs`|<span data-ttu-id="6c70a-244">映射到数据成员的 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> 属性（当`IsRequired` 为 1 时， `minOccurs` 为 true）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-244">Maps to the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of a data member (`IsRequired` is true when `minOccurs` is 1).</span></span>|  
|`nillable`|<span data-ttu-id="6c70a-245">影响类型映射。</span><span class="sxs-lookup"><span data-stu-id="6c70a-245">Affects type mapping.</span></span> <span data-ttu-id="6c70a-246">请参见“类型/基元映射”。</span><span class="sxs-lookup"><span data-stu-id="6c70a-246">See Type/primitive mapping.</span></span>|  
  
### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a><span data-ttu-id="6c70a-247">\<xs:element > maxoccurs > 中的 1 \<xs:sequence > （集合）</span><span class="sxs-lookup"><span data-stu-id="6c70a-247">\<xs:element> with maxOccurs>1 within an \<xs:sequence> (Collections)</span></span>  
  
-   <span data-ttu-id="6c70a-248">映射到 <xref:System.Runtime.Serialization.CollectionDataContractAttribute>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-248">Maps to a <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span></span>  
  
-   <span data-ttu-id="6c70a-249">在集合类型中，在 xs:sequence 内只允许一个 xs:element。</span><span class="sxs-lookup"><span data-stu-id="6c70a-249">In collection types, only one xs:element is allowed within an xs:sequence.</span></span>  
  
 <span data-ttu-id="6c70a-250">集合可以是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="6c70a-250">Collections can be of the following types:</span></span>  
  
-   <span data-ttu-id="6c70a-251">常规集合（例如，数组）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-251">Regular collections (for example, arrays).</span></span>  
  
-   <span data-ttu-id="6c70a-252">字典集合（将一个值映射到另一个值，例如 <xref:System.Collections.Hashtable>）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-252">Dictionary collections (mapping one value to another; for example, a <xref:System.Collections.Hashtable>).</span></span>  
  
-   <span data-ttu-id="6c70a-253">字典和密钥/值对类型的数组之间仅有的差别在于生成的编程模型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-253">The only difference between a dictionary and an array of a key/value pair type is in the generated programming model.</span></span> <span data-ttu-id="6c70a-254">有一种架构批注机制可用来指示给定的类型是一个字典集合。</span><span class="sxs-lookup"><span data-stu-id="6c70a-254">There is a schema annotation mechanism that can be used to indicate that a given type is a dictionary collection.</span></span>  
  
 <span data-ttu-id="6c70a-255">`ref`、 `block`、 `default`、 `fixed`, `form`和 `id` 属性的规则与非集合情况下的规则相同。</span><span class="sxs-lookup"><span data-stu-id="6c70a-255">The rules for the `ref`, `block`, `default`, `fixed`, `form`, and `id` attributes are the same as for the non-collection case.</span></span> <span data-ttu-id="6c70a-256">其他属性包含下表中的规则。</span><span class="sxs-lookup"><span data-stu-id="6c70a-256">Other attributes include those in the following table.</span></span>  
  
|<span data-ttu-id="6c70a-257">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-257">Attribute</span></span>|<span data-ttu-id="6c70a-258">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-258">Schema</span></span>|  
|---------------|------------|  
|`name`|<span data-ttu-id="6c70a-259">支持，映射到 <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> 属性 (Attribute) 中的 `CollectionDataContractAttribute` 属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="6c70a-259">Supported, maps to the <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> property in the `CollectionDataContractAttribute` attribute.</span></span>|  
|`type`|<span data-ttu-id="6c70a-260">支持，映射到集合中存储的类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-260">Supported, maps to the type stored in the collection.</span></span>|  
|`maxOccurs`|<span data-ttu-id="6c70a-261">大于 1 或为“unbounded”。</span><span class="sxs-lookup"><span data-stu-id="6c70a-261">Greater than 1 or "unbounded".</span></span> <span data-ttu-id="6c70a-262">DC 架构应使用“unbounded”。</span><span class="sxs-lookup"><span data-stu-id="6c70a-262">The DC schema should use "unbounded".</span></span>|  
|`minOccurs`|<span data-ttu-id="6c70a-263">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-263">Ignored.</span></span>|  
|`nillable`|<span data-ttu-id="6c70a-264">影响类型映射。</span><span class="sxs-lookup"><span data-stu-id="6c70a-264">Affects type mapping.</span></span> <span data-ttu-id="6c70a-265">对于字典集合，忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="6c70a-265">This attribute is ignored for dictionary collections.</span></span>|  
  
### <a name="xselement-within-an-xsschema-global-element-declaration"></a><span data-ttu-id="6c70a-266">\<xs:element > 内\<xs:schema > 全局元素声明</span><span class="sxs-lookup"><span data-stu-id="6c70a-266">\<xs:element> within an \<xs:schema> Global Element Declaration</span></span>  
  
-   <span data-ttu-id="6c70a-267">在架构中的某个类型时具有相同的名称和命名空间的全局元素声明 (GED) 或在其内部指定匿名类型的全局元素声明 (GED) 可认为是与该类型相关联。</span><span class="sxs-lookup"><span data-stu-id="6c70a-267">A Global Element Declaration (GED) that has the same name and namespace as a type in schema, or that defines an anonymous type inside itself, is said to be associated with the type.</span></span>  
  
-   <span data-ttu-id="6c70a-268">架构导出：将为每个生成的（简单的和复杂的）类型生成相关联的 GED。</span><span class="sxs-lookup"><span data-stu-id="6c70a-268">Schema export: associated GEDs are generated for every generated type, both simple and complex.</span></span>  
  
-   <span data-ttu-id="6c70a-269">反序列化/序列化：将关联的 GED 用作类型的根元素。</span><span class="sxs-lookup"><span data-stu-id="6c70a-269">Deserialization/serialization: associated GEDs are used as root elements for the type.</span></span>  
  
-   <span data-ttu-id="6c70a-270">架构导入：当关联的 GED 遵循以下规则时，将不是必需的并可忽略（除非它们定义了类型）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-270">Schema import: associated GEDs are not required and are ignored if they follow the following rules (unless they define types).</span></span>  
  
|<span data-ttu-id="6c70a-271">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-271">Attribute</span></span>|<span data-ttu-id="6c70a-272">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-272">Schema</span></span>|  
|---------------|------------|  
|`abstract`|<span data-ttu-id="6c70a-273">对于关联的 GED 必须是 false。</span><span class="sxs-lookup"><span data-stu-id="6c70a-273">Must be false for associated GEDs.</span></span>|  
|`block`|<span data-ttu-id="6c70a-274">在关联的 GED 中禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-274">Forbidden in associated GEDs.</span></span>|  
|`default`|<span data-ttu-id="6c70a-275">在关联的 GED 中禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-275">Forbidden in associated GEDs.</span></span>|  
|`final`|<span data-ttu-id="6c70a-276">对于关联的 GED 必须是 false。</span><span class="sxs-lookup"><span data-stu-id="6c70a-276">Must be false for associated GEDs.</span></span>|  
|`fixed`|<span data-ttu-id="6c70a-277">在关联的 GED 中禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-277">Forbidden in associated GEDs.</span></span>|  
|`id`|<span data-ttu-id="6c70a-278">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-278">Ignored.</span></span>|  
|`name`|<span data-ttu-id="6c70a-279">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-279">Supported.</span></span> <span data-ttu-id="6c70a-280">请参见关联的 GED 的定义。</span><span class="sxs-lookup"><span data-stu-id="6c70a-280">See the definition of associated GEDs.</span></span>|  
|`nillable`|<span data-ttu-id="6c70a-281">对于关联的 GED 必须是 true。</span><span class="sxs-lookup"><span data-stu-id="6c70a-281">Must be true for associated GEDs.</span></span>|  
|`substitutionGroup`|<span data-ttu-id="6c70a-282">在关联的 GED 中禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-282">Forbidden in associated GEDs.</span></span>|  
|`type`|<span data-ttu-id="6c70a-283">支持，必须与关联的 GED 的关联类型相匹配（除非该元素包含一个匿名类型）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-283">Supported, and must match the associated type for associated GEDs (unless the element contains an anonymous type).</span></span>|  
  
### <a name="xselement-contents"></a><span data-ttu-id="6c70a-284">\<xs:element >： 内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-284">\<xs:element>: contents</span></span>  
  
|<span data-ttu-id="6c70a-285">内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-285">Contents</span></span>|<span data-ttu-id="6c70a-286">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-286">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="6c70a-287">支持。*</span><span class="sxs-lookup"><span data-stu-id="6c70a-287">Supported.*</span></span>|  
|`complexType`|<span data-ttu-id="6c70a-288">支持。*</span><span class="sxs-lookup"><span data-stu-id="6c70a-288">Supported.*</span></span>|  
|`unique`|<span data-ttu-id="6c70a-289">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-289">Ignored.</span></span>|  
|`key`|<span data-ttu-id="6c70a-290">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-290">Ignored.</span></span>|  
|`keyref`|<span data-ttu-id="6c70a-291">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-291">Ignored.</span></span>|  
|<span data-ttu-id="6c70a-292">(空白)</span><span class="sxs-lookup"><span data-stu-id="6c70a-292">(blank)</span></span>|<span data-ttu-id="6c70a-293">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-293">Supported.</span></span>|  
  
 <span data-ttu-id="6c70a-294">\*使用时`simpleType`和`complexType,`匿名类型的映射是与非匿名类型相同，只不过没有匿名数据协定，因此创建命名的数据协定，使用派生自元素名称的生成名称。</span><span class="sxs-lookup"><span data-stu-id="6c70a-294">\* When using the `simpleType` and `complexType,` mapping for anonymous types is the same as for non-anonymous types, except that there is no anonymous data contracts, and so a named data contract is created, with a generated name derived from the element name.</span></span> <span data-ttu-id="6c70a-295">下面的列表中是匿名类型的规则：</span><span class="sxs-lookup"><span data-stu-id="6c70a-295">The rules for anonymous types are in the following list:</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="6c70a-296"> 实现详细信息：如果 `xs:element` 名称不包含句点，则匿名类型映射到外部数据协定类型的内部类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-296"> implementation detail: If the `xs:element` name does not contain periods, the anonymous type maps to an inner type of the outer data contract type.</span></span> <span data-ttu-id="6c70a-297">如果名称包含句点，则结果数据协定类型是独立的（不是内部类型）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-297">If the name contains periods, the resulting data contract type is independent (not an inner type).</span></span>  
  
-   <span data-ttu-id="6c70a-298">内部类型的生成数据协定名称是由外部类型的数据协定名称后跟一个句点、元素名称和字符串“Type”构成。</span><span class="sxs-lookup"><span data-stu-id="6c70a-298">The generated data contract name of the inner type is the data contract name of the outer type followed by a period, the name of the element, and the string "Type".</span></span>  
  
-   <span data-ttu-id="6c70a-299">如果已存在具有这个名称的数据协定，则通过在该名称后追加“1”、“2”、“3”等以使名称具有唯一性，从而创建一个唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="6c70a-299">If a data contract with such a name already exists, the name is made unique by appending "1", "2", "3", and so on until a unique name is created.</span></span>  
  
## <a name="simple-types---xssimpletype"></a><span data-ttu-id="6c70a-300">简单类型- \<xs:simpleType ></span><span class="sxs-lookup"><span data-stu-id="6c70a-300">Simple Types - \<xs:simpleType></span></span>  
  
### <a name="xssimpletype-attributes"></a><span data-ttu-id="6c70a-301">\<xs:simpleType >： 属性</span><span class="sxs-lookup"><span data-stu-id="6c70a-301">\<xs:simpleType>: attributes</span></span>  
  
|<span data-ttu-id="6c70a-302">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-302">Attribute</span></span>|<span data-ttu-id="6c70a-303">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-303">Schema</span></span>|  
|---------------|------------|  
|`final`|<span data-ttu-id="6c70a-304">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-304">Ignored.</span></span>|  
|`id`|<span data-ttu-id="6c70a-305">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-305">Ignored.</span></span>|  
|`name`|<span data-ttu-id="6c70a-306">支持，映射到数据协定名称。</span><span class="sxs-lookup"><span data-stu-id="6c70a-306">Supported, maps to the data contract name.</span></span>|  
  
### <a name="xssimpletype-contents"></a><span data-ttu-id="6c70a-307">\<xs:simpleType >： 内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-307">\<xs:simpleType>: contents</span></span>  
  
|<span data-ttu-id="6c70a-308">内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-308">Contents</span></span>|<span data-ttu-id="6c70a-309">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-309">Schema</span></span>|  
|--------------|------------|  
|`restriction`|<span data-ttu-id="6c70a-310">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-310">Supported.</span></span> <span data-ttu-id="6c70a-311">映射到枚举数据协定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-311">Maps to enumeration data contracts.</span></span> <span data-ttu-id="6c70a-312">如果与枚举模式不匹配，则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="6c70a-312">This attribute is ignored if it does not match the enumeration pattern.</span></span> <span data-ttu-id="6c70a-313">请参见“ `xs:simpleType` 限制”一节。</span><span class="sxs-lookup"><span data-stu-id="6c70a-313">See the `xs:simpleType` restrictions section.</span></span>|  
|`list`|<span data-ttu-id="6c70a-314">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-314">Supported.</span></span> <span data-ttu-id="6c70a-315">映射到标志枚举数据协定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-315">Maps to flag enumeration data contracts.</span></span> <span data-ttu-id="6c70a-316">请参见“ `xs:simpleType` 列表”一节。</span><span class="sxs-lookup"><span data-stu-id="6c70a-316">See the `xs:simpleType` lists section.</span></span>|  
|`union`|<span data-ttu-id="6c70a-317">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-317">Forbidden.</span></span>|  
  
### <a name="xsrestriction"></a><span data-ttu-id="6c70a-318">\<xs: restriction ></span><span class="sxs-lookup"><span data-stu-id="6c70a-318">\<xs:restriction></span></span>  
  
-   <span data-ttu-id="6c70a-319">仅 base="`xs:anyType`" 支持复杂类型限制。</span><span class="sxs-lookup"><span data-stu-id="6c70a-319">Complex type restrictions are supported only for base="`xs:anyType`".</span></span>  
  
-   <span data-ttu-id="6c70a-320">除 `xs:string` 之外没有任何限制方面的 `xs:enumeration` 的简单类型限制映射到枚举数据协定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-320">Simple type restrictions of `xs:string` that do not have any restriction facets other than `xs:enumeration` are mapped to enumeration data contracts.</span></span>  
  
-   <span data-ttu-id="6c70a-321">将所有其他简单类型限制映射到它们限制的类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-321">All other simple type restrictions are mapped to the types they restrict.</span></span> <span data-ttu-id="6c70a-322">例如， `xs:int` 的限制将映射到一个整数，就像 `xs:int` 自身一样。</span><span class="sxs-lookup"><span data-stu-id="6c70a-322">For example, a restriction of `xs:int` maps to an integer, just as `xs:int` itself does.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="6c70a-323"> 基元类型映射，请参见“类型/基元映射”。</span><span class="sxs-lookup"><span data-stu-id="6c70a-323"> primitive type mapping, see Type/primitive mapping.</span></span>  
  
### <a name="xsrestriction-attributes"></a><span data-ttu-id="6c70a-324">\<xs: restriction >： 属性</span><span class="sxs-lookup"><span data-stu-id="6c70a-324">\<xs:restriction>: attributes</span></span>  
  
|<span data-ttu-id="6c70a-325">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-325">Attribute</span></span>|<span data-ttu-id="6c70a-326">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-326">Schema</span></span>|  
|---------------|------------|  
|`base`|<span data-ttu-id="6c70a-327">必须是一个支持的简单类型或 `xs:anyType`。</span><span class="sxs-lookup"><span data-stu-id="6c70a-327">Must be a supported simple type or `xs:anyType`.</span></span>|  
|`id`|<span data-ttu-id="6c70a-328">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-328">Ignored.</span></span>|  
  
### <a name="xsrestriction-for-all-other-cases-contents"></a><span data-ttu-id="6c70a-329">\<xs: restriction > 对于所有其他情况： 内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-329">\<xs:restriction> for all other cases: contents</span></span>  
  
|<span data-ttu-id="6c70a-330">内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-330">Contents</span></span>|<span data-ttu-id="6c70a-331">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-331">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="6c70a-332">如果存在，必须派生自支持的基元类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-332">If present, must be derived from a supported primitive type.</span></span>|  
|`minExclusive`|<span data-ttu-id="6c70a-333">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-333">Ignored.</span></span>|  
|`minInclusive`|<span data-ttu-id="6c70a-334">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-334">Ignored.</span></span>|  
|`maxExclusive`|<span data-ttu-id="6c70a-335">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-335">Ignored.</span></span>|  
|`maxInclusive`|<span data-ttu-id="6c70a-336">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-336">Ignored.</span></span>|  
|`totalDigits`|<span data-ttu-id="6c70a-337">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-337">Ignored.</span></span>|  
|`fractionDigits`|<span data-ttu-id="6c70a-338">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-338">Ignored.</span></span>|  
|`length`|<span data-ttu-id="6c70a-339">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-339">Ignored.</span></span>|  
|`minLength`|<span data-ttu-id="6c70a-340">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-340">Ignored.</span></span>|  
|`maxLength`|<span data-ttu-id="6c70a-341">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-341">Ignored.</span></span>|  
|`enumeration`|<span data-ttu-id="6c70a-342">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-342">Ignored.</span></span>|  
|`whiteSpace`|<span data-ttu-id="6c70a-343">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-343">Ignored.</span></span>|  
|`pattern`|<span data-ttu-id="6c70a-344">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-344">Ignored.</span></span>|  
|<span data-ttu-id="6c70a-345">(空白)</span><span class="sxs-lookup"><span data-stu-id="6c70a-345">(blank)</span></span>|<span data-ttu-id="6c70a-346">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-346">Supported.</span></span>|  
  
## <a name="enumeration"></a><span data-ttu-id="6c70a-347">枚举</span><span class="sxs-lookup"><span data-stu-id="6c70a-347">Enumeration</span></span>  
  
### <a name="xsrestriction-for-enumerations-attributes"></a><span data-ttu-id="6c70a-348">\<xs: restriction > 枚举： 属性</span><span class="sxs-lookup"><span data-stu-id="6c70a-348">\<xs:restriction> for enumerations: attributes</span></span>  
  
|<span data-ttu-id="6c70a-349">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-349">Attribute</span></span>|<span data-ttu-id="6c70a-350">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-350">Schema</span></span>|  
|---------------|------------|  
|`base`|<span data-ttu-id="6c70a-351">如果存在，必须是 `xs:string`。</span><span class="sxs-lookup"><span data-stu-id="6c70a-351">If present, must be `xs:string`.</span></span>|  
|`id`|<span data-ttu-id="6c70a-352">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-352">Ignored.</span></span>|  
  
### <a name="xsrestriction-for-enumerations-contents"></a><span data-ttu-id="6c70a-353">\<xs: restriction > 枚举： 内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-353">\<xs:restriction> for enumerations: contents</span></span>  
  
|<span data-ttu-id="6c70a-354">内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-354">Contents</span></span>|<span data-ttu-id="6c70a-355">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-355">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="6c70a-356">如果存在，必须是数据协定支持的枚举限制（本节）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-356">If present, must be an enumeration restriction supported by the data contract (this section).</span></span>|  
|`minExclusive`|<span data-ttu-id="6c70a-357">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-357">Ignored.</span></span>|  
|`minInclusive`|<span data-ttu-id="6c70a-358">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-358">Ignored.</span></span>|  
|`maxExclusive`|<span data-ttu-id="6c70a-359">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-359">Ignored.</span></span>|  
|`maxInclusive`|<span data-ttu-id="6c70a-360">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-360">Ignored.</span></span>|  
|`totalDigits`|<span data-ttu-id="6c70a-361">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-361">Ignored.</span></span>|  
|`fractionDigits`|<span data-ttu-id="6c70a-362">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-362">Ignored.</span></span>|  
|`length`|<span data-ttu-id="6c70a-363">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-363">Forbidden.</span></span>|  
|`minLength`|<span data-ttu-id="6c70a-364">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-364">Forbidden.</span></span>|  
|`maxLength`|<span data-ttu-id="6c70a-365">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-365">Forbidden.</span></span>|  
|`enumeration`|<span data-ttu-id="6c70a-366">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-366">Supported.</span></span> <span data-ttu-id="6c70a-367">忽略枚举“id”，并且“值”映射到枚举数据协定上的值名称。</span><span class="sxs-lookup"><span data-stu-id="6c70a-367">Enumeration "id" is ignored, and "value" maps to the value name in the enumeration data contract.</span></span>|  
|`whiteSpace`|<span data-ttu-id="6c70a-368">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-368">Forbidden.</span></span>|  
|`pattern`|<span data-ttu-id="6c70a-369">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-369">Forbidden.</span></span>|  
|<span data-ttu-id="6c70a-370">（空）</span><span class="sxs-lookup"><span data-stu-id="6c70a-370">(empty)</span></span>|<span data-ttu-id="6c70a-371">支持，映射到空枚举类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-371">Supported, maps to empty enumeration type.</span></span>|  
  
 <span data-ttu-id="6c70a-372">下面的代码演示 C# 枚举类。</span><span class="sxs-lookup"><span data-stu-id="6c70a-372">The following code shows a C# enumeration class.</span></span>  
  
```  
public enum MyEnum  
{  
   first = 3,  
   second = 4,  
   third =5  
```  
  
 <span data-ttu-id="6c70a-373">}</span><span class="sxs-lookup"><span data-stu-id="6c70a-373">}</span></span>  
  
 <span data-ttu-id="6c70a-374">此类通过 `DataContractSerializer`映射到下面的架构。</span><span class="sxs-lookup"><span data-stu-id="6c70a-374">This class maps to the following schema by the `DataContractSerializer`.</span></span> <span data-ttu-id="6c70a-375">如果枚举值从 1 开始，则不生成 `xs:annotation` 块。</span><span class="sxs-lookup"><span data-stu-id="6c70a-375">If enumeration values start from 1, `xs:annotation` blocks are not generated.</span></span>  
  
```xml  
<xs:simpleType name="MyEnum">  
<xs:restriction base="xs:string">  
 <xs:enumeration value="first">  
  <xs:annotation>  
   <xs:appinfo>  
    <EnumerationValue   
     xmlns="http://schemas.microsoft.com/2003/10/Serialization/">  
     3  
    </EnumerationValue>  
   </xs:appinfo>  
  </xs:annotation>  
 </xs:enumeration>  
 <xs:enumeration value="second">  
  <xs:annotation>  
   <xs:appinfo>  
    <EnumerationValue   
     xmlns="http://schemas.microsoft.com/2003/10/Serialization/">  
     4  
    </EnumerationValue>  
   </xs:appinfo>  
  </xs:annotation>  
 </xs:enumeration>  
</xs:restriction>  
</xs:simpleType>  
```  
  
### <a name="xslist"></a><span data-ttu-id="6c70a-376">\<xs:list ></span><span class="sxs-lookup"><span data-stu-id="6c70a-376">\<xs:list></span></span>  
 <span data-ttu-id="6c70a-377">`DataContractSerializer` 将用 `System.FlagsAttribute` 标记的枚举类型映射到从 `xs:list` 派生的 `xs:string`。</span><span class="sxs-lookup"><span data-stu-id="6c70a-377">`DataContractSerializer` maps enumeration types marked with `System.FlagsAttribute` to `xs:list` derived from `xs:string`.</span></span> <span data-ttu-id="6c70a-378">不支持其他 `xs:list` 变体。</span><span class="sxs-lookup"><span data-stu-id="6c70a-378">No other `xs:list` variations are supported.</span></span>  
  
### <a name="xslist-attributes"></a><span data-ttu-id="6c70a-379">\<xs:list >： 属性</span><span class="sxs-lookup"><span data-stu-id="6c70a-379">\<xs:list>: attributes</span></span>  
  
|<span data-ttu-id="6c70a-380">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-380">Attribute</span></span>|<span data-ttu-id="6c70a-381">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-381">Schema</span></span>|  
|---------------|------------|  
|`itemType`|<span data-ttu-id="6c70a-382">已禁止。</span><span class="sxs-lookup"><span data-stu-id="6c70a-382">Forbidden.</span></span>|  
|`id`|<span data-ttu-id="6c70a-383">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-383">Ignored.</span></span>|  
  
### <a name="xslist-contents"></a><span data-ttu-id="6c70a-384">\<xs:list >： 内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-384">\<xs:list>: contents</span></span>  
  
|<span data-ttu-id="6c70a-385">内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-385">Contents</span></span>|<span data-ttu-id="6c70a-386">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-386">Schema</span></span>|  
|--------------|------------|  
|`simpleType`|<span data-ttu-id="6c70a-387">必须是来自使用 `xs:string` 方面的 `xs:enumeration` 的限制。</span><span class="sxs-lookup"><span data-stu-id="6c70a-387">Must be restriction from `xs:string` using `xs:enumeration` facet.</span></span>|  
  
 <span data-ttu-id="6c70a-388">如果枚举值后面没有 2 的幂级数（标志的默认值），则在 `xs:annotation/xs:appInfo/ser:EnumerationValue` 元素中存储值。</span><span class="sxs-lookup"><span data-stu-id="6c70a-388">If enumeration value does not follow a power of 2 progression (default for Flags), the value is stored in the `xs:annotation/xs:appInfo/ser:EnumerationValue` element.</span></span>  
  
 <span data-ttu-id="6c70a-389">例如，下面的代码标志一个枚举类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-389">For example, the following code flags an enumeration type.</span></span>  
  
```  
[Flags]  
public enum AuthFlags  
{    
  AuthAnonymous = 1,  
  AuthBasic = 2,  
  AuthNTLM = 4,  
  AuthMD5 = 16,  
  AuthWindowsLiveID = 64,  
}  
```  
  
 <span data-ttu-id="6c70a-390">此类型映射到下面的架构。</span><span class="sxs-lookup"><span data-stu-id="6c70a-390">This type maps to the following schema.</span></span>  
  
```xml  
<xs:simpleType name="AuthFlags">  
    <xs:list>  
      <xs:simpleType>  
        <xs:restriction base="xs:string">  
          <xs:enumeration value="AuthAnonymous" />  
          <xs:enumeration value="AuthBasic" />  
          <xs:enumeration value="AuthNTLM" />  
          <xs:enumeration value="AuthMD5">  
            <xs:annotation>  
              <xs:appinfo>  
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Se  
rialization/">16</EnumerationValue>  
              </xs:appinfo>  
            </xs:annotation>  
          </xs:enumeration>  
          <xs:enumeration value="AuthWindowsLiveID">  
            <xs:annotation>  
              <xs:appinfo>  
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Se  
rialization/">64</EnumerationValue>  
              </xs:appinfo>  
            </xs:annotation>  
          </xs:enumeration>  
        </xs:restriction>  
      </xs:simpleType>  
    </xs:list>  
  </xs:simpleType>  
```  
  
## <a name="inheritance"></a><span data-ttu-id="6c70a-391">继承</span><span class="sxs-lookup"><span data-stu-id="6c70a-391">Inheritance</span></span>  
  
### <a name="general-rules"></a><span data-ttu-id="6c70a-392">一般规则</span><span class="sxs-lookup"><span data-stu-id="6c70a-392">General rules</span></span>  
 <span data-ttu-id="6c70a-393">数据协定可以继承自另一个数据协定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-393">A data contract can inherit from another data contract.</span></span> <span data-ttu-id="6c70a-394">这类数据协定映射到一个基协定，并由扩展类型使用 `<xs:extension>` XML 架构协定进行派生。</span><span class="sxs-lookup"><span data-stu-id="6c70a-394">Such data contracts map to a base and are derived by extension types using the `<xs:extension>` XML Schema construct.</span></span>  
  
 <span data-ttu-id="6c70a-395">数据协定不能继承自集合数据协定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-395">A data contract cannot inherit from a collection data contract.</span></span>  
  
 <span data-ttu-id="6c70a-396">例如，下面的代码是数据协定。</span><span class="sxs-lookup"><span data-stu-id="6c70a-396">For example, the following code is a data contract.</span></span>  
  
```  
[DataContract]  
public class Person  
{  
  [DataMember]  
  public string Name;  
}  
[DataContract]  
public class Employee : Person   
{      
  [DataMember]  
  public int ID;  
}  
```  
  
 <span data-ttu-id="6c70a-397">此数据协定映射到下面的 XML 架构类型声明。</span><span class="sxs-lookup"><span data-stu-id="6c70a-397">This data contract maps to the following XML Schema type declaration.</span></span>  
  
```xml  
<xs:complexType name="Employee">  
 <xs:complexContent mixed="false">  
  <xs:extension base="tns:Person">  
   <xs:sequence>  
    <xs:element minOccurs="0" name="ID" type="xs:int"/>  
   </xs:sequence>  
  </xs:extension>  
 </xs:complexContent>  
</xs:complexType>  
<xs:complexType name="Person">  
 <xs:sequence>  
  <xs:element minOccurs="0" name="Name"   
    nillable="true" type="xs:string"/>  
 </xs:sequence>  
</xs:complexType>  
```  
  
### <a name="xscomplexcontent-attributes"></a><span data-ttu-id="6c70a-398">\<xs:complexContent >： 属性</span><span class="sxs-lookup"><span data-stu-id="6c70a-398">\<xs:complexContent>: attributes</span></span>  
  
|<span data-ttu-id="6c70a-399">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-399">Attribute</span></span>|<span data-ttu-id="6c70a-400">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-400">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="6c70a-401">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-401">Ignored.</span></span>|  
|`mixed`|<span data-ttu-id="6c70a-402">必须是 false。</span><span class="sxs-lookup"><span data-stu-id="6c70a-402">Must be false.</span></span>|  
  
### <a name="xscomplexcontent-contents"></a><span data-ttu-id="6c70a-403">\<xs:complexContent >： 内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-403">\<xs:complexContent>: contents</span></span>  
  
|<span data-ttu-id="6c70a-404">内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-404">Contents</span></span>|<span data-ttu-id="6c70a-405">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-405">Schema</span></span>|  
|--------------|------------|  
|`restriction`|<span data-ttu-id="6c70a-406">已禁止，除了 base="`xs:anyType`"。</span><span class="sxs-lookup"><span data-stu-id="6c70a-406">Forbidden, except when base="`xs:anyType`".</span></span> <span data-ttu-id="6c70a-407">后者等效于将 `xs:restriction` 的内容直接放到 `xs:complexContent`的容器下。</span><span class="sxs-lookup"><span data-stu-id="6c70a-407">The latter is equivalent to placing the content of the `xs:restriction` directly under the container of the `xs:complexContent`.</span></span>|  
|`extension`|<span data-ttu-id="6c70a-408">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-408">Supported.</span></span> <span data-ttu-id="6c70a-409">映射到数据协定继承。</span><span class="sxs-lookup"><span data-stu-id="6c70a-409">Maps to data contract inheritance.</span></span>|  
  
### <a name="xsextension-in-xscomplexcontent-attributes"></a><span data-ttu-id="6c70a-410">\<xs: extension > 中\<xs:complexContent >： 属性</span><span class="sxs-lookup"><span data-stu-id="6c70a-410">\<xs:extension> in \<xs:complexContent>: attributes</span></span>  
  
|<span data-ttu-id="6c70a-411">特性</span><span class="sxs-lookup"><span data-stu-id="6c70a-411">Attribute</span></span>|<span data-ttu-id="6c70a-412">架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-412">Schema</span></span>|  
|---------------|------------|  
|`id`|<span data-ttu-id="6c70a-413">已忽略。</span><span class="sxs-lookup"><span data-stu-id="6c70a-413">Ignored.</span></span>|  
|`base`|<span data-ttu-id="6c70a-414">支持。</span><span class="sxs-lookup"><span data-stu-id="6c70a-414">Supported.</span></span> <span data-ttu-id="6c70a-415">映射到此类型继承自的基数据协定类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-415">Maps to the base data contract type that this type inherits from.</span></span>|  
  
### <a name="xsextension-in-xscomplexcontent-contents"></a><span data-ttu-id="6c70a-416">\<xs: extension > 中\<xs:complexContent >： 内容</span><span class="sxs-lookup"><span data-stu-id="6c70a-416">\<xs:extension> in \<xs:complexContent>: contents</span></span>  
 <span data-ttu-id="6c70a-417">规则与 `<xs:complexType>` 内容的规则相同。</span><span class="sxs-lookup"><span data-stu-id="6c70a-417">The rules are the same as for `<xs:complexType>` contents.</span></span>  
  
 <span data-ttu-id="6c70a-418">如果提供 `<xs:sequence>` ，则其成员元素将映射到存在于派生的数据协定中的附加数据成员。</span><span class="sxs-lookup"><span data-stu-id="6c70a-418">If an `<xs:sequence>` is provided, its member elements map to additional data members that are present in the derived data contract.</span></span>  
  
 <span data-ttu-id="6c70a-419">如果派生的类型包含与基类型中的元素有相同名称的元素，则重复元素声明映射到一个具有生成的唯一名称的数据成员。</span><span class="sxs-lookup"><span data-stu-id="6c70a-419">If a derived type contains an element with the same name as an element in a base type, the duplicate element declaration maps to a data member with a name that is generated to be unique.</span></span> <span data-ttu-id="6c70a-420">将向数据成员名称添加正整数数字（“member1”、“member2”等）直至查找到唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="6c70a-420">Positive integer numbers are added to the data member name ("member1", "member2", and so on) until a unique name is found.</span></span> <span data-ttu-id="6c70a-421">相反：</span><span class="sxs-lookup"><span data-stu-id="6c70a-421">Conversely:</span></span>  
  
-   <span data-ttu-id="6c70a-422">如果派生的数据协定有一个数据成员与基数据协定中的数据成员具有相同的名称和类型，则 `DataContractSerializer` 在派生的类型中生成此对应的元素。</span><span class="sxs-lookup"><span data-stu-id="6c70a-422">If a derived data contract has a data member with the same name and type as a data member in a base data contract, `DataContractSerializer` generates this corresponding element in the derived type.</span></span>  
  
-   <span data-ttu-id="6c70a-423">如果派生的数据协定有一个数据成员与基数据协定中的数据成员具有相同的名称，但类型不同，则 `DataContractSerializer` 使用基类型和派生的类型声明中的 `xs:anyType` 类型的元素导入架构。</span><span class="sxs-lookup"><span data-stu-id="6c70a-423">If a derived data contract has a data member with the same name as a data member in a base data contract but a different type, the `DataContractSerializer` imports a schema with an element of the type `xs:anyType` in both base type and derived type declarations.</span></span> <span data-ttu-id="6c70a-424">在 `xs:annotations/xs:appInfo/ser:ActualType/@Name`中保留原始类型名称。</span><span class="sxs-lookup"><span data-stu-id="6c70a-424">The original type name is preserved in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span></span>  
  
 <span data-ttu-id="6c70a-425">两个变体可能会导致一个使用有歧义的内容模型的架构，此内容模型取决于各自数据成员的顺序。</span><span class="sxs-lookup"><span data-stu-id="6c70a-425">Both variations may lead to a schema with an ambiguous content model, which depends on the order of the respective data members.</span></span>  
  
## <a name="typeprimitive-mapping"></a><span data-ttu-id="6c70a-426">类型/基元映射</span><span class="sxs-lookup"><span data-stu-id="6c70a-426">Type/primitive mapping</span></span>  
 <span data-ttu-id="6c70a-427">`DataContractSerializer` 使用下面的 XML 架构基元类型映射。</span><span class="sxs-lookup"><span data-stu-id="6c70a-427">The `DataContractSerializer` uses the following mapping for XML Schema primitive types.</span></span>  
  
|<span data-ttu-id="6c70a-428">XSD 类型</span><span class="sxs-lookup"><span data-stu-id="6c70a-428">XSD type</span></span>|<span data-ttu-id="6c70a-429">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="6c70a-429">.NET type</span></span>|  
|--------------|---------------|  
|`anyType`|<span data-ttu-id="6c70a-430"><xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-430"><xref:System.Object>.</span></span>|  
|`anySimpleType`|<span data-ttu-id="6c70a-431"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-431"><xref:System.String>.</span></span>|  
|`duration`|<span data-ttu-id="6c70a-432"><xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-432"><xref:System.TimeSpan>.</span></span>|  
|`dateTime`|<span data-ttu-id="6c70a-433"><xref:System.DateTime>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-433"><xref:System.DateTime>.</span></span>|  
|`dateTimeOffset`|<span data-ttu-id="6c70a-434">表示偏移量的<xref:System.DateTime> 和 <xref:System.TimeSpan> 。</span><span class="sxs-lookup"><span data-stu-id="6c70a-434"><xref:System.DateTime> and <xref:System.TimeSpan> for the offset.</span></span> <span data-ttu-id="6c70a-435">请参见下面的“DateTimeOffset 序列化”。</span><span class="sxs-lookup"><span data-stu-id="6c70a-435">See DateTimeOffset Serialization below.</span></span>|  
|`time`|<span data-ttu-id="6c70a-436"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-436"><xref:System.String>.</span></span>|  
|`date`|<span data-ttu-id="6c70a-437"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-437"><xref:System.String>.</span></span>|  
|`gYearMonth`|<span data-ttu-id="6c70a-438"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-438"><xref:System.String>.</span></span>|  
|`gYear`|<span data-ttu-id="6c70a-439"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-439"><xref:System.String>.</span></span>|  
|`gMonthDay`|<span data-ttu-id="6c70a-440"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-440"><xref:System.String>.</span></span>|  
|`gDay`|<span data-ttu-id="6c70a-441"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-441"><xref:System.String>.</span></span>|  
|`gMonth`|<span data-ttu-id="6c70a-442"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-442"><xref:System.String>.</span></span>|  
|`boolean`|<xref:System.Boolean>|  
|`base64Binary`|<span data-ttu-id="6c70a-443"><xref:System.Byte> 数组。</span><span class="sxs-lookup"><span data-stu-id="6c70a-443"><xref:System.Byte> array.</span></span>|  
|`hexBinary`|<span data-ttu-id="6c70a-444"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-444"><xref:System.String>.</span></span>|  
|`float`|<span data-ttu-id="6c70a-445"><xref:System.Single>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-445"><xref:System.Single>.</span></span>|  
|`double`|<span data-ttu-id="6c70a-446"><xref:System.Double>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-446"><xref:System.Double>.</span></span>|  
|`anyURI`|<span data-ttu-id="6c70a-447"><xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-447"><xref:System.Uri>.</span></span>|  
|`QName`|<span data-ttu-id="6c70a-448"><xref:System.Xml.XmlQualifiedName>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-448"><xref:System.Xml.XmlQualifiedName>.</span></span>|  
|`string`|<span data-ttu-id="6c70a-449"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-449"><xref:System.String>.</span></span>|  
|`normalizedString`|<span data-ttu-id="6c70a-450"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-450"><xref:System.String>.</span></span>|  
|`token`|<span data-ttu-id="6c70a-451"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-451"><xref:System.String>.</span></span>|  
|`language`|<span data-ttu-id="6c70a-452"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-452"><xref:System.String>.</span></span>|  
|`Name`|<span data-ttu-id="6c70a-453"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-453"><xref:System.String>.</span></span>|  
|`NCName`|<span data-ttu-id="6c70a-454"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-454"><xref:System.String>.</span></span>|  
|`ID`|<span data-ttu-id="6c70a-455"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-455"><xref:System.String>.</span></span>|  
|`IDREF`|<span data-ttu-id="6c70a-456"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-456"><xref:System.String>.</span></span>|  
|`IDREFS`|<span data-ttu-id="6c70a-457"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-457"><xref:System.String>.</span></span>|  
|`ENTITY`|<span data-ttu-id="6c70a-458"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-458"><xref:System.String>.</span></span>|  
|`ENTITIES`|<span data-ttu-id="6c70a-459"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-459"><xref:System.String>.</span></span>|  
|`NMTOKEN`|<span data-ttu-id="6c70a-460"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-460"><xref:System.String>.</span></span>|  
|`NMTOKENS`|<span data-ttu-id="6c70a-461"><xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-461"><xref:System.String>.</span></span>|  
|`decimal`|<span data-ttu-id="6c70a-462"><xref:System.Decimal>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-462"><xref:System.Decimal>.</span></span>|  
|`integer`|<span data-ttu-id="6c70a-463"><xref:System.Int64>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-463"><xref:System.Int64>.</span></span>|  
|`nonPositiveInteger`|<span data-ttu-id="6c70a-464"><xref:System.Int64>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-464"><xref:System.Int64>.</span></span>|  
|`negativeInteger`|<span data-ttu-id="6c70a-465"><xref:System.Int64>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-465"><xref:System.Int64>.</span></span>|  
|`long`|<span data-ttu-id="6c70a-466"><xref:System.Int64>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-466"><xref:System.Int64>.</span></span>|  
|`int`|<span data-ttu-id="6c70a-467"><xref:System.Int32>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-467"><xref:System.Int32>.</span></span>|  
|`short`|<span data-ttu-id="6c70a-468"><xref:System.Int16>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-468"><xref:System.Int16>.</span></span>|  
|`Byte`|<span data-ttu-id="6c70a-469"><xref:System.SByte>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-469"><xref:System.SByte>.</span></span>|  
|`nonNegativeInteger`|<span data-ttu-id="6c70a-470"><xref:System.Int64>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-470"><xref:System.Int64>.</span></span>|  
|`unsignedLong`|<span data-ttu-id="6c70a-471"><xref:System.UInt64>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-471"><xref:System.UInt64>.</span></span>|  
|`unsignedInt`|<span data-ttu-id="6c70a-472"><xref:System.UInt32>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-472"><xref:System.UInt32>.</span></span>|  
|`unsignedShort`|<span data-ttu-id="6c70a-473"><xref:System.UInt16>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-473"><xref:System.UInt16>.</span></span>|  
|`unsignedByte`|<span data-ttu-id="6c70a-474"><xref:System.Byte>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-474"><xref:System.Byte>.</span></span>|  
|`positiveInteger`|<span data-ttu-id="6c70a-475"><xref:System.Int64>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-475"><xref:System.Int64>.</span></span>|  
  
## <a name="iserializable-types-mapping"></a><span data-ttu-id="6c70a-476">ISerializable 类型映射</span><span class="sxs-lookup"><span data-stu-id="6c70a-476">ISerializable types mapping</span></span>  
 <span data-ttu-id="6c70a-477">在 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 版本 1.0 中，已引入 `ISerializable` 作为一种用于序列化持久性或数据传输对象的机制。</span><span class="sxs-lookup"><span data-stu-id="6c70a-477">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.0, `ISerializable` was introduced as a general mechanism to serialize objects for persistence or data transfer.</span></span> <span data-ttu-id="6c70a-478">有许多实现 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 的 `ISerializable` 类型，这些类型可以在应用程序之间进行传递。</span><span class="sxs-lookup"><span data-stu-id="6c70a-478">There are many [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types that implement `ISerializable` and that can be passed between applications.</span></span> <span data-ttu-id="6c70a-479">`DataContractSerializer` 自然支持 `ISerializable` 类。</span><span class="sxs-lookup"><span data-stu-id="6c70a-479">`DataContractSerializer` naturally provides support for `ISerializable` classes.</span></span> <span data-ttu-id="6c70a-480">`DataContractSerializer` 映射到 `ISerializable` 实现架构类型，这些类型仅在类型的 QName（限定名）上存在不同，并且实际上是属性集合。</span><span class="sxs-lookup"><span data-stu-id="6c70a-480">The `DataContractSerializer` maps `ISerializable` implementation schema types that differ only by the QName (qualified name) of the type and are effectively property collections.</span></span> <span data-ttu-id="6c70a-481">例如， `DataContractSerializer` 将 <xref:System.Exception> 映射到下面 http://schemas.datacontract.org/2004/07/System 命名空间中的 XSD 类型。</span><span class="sxs-lookup"><span data-stu-id="6c70a-481">For example, the `DataContractSerializer` maps <xref:System.Exception> to the following XSD type in the http://schemas.datacontract.org/2004/07/System namespace.</span></span>  
  
```xml  
<xs:complexType name="Exception">  
 <xs:sequence>  
  <xs:any minOccurs="0" maxOccurs="unbounded"   
      namespace="##local" processContents="skip"/>  
 </xs:sequence>  
 <xs:attribute ref="ser:FactoryType"/>  
</xs:complexType>  
```  
  
 <span data-ttu-id="6c70a-482">数据协定序列化架构中声明的可选属性 `ser:FactoryType` 引用可以反序列化类型的工厂类。</span><span class="sxs-lookup"><span data-stu-id="6c70a-482">The optional attribute `ser:FactoryType` declared in the Data Contract Serialization schema references a factory class that can deserialize the type.</span></span> <span data-ttu-id="6c70a-483">工厂类必须是正在使用的 `DataContractSerializer` 实例的已知类型集合的一部分。</span><span class="sxs-lookup"><span data-stu-id="6c70a-483">The factory class must be part of the known types collection of the `DataContractSerializer` instance being used.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="6c70a-484"> 已知类型的更多信息，请参见 [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)将 CLR 类型映射到 XSD。</span><span class="sxs-lookup"><span data-stu-id="6c70a-484"> known types, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="datacontract-serialization-schema"></a><span data-ttu-id="6c70a-485">DataContract 序列化架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-485">DataContract Serialization Schema</span></span>  
 <span data-ttu-id="6c70a-486">许多由 `DataContractSerializer` 导出的架构都使用一个特殊数据协定序列化命名空间中的类型、元素和属性：</span><span class="sxs-lookup"><span data-stu-id="6c70a-486">A number of schemas exported by the `DataContractSerializer` use types, elements, and attributes from a special Data Contract Serialization namespace:</span></span>  
  
 <span data-ttu-id="6c70a-487">http://schemas.microsoft.com/2003/10/Serialization</span><span class="sxs-lookup"><span data-stu-id="6c70a-487">http://schemas.microsoft.com/2003/10/Serialization</span></span>  
  
 <span data-ttu-id="6c70a-488">下面是一个完整的数据协定序列化架构声明。</span><span class="sxs-lookup"><span data-stu-id="6c70a-488">The following is a complete Data Contract Serialization schema declaration.</span></span>  
  
```xml  
<xs:schema attributeFormDefault="qualified"          
   elementFormDefault="qualified"        
   targetNamespace =   
    "http://schemas.microsoft.com/2003/10/Serialization/"   
   xmlns:xs="http://www.w3.org/2001/XMLSchema"        
   xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/">  
  
 <!-- Top-level elements for primitive types. -->  
 <xs:element name="anyType" nillable="true" type="xs:anyType"/>  
 <xs:element name="anyURI" nillable="true" type="xs:anyURI"/>  
 <xs:element name="base64Binary"  
       nillable="true" type="xs:base64Binary"/>  
 <xs:element name="boolean" nillable="true" type="xs:boolean"/>  
 <xs:element name="byte" nillable="true" type="xs:byte"/>  
 <xs:element name="dateTime" nillable="true" type="xs:dateTime"/>  
 <xs:element name="decimal" nillable="true" type="xs:decimal"/>  
 <xs:element name="double" nillable="true" type="xs:double"/>  
 <xs:element name="float" nillable="true" type="xs:float"/>  
 <xs:element name="int" nillable="true" type="xs:int"/>  
 <xs:element name="long" nillable="true" type="xs:long"/>  
 <xs:element name="QName" nillable="true" type="xs:QName"/>  
 <xs:element name="short" nillable="true" type="xs:short"/>  
 <xs:element name="string" nillable="true" type="xs:string"/>  
 <xs:element name="unsignedByte"  
       nillable="true" type="xs:unsignedByte"/>  
 <xs:element name="unsignedInt"  
       nillable="true" type="xs:unsignedInt"/>  
 <xs:element name="unsignedLong"  
       nillable="true" type="xs:unsignedLong"/>  
 <xs:element name="unsignedShort"  
       nillable="true" type="xs:unsignedShort"/>  
  
 <!-- Primitive types introduced for certain .NET simple types. -->  
 <xs:element name="char" nillable="true" type="tns:char"/>  
 <xs:simpleType name="char">  
  <xs:restriction base="xs:int"/>  
 </xs:simpleType>  
  
 <!-- xs:duration is restricted to an ordered value space,  
    to map to System.TimeSpan -->  
 <xs:element name="duration" nillable="true" type="tns:duration"/>  
 <xs:simpleType name="duration">  
  <xs:restriction base="xs:duration">  
   <xs:pattern   
     value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?"/>  
   <xs:minInclusive value="-P10675199DT2H48M5.4775808S"/>  
   <xs:maxInclusive value="P10675199DT2H48M5.4775807S"/>  
  </xs:restriction>  
 </xs:simpleType>  
  
 <xs:element name="guid" nillable="true" type="tns:guid"/>  
 <xs:simpleType name="guid">  
  <xs:restriction base="xs:string">  
   <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}"/>  
  </xs:restriction>  
 </xs:simpleType>  
  
 <!-- This is used for schemas exported from ISerializable type. -->  
 <xs:attribute name="FactoryType" type="xs:QName"/>  
</xs:schema>  
```  
  
 <span data-ttu-id="6c70a-489">应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="6c70a-489">The following should be noted:</span></span>  
  
-   <span data-ttu-id="6c70a-490">已引入`ser:char` 来表示 <xref:System.Char>类型的 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="6c70a-490">`ser:char` is introduced to represent Unicode characters of type <xref:System.Char>.</span></span>  
  
-   <span data-ttu-id="6c70a-491">`valuespace` 的 `xs:duration` 已简化为一个有序集，因此可以将其映射到 <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-491">The `valuespace` of `xs:duration` is reduced to an ordered set so that it can be mapped to a <xref:System.TimeSpan>.</span></span>  
  
-   <span data-ttu-id="6c70a-492">在从派生自`FactoryType` 的类型中导出的架构中使用 <xref:System.Runtime.Serialization.ISerializable>。</span><span class="sxs-lookup"><span data-stu-id="6c70a-492">`FactoryType` is used in schemas exported from types that are derived from <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
## <a name="importing-non-datacontract-schemas"></a><span data-ttu-id="6c70a-493">导入非 DataContract 架构</span><span class="sxs-lookup"><span data-stu-id="6c70a-493">Importing non-DataContract schemas</span></span>  
 <span data-ttu-id="6c70a-494">`DataContractSerializer` 具有 `ImportXmlTypes` 选项，可允许导入不符合 `DataContractSerializer` XSD 配置文件的架构（请参见 <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> 属性）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-494">`DataContractSerializer` has the `ImportXmlTypes` option to allow import of schemas that do not conform to the `DataContractSerializer` XSD profile (see the <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> property).</span></span> <span data-ttu-id="6c70a-495">将此选项设置为 `true` 可接受不符合要求的架构类型，并将其映射到下面的实现，即包装 <xref:System.Xml.Serialization.IXmlSerializable> 数组的 <xref:System.Xml.XmlNode> （仅类名称不同）。</span><span class="sxs-lookup"><span data-stu-id="6c70a-495">Setting this option to `true` enables acceptance of non-conforming schema types and mapping them to the following implementation, <xref:System.Xml.Serialization.IXmlSerializable> wrapping an array of <xref:System.Xml.XmlNode> (only the class name differs).</span></span>  
  
```  
[GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
[System.Xml.Serialization.XmlSchemaProviderAttribute("ExportSchema")]  
[System.Xml.Serialization.XmlRootAttribute(IsNullable=false)]  
public partial class Person : object, IXmlSerializable  
{    
  private XmlNode[] nodesField;    
  private static XmlQualifiedName typeName =   
new XmlQualifiedName("Person","http://Microsoft.ServiceModel.Samples");    
  public XmlNode[] Nodes  
  {  
    get {return this.nodesField;}  
    set {this.nodesField = value;}  
  }    
  public void ReadXml(XmlReader reader)  
  {  
    this.nodesField = XmlSerializableServices.ReadNodes(reader);  
  }    
  public void WriteXml(XmlWriter writer)  
  {  
    XmlSerializableServices.WriteNodes(writer, this.Nodes);  
  }    
  public System.Xml.Schema.XmlSchema GetSchema()  
  {  
    return null;  
  }    
  public static XmlQualifiedName ExportSchema(XmlSchemaSet schemas)  
  {  
    XmlSerializableServices.AddDefaultSchema(schemas, typeName);  
    return typeName;  
  }  
}  
```  
  
## <a name="datetimeoffset-serialization"></a><span data-ttu-id="6c70a-496">DateTimeOffset 序列化</span><span class="sxs-lookup"><span data-stu-id="6c70a-496">DateTimeOffset Serialization</span></span>  
 <span data-ttu-id="6c70a-497">未将 <xref:System.DateTimeOffset> 视为基元类型，</span><span class="sxs-lookup"><span data-stu-id="6c70a-497">The <xref:System.DateTimeOffset> is not treated as a primitive type.</span></span> <span data-ttu-id="6c70a-498">而是将其序列化为具有两部分的复杂元素。</span><span class="sxs-lookup"><span data-stu-id="6c70a-498">Instead, it is serialized as a complex element with two parts.</span></span> <span data-ttu-id="6c70a-499">第一部分表示日期时间，第二部分表示日期时间的偏移量。</span><span class="sxs-lookup"><span data-stu-id="6c70a-499">The first part represents the date time, and the second part represents the offset from the date time.</span></span> <span data-ttu-id="6c70a-500">在下面的代码中演示已序列化的 DateTimeOffset 值的示例。</span><span class="sxs-lookup"><span data-stu-id="6c70a-500">An example of a serialized DateTimeOffset value is shown in the following code.</span></span>  
  
```xml  
<OffSet xmlns:a="http://schemas.datacontract.org/2004/07/System">  
  <DateTime i:type="b:dateTime" xmlns=""   
    xmlns:b="http://www.w3.org/2001/XMLSchema">2008-08-28T08:00:00    
  </DateTime>   
  <OffsetMinutes i:type="b:short" xmlns=""   
   xmlns:b="http://www.w3.org/2001/XMLSchema">-480  
   </OffsetMinutes>   
</OffSet>  
```  
  
 <span data-ttu-id="6c70a-501">相应的架构如下所示。</span><span class="sxs-lookup"><span data-stu-id="6c70a-501">The schema is as follows.</span></span>  
  
```xml  
<xs:schema targetNamespace="http://schemas.datacontract.org/2004/07/System">  
   <xs:complexType name="DateTimeOffset">  
      <xs:sequence minOccurs="1" maxOccurs="1">  
         <xs:element name="DateTime" type="xs:dateTime"  
         minOccurs="1" maxOccurs="1" />  
         <xs:elementname="OffsetMinutes" type="xs:short"  
         minOccurs="1" maxOccurs="1" />  
      </xs:sequence>  
   </xs:complexType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c70a-502">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c70a-502">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 <xref:System.Runtime.Serialization.XsdDataContractImporter>  
 [<span data-ttu-id="6c70a-503">使用数据协定</span><span class="sxs-lookup"><span data-stu-id="6c70a-503">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
