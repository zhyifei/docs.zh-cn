---
title: 指定完全限定的类型名称
ms.date: 03/14/2018
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9281906f5500d954f3a0c7abface4ee43adcb64d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628534"
---
# <a name="specifying-fully-qualified-type-names"></a><span data-ttu-id="d6548-102">指定完全限定的类型名称</span><span class="sxs-lookup"><span data-stu-id="d6548-102">Specifying Fully Qualified Type Names</span></span>
<span data-ttu-id="d6548-103">必须指定类型名称才能为各种反射操作提供有效输入。</span><span class="sxs-lookup"><span data-stu-id="d6548-103">You must specify type names to have valid input to various reflection operations.</span></span> <span data-ttu-id="d6548-104">完全限定的类型名称包含程序集名称规范、命名空间规范和类型名称。</span><span class="sxs-lookup"><span data-stu-id="d6548-104">A fully qualified type name consists of an assembly name specification, a namespace specification, and a type name.</span></span> <span data-ttu-id="d6548-105">类型名称规范由 <xref:System.Type.GetType%2A?displayProperty=nameWithType>、<xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>、<xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> 和 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 等方法使用。</span><span class="sxs-lookup"><span data-stu-id="d6548-105">Type name specifications are used by methods such as <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, and <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="grammar-for-type-names"></a><span data-ttu-id="d6548-106">类型名称的语法</span><span class="sxs-lookup"><span data-stu-id="d6548-106">Grammar for Type Names</span></span>  
 <span data-ttu-id="d6548-107">语法定义正式语言的语法。</span><span class="sxs-lookup"><span data-stu-id="d6548-107">The grammar defines the syntax of formal languages.</span></span> <span data-ttu-id="d6548-108">下表列出了词法规则，说明如何识别有效输入。</span><span class="sxs-lookup"><span data-stu-id="d6548-108">The following table lists lexical rules that describe how to recognize a valid input.</span></span> <span data-ttu-id="d6548-109">最终元素（无法再减小的元素）全部以大写字母显示。</span><span class="sxs-lookup"><span data-stu-id="d6548-109">Terminals (those elements that are not further reducible) are shown in all uppercase letters.</span></span> <span data-ttu-id="d6548-110">非最终元素（可以再减小的元素）则显示为大小写混合或带单引号的字符串，但单引号 (') 不是语法本身的一部分。</span><span class="sxs-lookup"><span data-stu-id="d6548-110">Nonterminals (those elements that are further reducible) are shown in mixed-case or singly quoted strings, but the single quote (') is not a part of the syntax itself.</span></span> <span data-ttu-id="d6548-111">竖线 (|) 表示具有子规则的规则。</span><span class="sxs-lookup"><span data-stu-id="d6548-111">The pipe character (&#124;) denotes rules that have subrules.</span></span>  

```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | ArrayTypeSpec
    | TypeName
    ;

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```

## <a name="specifying-special-characters"></a><span data-ttu-id="d6548-112">指定特殊字符</span><span class="sxs-lookup"><span data-stu-id="d6548-112">Specifying Special Characters</span></span>  
 <span data-ttu-id="d6548-113">在类型名称中，IDENTIFIER 是语言规则确定的任何有效名称。</span><span class="sxs-lookup"><span data-stu-id="d6548-113">In a type name, IDENTIFIER is any valid name determined by the rules of a language.</span></span>  
  
 <span data-ttu-id="d6548-114">反斜杠 (\\) 可用作转义符来分隔以下用作 IDENTIFIER 一部分的标记。</span><span class="sxs-lookup"><span data-stu-id="d6548-114">Use the backslash (\\) as an escape character to separate the following tokens when used as part of IDENTIFIER.</span></span>  
  
|<span data-ttu-id="d6548-115">标记</span><span class="sxs-lookup"><span data-stu-id="d6548-115">Token</span></span>|<span data-ttu-id="d6548-116">含义</span><span class="sxs-lookup"><span data-stu-id="d6548-116">Meaning</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="d6548-117">\\,</span><span class="sxs-lookup"><span data-stu-id="d6548-117">\\,</span></span>|<span data-ttu-id="d6548-118">程序集分隔符。</span><span class="sxs-lookup"><span data-stu-id="d6548-118">Assembly separator.</span></span>|  
|\\+|<span data-ttu-id="d6548-119">嵌套类型分隔符。</span><span class="sxs-lookup"><span data-stu-id="d6548-119">Nested type separator.</span></span>|  
|\\&|<span data-ttu-id="d6548-120">引用类型。</span><span class="sxs-lookup"><span data-stu-id="d6548-120">Reference type.</span></span>|  
|\\*|<span data-ttu-id="d6548-121">指针类型。</span><span class="sxs-lookup"><span data-stu-id="d6548-121">Pointer type.</span></span>|  
|<span data-ttu-id="d6548-122">\\[</span><span class="sxs-lookup"><span data-stu-id="d6548-122">\\[</span></span>|<span data-ttu-id="d6548-123">数组维度分隔符。</span><span class="sxs-lookup"><span data-stu-id="d6548-123">Array dimension delimiter.</span></span>|  
|<span data-ttu-id="d6548-124">\\]</span><span class="sxs-lookup"><span data-stu-id="d6548-124">\\]</span></span>|<span data-ttu-id="d6548-125">数组维度分隔符。</span><span class="sxs-lookup"><span data-stu-id="d6548-125">Array dimension delimiter.</span></span>|  
|<span data-ttu-id="d6548-126">\\。</span><span class="sxs-lookup"><span data-stu-id="d6548-126">\\.</span></span>|<span data-ttu-id="d6548-127">只有在数组规范中使用句点时，才应在句点前使用反斜杠。</span><span class="sxs-lookup"><span data-stu-id="d6548-127">Use the backslash before a period only if the period is used in an array specification.</span></span> <span data-ttu-id="d6548-128">NamespaceSpec 中的句点不使用反斜杠。</span><span class="sxs-lookup"><span data-stu-id="d6548-128">Periods in NamespaceSpec do not take the backslash.</span></span>|  
|<span data-ttu-id="d6548-129">\\\|必要时将反斜杠用作字符串文本。</span><span class="sxs-lookup"><span data-stu-id="d6548-129">\\\|Backslash when needed as a string literal.</span></span>|  
  
 <span data-ttu-id="d6548-130">请注意，除 AssemblyNameSpec 外，所有 TypeSpec 组件中的空格都是相关的。</span><span class="sxs-lookup"><span data-stu-id="d6548-130">Note that in all TypeSpec components except AssemblyNameSpec, spaces are relevant.</span></span> <span data-ttu-id="d6548-131">在 AssemblyNameSpec 中，“,”分隔符之前的空格相关，但“,”分隔符之后的空格将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d6548-131">In the AssemblyNameSpec, spaces before the ',' separator are relevant, but spaces after the ',' separator are ignored.</span></span>  
  
 <span data-ttu-id="d6548-132">反射类（如 <xref:System.Type.FullName%2A?displayProperty=nameWithType>）返回改变后的名称，以便使返回的名称可以用在对 <xref:System.Type.GetType%2A> 的调用中（如同用在 `MyType.GetType(myType.FullName)` 中）。</span><span class="sxs-lookup"><span data-stu-id="d6548-132">Reflection classes, such as <xref:System.Type.FullName%2A?displayProperty=nameWithType>, return the mangled name so that the returned name can be used in a call to <xref:System.Type.GetType%2A>, as in `MyType.GetType(myType.FullName)`.</span></span>  
  
 <span data-ttu-id="d6548-133">例如，某个类型的完全限定名称可能是 `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`。</span><span class="sxs-lookup"><span data-stu-id="d6548-133">For example, the fully qualified name for a type might be `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span></span>  
  
 <span data-ttu-id="d6548-134">如果命名空间为 `Ozzy.Out+Back`，则必须在加号前加反斜杠。</span><span class="sxs-lookup"><span data-stu-id="d6548-134">If the namespace were `Ozzy.Out+Back`, then the plus sign must be preceded by a backslash.</span></span> <span data-ttu-id="d6548-135">否则，分析器会将其解释为嵌套分隔符。</span><span class="sxs-lookup"><span data-stu-id="d6548-135">Otherwise, the parser would interpret it as a nesting separator.</span></span> <span data-ttu-id="d6548-136">反射会将该字符串当作 `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly` 发出。</span><span class="sxs-lookup"><span data-stu-id="d6548-136">Reflection emits this string as `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span></span>  
  
## <a name="specifying-assembly-names"></a><span data-ttu-id="d6548-137">指定程序集名称</span><span class="sxs-lookup"><span data-stu-id="d6548-137">Specifying Assembly Names</span></span>  
 <span data-ttu-id="d6548-138">程序集名称规范中至少需要具有程序集的文本名称 (IDENTIFIER)。</span><span class="sxs-lookup"><span data-stu-id="d6548-138">The minimum information required in an assembly name specification is the textual name (IDENTIFIER) of the assembly.</span></span> <span data-ttu-id="d6548-139">可以在 IDENTIFIER 后添加下表所述的以逗号分隔的属性/值对列表。</span><span class="sxs-lookup"><span data-stu-id="d6548-139">You can follow the IDENTIFIER by a comma-separated list of property/value pairs as described in the following table.</span></span> <span data-ttu-id="d6548-140">IDENTIFIER 命名应遵循文件命名的规则。</span><span class="sxs-lookup"><span data-stu-id="d6548-140">IDENTIFIER naming should follow the rules for file naming.</span></span> <span data-ttu-id="d6548-141">IDENTIFIER 不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d6548-141">The IDENTIFIER is case-insensitive.</span></span>  
  
|<span data-ttu-id="d6548-142">属性名称</span><span class="sxs-lookup"><span data-stu-id="d6548-142">Property name</span></span>|<span data-ttu-id="d6548-143">说明</span><span class="sxs-lookup"><span data-stu-id="d6548-143">Description</span></span>|<span data-ttu-id="d6548-144">允许的值</span><span class="sxs-lookup"><span data-stu-id="d6548-144">Allowable values</span></span>|  
|-------------------|-----------------|----------------------|  
|<span data-ttu-id="d6548-145">**Version**</span><span class="sxs-lookup"><span data-stu-id="d6548-145">**Version**</span></span>|<span data-ttu-id="d6548-146">程序集版本号</span><span class="sxs-lookup"><span data-stu-id="d6548-146">Assembly version number</span></span>|<span data-ttu-id="d6548-147">Major.Minor.Build.Revision，其中 Major、Minor、Build 和 Revision 是 0 和 65535 之间（含 0 和 65535）的整数。</span><span class="sxs-lookup"><span data-stu-id="d6548-147">*Major.Minor.Build.Revision*, where *Major*, *Minor*, *Build*, and *Revision* are integers between 0 and 65535 inclusive.</span></span>|  
|<span data-ttu-id="d6548-148">PublicKey</span><span class="sxs-lookup"><span data-stu-id="d6548-148">**PublicKey**</span></span>|<span data-ttu-id="d6548-149">完整公钥</span><span class="sxs-lookup"><span data-stu-id="d6548-149">Full public key</span></span>|<span data-ttu-id="d6548-150">完整公钥十六进制格式的字符串值。</span><span class="sxs-lookup"><span data-stu-id="d6548-150">String value of full public key in hexadecimal format.</span></span> <span data-ttu-id="d6548-151">指定 null 引用（在 Visual Basic 中为 Nothing）以显式指示私有程序集。</span><span class="sxs-lookup"><span data-stu-id="d6548-151">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|  
|<span data-ttu-id="d6548-152">**PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="d6548-152">**PublicKeyToken**</span></span>|<span data-ttu-id="d6548-153">公钥标记（完整公钥的 8 字节哈希）</span><span class="sxs-lookup"><span data-stu-id="d6548-153">Public key token (8-byte hash of the full public key)</span></span>|<span data-ttu-id="d6548-154">公钥标记十六进制格式的字符串值。</span><span class="sxs-lookup"><span data-stu-id="d6548-154">String value of public key token in hexadecimal format.</span></span> <span data-ttu-id="d6548-155">指定 null 引用（在 Visual Basic 中为 Nothing）以显式指示私有程序集。</span><span class="sxs-lookup"><span data-stu-id="d6548-155">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|  
|<span data-ttu-id="d6548-156">**区域性**</span><span class="sxs-lookup"><span data-stu-id="d6548-156">**Culture**</span></span>|<span data-ttu-id="d6548-157">程序集区域性</span><span class="sxs-lookup"><span data-stu-id="d6548-157">Assembly culture</span></span>|<span data-ttu-id="d6548-158">RFC-1766 格式的程序集区域性，对于独立于语言（非附属）的程序集则为“非特定”。</span><span class="sxs-lookup"><span data-stu-id="d6548-158">Culture of the assembly in RFC-1766 format, or "neutral" for language-independent (nonsatellite) assemblies.</span></span>|  
|<span data-ttu-id="d6548-159">**自定义**</span><span class="sxs-lookup"><span data-stu-id="d6548-159">**Custom**</span></span>|<span data-ttu-id="d6548-160">自定义二进制大对象 (BLOB)。</span><span class="sxs-lookup"><span data-stu-id="d6548-160">Custom binary large object (BLOB).</span></span> <span data-ttu-id="d6548-161">它当前仅用于由[本机图像生成器 (Ngen)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) 生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="d6548-161">This is currently used only in assemblies generated by the [Native Image Generator (Ngen)](../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>|<span data-ttu-id="d6548-162">本机图像生成器工具用以向程序集缓存通知所安装程序集为本机图像的自定义字符串，因此该自定义字符串安装在本机图像缓存中。</span><span class="sxs-lookup"><span data-stu-id="d6548-162">Custom string used by the Native Image Generator tool to notify the assembly cache that the assembly being installed is a native image, and is therefore to be installed in the native image cache.</span></span> <span data-ttu-id="d6548-163">也称作 zap 字符串。</span><span class="sxs-lookup"><span data-stu-id="d6548-163">Also called a zap string.</span></span>|  
  
 <span data-ttu-id="d6548-164">下面的示例演示具有默认区域性的简单命名程序集的 AssemblyName。</span><span class="sxs-lookup"><span data-stu-id="d6548-164">The following example shows an **AssemblyName** for a simply named assembly with default culture.</span></span>  
  
```csharp  
com.microsoft.crypto, Culture=""   
```  
  
 <span data-ttu-id="d6548-165">下面的示例演示区域性为“en”的强名称程序集的完全指定的引用。</span><span class="sxs-lookup"><span data-stu-id="d6548-165">The following example shows a fully specified reference for a strongly named assembly with culture "en".</span></span>  
  
```csharp  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0   
```  
  
 <span data-ttu-id="d6548-166">下面的示例演示部分指定的 AssemblyName，它可以由具有强名称或简单名称的程序集来满足。</span><span class="sxs-lookup"><span data-stu-id="d6548-166">The following examples each show a partially specified **AssemblyName**, which can be satisfied by either a strong or a simply named assembly.</span></span>  
  
```csharp  
com.microsoft.crypto  
com.microsoft.crypto, Culture=""  
com.microsoft.crypto, Culture=en   
```  
  
 <span data-ttu-id="d6548-167">下面的示例分别演示一个部分指定的 AssemblyName，它必须由具有简单名称的程序集来满足。</span><span class="sxs-lookup"><span data-stu-id="d6548-167">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a simply named assembly.</span></span>  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=null   
com.microsoft.crypto, Culture=en, PublicKeyToken=null  
```  
  
 <span data-ttu-id="d6548-168">下面的示例分别演示一个部分指定的 AssemblyName，它必须由具有强名称的程序集来满足。</span><span class="sxs-lookup"><span data-stu-id="d6548-168">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a strongly named assembly.</span></span>  
  
```csharp  
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012  
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,  
    Version=1.0.0.0  
```  
  
## <a name="specifying-pointers"></a><span data-ttu-id="d6548-169">指定指针</span><span class="sxs-lookup"><span data-stu-id="d6548-169">Specifying Pointers</span></span>  
 <span data-ttu-id="d6548-170">SimpleTypeSpec\* 表示未托管的指针。</span><span class="sxs-lookup"><span data-stu-id="d6548-170">SimpleTypeSpec\* represents an unmanaged pointer.</span></span> <span data-ttu-id="d6548-171">例如，要获取指向 MyType 类型的指针，请使用 `Type.GetType("MyType*")`。</span><span class="sxs-lookup"><span data-stu-id="d6548-171">For example, to get a pointer to type MyType, use `Type.GetType("MyType*")`.</span></span> <span data-ttu-id="d6548-172">要获取指向 MyType 类型指针的指针，请使用 `Type.GetType("MyType**")`。</span><span class="sxs-lookup"><span data-stu-id="d6548-172">To get a pointer to a pointer to type MyType, use `Type.GetType("MyType**")`.</span></span>  
  
## <a name="specifying-references"></a><span data-ttu-id="d6548-173">指定引用</span><span class="sxs-lookup"><span data-stu-id="d6548-173">Specifying References</span></span>  
 <span data-ttu-id="d6548-174">SimpleTypeSpec & 表示托管指针或引用。</span><span class="sxs-lookup"><span data-stu-id="d6548-174">SimpleTypeSpec & represents a managed pointer or reference.</span></span> <span data-ttu-id="d6548-175">例如，要获取对 MyType 类型的引用，请使用 `Type.GetType("MyType &")`。</span><span class="sxs-lookup"><span data-stu-id="d6548-175">For example, to get a reference to type MyType, use `Type.GetType("MyType &")`.</span></span> <span data-ttu-id="d6548-176">请注意，与指针不同，引用仅限于一个级别。</span><span class="sxs-lookup"><span data-stu-id="d6548-176">Note that unlike pointers, references are limited to one level.</span></span>  
  
## <a name="specifying-arrays"></a><span data-ttu-id="d6548-177">指定数组</span><span class="sxs-lookup"><span data-stu-id="d6548-177">Specifying Arrays</span></span>  
 <span data-ttu-id="d6548-178">在 BNF 语法中，ReflectionEmitDimension 仅适用于使用 <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> 检索的不完整类型定义。</span><span class="sxs-lookup"><span data-stu-id="d6548-178">In the BNF Grammar, ReflectionEmitDimension only applies to incomplete type definitions retrieved using <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d6548-179">不完整类型定义是使用 <xref:System.Reflection.Emit?displayProperty=nameWithType> 构造但没有对其调用 <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> 的 <xref:System.Reflection.Emit.TypeBuilder> 对象。</span><span class="sxs-lookup"><span data-stu-id="d6548-179">Incomplete type definitions are <xref:System.Reflection.Emit.TypeBuilder> objects constructed using <xref:System.Reflection.Emit?displayProperty=nameWithType> but on which <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> has not been called.</span></span> <span data-ttu-id="d6548-180">ReflectionDimension 可用于检索任何已完成的类型定义，即已加载的类型。</span><span class="sxs-lookup"><span data-stu-id="d6548-180">ReflectionDimension can be used to retrieve any type definition that has been completed, that is, a type that has been loaded.</span></span>  
  
 <span data-ttu-id="d6548-181">通过指定数组的级别，可以访问反射中的数组：</span><span class="sxs-lookup"><span data-stu-id="d6548-181">Arrays are accessed in reflection by specifying the rank of the array:</span></span>  
  
-   <span data-ttu-id="d6548-182">`Type.GetType("MyArray[]")` 获取下限为 0 的单维数组。</span><span class="sxs-lookup"><span data-stu-id="d6548-182">`Type.GetType("MyArray[]")` gets a single-dimension array with 0 lower bound.</span></span>  
  
-   <span data-ttu-id="d6548-183">`Type.GetType("MyArray[*]")` 获取下限未知的单维数组。</span><span class="sxs-lookup"><span data-stu-id="d6548-183">`Type.GetType("MyArray[*]")` gets a single-dimension array with unknown lower bound.</span></span>  
  
-   <span data-ttu-id="d6548-184">`Type.GetType("MyArray[][]")` 获取二维数组的数组。</span><span class="sxs-lookup"><span data-stu-id="d6548-184">`Type.GetType("MyArray[][]")` gets a two-dimensional array's array.</span></span>  
  
-   <span data-ttu-id="d6548-185">`Type.GetType("MyArray[*,*]")` 和 `Type.GetType("MyArray[,]")` 获取下限未知的矩形二维数组。</span><span class="sxs-lookup"><span data-stu-id="d6548-185">`Type.GetType("MyArray[*,*]")` and `Type.GetType("MyArray[,]")` gets a rectangular two-dimensional array with unknown lower bounds.</span></span>  
  
 <span data-ttu-id="d6548-186">请注意，从运行时的角度来看，`MyArray[] != MyArray[*]`，但对于多维数组，这两种表示是等效的。</span><span class="sxs-lookup"><span data-stu-id="d6548-186">Note that from a runtime point of view, `MyArray[] != MyArray[*]`, but for multidimensional arrays, the two notations are equivalent.</span></span> <span data-ttu-id="d6548-187">也就是说，`Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` 的计算结果为 true。</span><span class="sxs-lookup"><span data-stu-id="d6548-187">That is, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` evaluates to **true**.</span></span>  
  
 <span data-ttu-id="d6548-188">对于 ModuleBuilder.GetType，`MyArray[0..5]` 指示大小为 6、下限为 0 的单维数组。</span><span class="sxs-lookup"><span data-stu-id="d6548-188">For **ModuleBuilder.GetType**, `MyArray[0..5]` indicates a single-dimension array with size 6, lower bound 0.</span></span> <span data-ttu-id="d6548-189">`MyArray[4…]` 指示大小未知、下限为 4 的单维数组。</span><span class="sxs-lookup"><span data-stu-id="d6548-189">`MyArray[4…]` indicates a single-dimension array of unknown size and lower bound 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6548-190">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6548-190">See also</span></span>
- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d6548-191">查看类型信息</span><span class="sxs-lookup"><span data-stu-id="d6548-191">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)
