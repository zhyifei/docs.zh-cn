---
title: '签名文件 （F #）'
description: '了解如何使用 F # 签名文件来保存一组 F # 程序元素，如类型、 命名空间和模块的信息的公共签名。'
ms.date: 06/15/2018
ms.openlocfilehash: f0836aa7f638dc9e2b066b0f46bbb6c086347615
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "45991228"
---
# <a name="signatures"></a><span data-ttu-id="d765e-103">签名</span><span class="sxs-lookup"><span data-stu-id="d765e-103">Signatures</span></span>

<span data-ttu-id="d765e-104">签名文件包含有关一组 F# 程序元素（如类型、命名空间和模块）的公共签名的信息。</span><span class="sxs-lookup"><span data-stu-id="d765e-104">A signature file contains information about the public signatures of a set of F# program elements, such as types, namespaces, and modules.</span></span> <span data-ttu-id="d765e-105">它可用于指定这些程序元素的可访问性。</span><span class="sxs-lookup"><span data-stu-id="d765e-105">It can be used to specify the accessibility of these program elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="d765e-106">备注</span><span class="sxs-lookup"><span data-stu-id="d765e-106">Remarks</span></span>

<span data-ttu-id="d765e-107">对于每个 F# 代码文件，均可具有 *签名文件*，该文件的名称与代码文件相同，但其扩展名为 .fsi 而非 .fs。</span><span class="sxs-lookup"><span data-stu-id="d765e-107">For each F# code file, you can have a *signature file*, which is a file that has the same name as the code file but with the extension .fsi instead of .fs.</span></span> <span data-ttu-id="d765e-108">如果你直接使用命令行，签名文件还可添加到编译命令行。</span><span class="sxs-lookup"><span data-stu-id="d765e-108">Signature files can also be added to the compilation command-line if you are using the command line directly.</span></span> <span data-ttu-id="d765e-109">为了区分代码文件和签名文件，代码文件有时称为 *实现文件*。</span><span class="sxs-lookup"><span data-stu-id="d765e-109">To distinguish between code files and signature files, code files are sometimes referred to as *implementation files*.</span></span> <span data-ttu-id="d765e-110">在项目中，签名文件应位于关联的代码文件之前。</span><span class="sxs-lookup"><span data-stu-id="d765e-110">In a project, the signature file should precede the associated code file.</span></span>

<span data-ttu-id="d765e-111">签名文件描述相应的实现文件中的命名空间、模块、类型和成员。</span><span class="sxs-lookup"><span data-stu-id="d765e-111">A signature file describes the namespaces, modules, types, and members in the corresponding implementation file.</span></span> <span data-ttu-id="d765e-112">你使用签名文件中的信息来指定相应实现文件中的哪部分代码可从实现文件外部的代码进行访问、哪部分代码属于实现文件内部。</span><span class="sxs-lookup"><span data-stu-id="d765e-112">You use the information in a signature file to specify what parts of the code in the corresponding implementation file can be accessed from code outside the implementation file, and what parts are internal to the implementation file.</span></span> <span data-ttu-id="d765e-113">包含在签名文件中的命名空间、模块和类型必须是包含在实现文件中的命名空间、模块和类型的子集。</span><span class="sxs-lookup"><span data-stu-id="d765e-113">The namespaces, modules, and types that are included in the signature file must be a subset of the namespaces, modules, and types that are included in the implementation file.</span></span> <span data-ttu-id="d765e-114">除了本主题后面记录的一些例外之外，签名文件中未列出的那些语言元素被视为实现文件专用元素。</span><span class="sxs-lookup"><span data-stu-id="d765e-114">With some exceptions noted later in this topic, those language elements that are not listed in the signature file are considered private to the implementation file.</span></span> <span data-ttu-id="d765e-115">如果项目或命令行中未找到签名文件，则使用默认可访问性。</span><span class="sxs-lookup"><span data-stu-id="d765e-115">If no signature file is found in the project or command line, the default accessibility is used.</span></span>

<span data-ttu-id="d765e-116">有关默认可访问性的详细信息，请参阅[访问控制](access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="d765e-116">For more information about the default accessibility, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="d765e-117">在签名文件中，你不会重复定义类型以及实现每个方法或函数。</span><span class="sxs-lookup"><span data-stu-id="d765e-117">In a signature file, you do not repeat the definition of the types and the implementations of each method or function.</span></span> <span data-ttu-id="d765e-118">相反，可以对每个方法和函数使用签名，它将作为由模块或命名空间片段实现的功能的完整规范。</span><span class="sxs-lookup"><span data-stu-id="d765e-118">Instead, you use the signature for each method and function, which acts as a complete specification of the functionality that is implemented by a module or namespace fragment.</span></span> <span data-ttu-id="d765e-119">类型签名的语法与在接口和抽象类的抽象方法声明中使用的语法相同，并且当它正确显示编译的输入时还由 IntelliSense 和 F# interpreter fsi.exe 显示。</span><span class="sxs-lookup"><span data-stu-id="d765e-119">The syntax for a type signature is the same as that used in abstract method declarations in interfaces and abstract classes, and is also shown by IntelliSense and by the F# interpreter fsi.exe when it displays correctly compiled input.</span></span>

<span data-ttu-id="d765e-120">如果类型签名中没有足够的信息来指示类型是否密封或它是否为接口类型，那么你必须添加一个特性，指示编译器类型的性质。</span><span class="sxs-lookup"><span data-stu-id="d765e-120">If there is not enough information in the type signature to indicate whether a type is sealed, or whether it is an interface type, you must add an attribute that indicates the nature of the type to the compiler.</span></span> <span data-ttu-id="d765e-121">下表中描述了用于此目的的特性。</span><span class="sxs-lookup"><span data-stu-id="d765e-121">Attributes that you use for this purpose are described in the following table.</span></span>

|<span data-ttu-id="d765e-122">特性</span><span class="sxs-lookup"><span data-stu-id="d765e-122">Attribute</span></span>|<span data-ttu-id="d765e-123">描述</span><span class="sxs-lookup"><span data-stu-id="d765e-123">Description</span></span>|
|---------|-----------|
|`[<Sealed>]`|<span data-ttu-id="d765e-124">适用于没有抽象成员或不应扩展的类型。</span><span class="sxs-lookup"><span data-stu-id="d765e-124">For a type that has no abstract members, or that should not be extended.</span></span>|
|`[<Interface>]`|<span data-ttu-id="d765e-125">适用于接口类型。</span><span class="sxs-lookup"><span data-stu-id="d765e-125">For a type that is an interface.</span></span>|
<span data-ttu-id="d765e-126">如果实现文件中的签名和声明的特性不一致，则编译器将产生错误。</span><span class="sxs-lookup"><span data-stu-id="d765e-126">The compiler produces an error if the attributes are not consistent between the signature and the declaration in the implementation file.</span></span>

<span data-ttu-id="d765e-127">使用关键字 `val` 来创建用于值或函数值的签名。</span><span class="sxs-lookup"><span data-stu-id="d765e-127">Use the keyword `val` to create a signature for a value or function value.</span></span> <span data-ttu-id="d765e-128">关键字 `type` 引入类型签名。</span><span class="sxs-lookup"><span data-stu-id="d765e-128">The keyword `type` introduces a type signature.</span></span>

<span data-ttu-id="d765e-129">你可使用 `--sig` 编译器选项生成签名文件。</span><span class="sxs-lookup"><span data-stu-id="d765e-129">You can generate a signature file by using the `--sig` compiler option.</span></span> <span data-ttu-id="d765e-130">通常情况下，不用手动编写 .fsi 文件。</span><span class="sxs-lookup"><span data-stu-id="d765e-130">Generally, you do not write .fsi files manually.</span></span> <span data-ttu-id="d765e-131">相反，可通过使用编译器生成 .fsi 文件，将它们添加到项目中（如果存在），并通过删除不希望被访问的方法和函数对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="d765e-131">Instead, you generate .fsi files by using the compiler, add them to your project, if you have one, and edit them by removing methods and functions that you do not want to be accessible.</span></span>

<span data-ttu-id="d765e-132">类型签名存在几个规则：</span><span class="sxs-lookup"><span data-stu-id="d765e-132">There are several rules for type signatures:</span></span>

- <span data-ttu-id="d765e-133">实现文件中的类型缩写不得与签名文件中没有缩写的类型匹配。</span><span class="sxs-lookup"><span data-stu-id="d765e-133">Type abbreviations in an implementation file must not match a type without an abbreviation in a signature file.</span></span>

- <span data-ttu-id="d765e-134">记录和可辨识的联合必须要么公开其所有字段和构造函数，要么不公开其任何字段和构造函数，并且签名中的顺序必须匹配实现文件中的顺序。</span><span class="sxs-lookup"><span data-stu-id="d765e-134">Records and discriminated unions must expose either all or none of their fields and constructors, and the order in the signature must match the order in the implementation file.</span></span> <span data-ttu-id="d765e-135">类可以公开签名中部分或全部字段和方法或者不公开任何字段和方法。</span><span class="sxs-lookup"><span data-stu-id="d765e-135">Classes can reveal some, all, or none of their fields and methods in the signature.</span></span>

- <span data-ttu-id="d765e-136">具有构造函数的类和结构必须公开其基类的声明（ `inherits` 声明）。</span><span class="sxs-lookup"><span data-stu-id="d765e-136">Classes and structures that have constructors must expose the declarations of their base classes (the `inherits` declaration).</span></span> <span data-ttu-id="d765e-137">此外，具有构造函数的类和结构必须公开其所有的抽象方法和接口声明。</span><span class="sxs-lookup"><span data-stu-id="d765e-137">Also, classes and structures that have constructors must expose all of their abstract methods and interface declarations.</span></span>

- <span data-ttu-id="d765e-138">接口类型必须显示其所有方法和接口。</span><span class="sxs-lookup"><span data-stu-id="d765e-138">Interface types must reveal all their methods and interfaces.</span></span>

<span data-ttu-id="d765e-139">值签名的规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="d765e-139">The rules for value signatures are as follows:</span></span>

- <span data-ttu-id="d765e-140">签名中的可访问性修饰符（`public`、 `internal`等）以及 `inline` 和 `mutable` 修饰符必须与实现中的修饰符匹配。</span><span class="sxs-lookup"><span data-stu-id="d765e-140">Modifiers for accessibility (`public`, `internal`, and so on) and the `inline` and `mutable` modifiers in the signature must match those in the implementation.</span></span>

- <span data-ttu-id="d765e-141">泛型类型参数的数目（不管是隐式推断还是显式声明）必须匹配，并且泛型类型参数中的类型和类型约束必须匹配。</span><span class="sxs-lookup"><span data-stu-id="d765e-141">The number of generic type parameters (either implicitly inferred or explicitly declared) must match, and the types and type constraints in generic type parameters must match.</span></span>

- <span data-ttu-id="d765e-142">如果使用了 `Literal` 特性，则它必须同时显示在签名和实现中，且必须为两者使用相同的文字值。</span><span class="sxs-lookup"><span data-stu-id="d765e-142">If the `Literal` attribute is used, it must appear in both the signature and the implementation, and the same literal value must be used for both.</span></span>

- <span data-ttu-id="d765e-143">签名和实现的参数模式（也称为 *arity*）必须一致。</span><span class="sxs-lookup"><span data-stu-id="d765e-143">The pattern of parameters (also known as the *arity*) of signatures and implementations must be consistent.</span></span>

- <span data-ttu-id="d765e-144">如果签名文件中的参数名称不同于相应的实现文件中，签名文件中的名称将使用相反，它可能会导致调试或分析时出现的问题。</span><span class="sxs-lookup"><span data-stu-id="d765e-144">If parameter names in a signature file differ from the corresponding implementation file, the name in the signature file will be used instead, which may cause issues when debugging or profiling.</span></span> <span data-ttu-id="d765e-145">如果希望此类不匹配项，启用警告 3218 在项目文件中的通知或调用编译器时 (请参阅`--warnon`下[编译器选项](compiler-options.md))。</span><span class="sxs-lookup"><span data-stu-id="d765e-145">If you wish to be notified of such mismatches, enable warning 3218 in your project file or when invoking the compiler (see `--warnon` under [Compiler Options](compiler-options.md)).</span></span>

<span data-ttu-id="d765e-146">下面的代码示例显示具有命名空间、模块、函数值、类型签名以及相应特性的签名文件示例。</span><span class="sxs-lookup"><span data-stu-id="d765e-146">The following code example shows an example of a signature file that has namespace, module, function value, and type signatures together with the appropriate attributes.</span></span> <span data-ttu-id="d765e-147">它还显示相应的实现文件。</span><span class="sxs-lookup"><span data-stu-id="d765e-147">It also shows the corresponding implementation file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9002.fs)]

<span data-ttu-id="d765e-148">下面的代码演示实现文件。</span><span class="sxs-lookup"><span data-stu-id="d765e-148">The following code shows the implementation file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9001.fs)]

## <a name="see-also"></a><span data-ttu-id="d765e-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="d765e-149">See also</span></span>

- [<span data-ttu-id="d765e-150">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="d765e-150">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d765e-151">访问控制</span><span class="sxs-lookup"><span data-stu-id="d765e-151">Access Control</span></span>](access-control.md)
- [<span data-ttu-id="d765e-152">编译器选项</span><span class="sxs-lookup"><span data-stu-id="d765e-152">Compiler Options</span></span>](compiler-options.md)
