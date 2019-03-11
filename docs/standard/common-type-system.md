---
title: 常规类型系统和公共语言规范
description: 了解通用类型系统 (CTS) 和公共语言规范 (CLS) 如何使 .NET 可支持多种语言。
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 3b1f5725-ac94-4f17-8e5f-244442438a4d
ms.openlocfilehash: a6704b09a51a509cb7fbd786f9040454f78cc862
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675363"
---
# <a name="common-type-system--common-language-specification"></a><span data-ttu-id="da0c3-103">常规类型系统和公共语言规范</span><span class="sxs-lookup"><span data-stu-id="da0c3-103">Common Type System & Common Language Specification</span></span>

<span data-ttu-id="da0c3-104">再次介绍 .NET 领域内大量使用的两个术语，对于理解 .NET 实现如何能够允许多语言开发及其工作原理，这两个术语至关重要。</span><span class="sxs-lookup"><span data-stu-id="da0c3-104">Again, two terms that are freely used in the .NET world, they actually are crucial to understand how a .NET implementation enables multi-language development and to understand how it works.</span></span>

## <a name="common-type-system"></a><span data-ttu-id="da0c3-105">常规类型系统</span><span class="sxs-lookup"><span data-stu-id="da0c3-105">Common Type System</span></span>

<span data-ttu-id="da0c3-106">首先，请记住 .NET 实现对语言不可知。</span><span class="sxs-lookup"><span data-stu-id="da0c3-106">To start from the beginning, remember that a .NET implementation is _language agnostic_.</span></span> <span data-ttu-id="da0c3-107">这不仅意味着程序员可以使用可编译为 IL 的任意语言编写代码。</span><span class="sxs-lookup"><span data-stu-id="da0c3-107">This doesn’t just mean that a programmer can write her code in any language that can be compiled to IL.</span></span> <span data-ttu-id="da0c3-108">还意味着程序员需要能够与使用 .NET 实现上可用的其他语言编写的代码进行交互。</span><span class="sxs-lookup"><span data-stu-id="da0c3-108">It also means that she needs to be able to interact with code written in other languages that are able to be used on a .NET implementation.</span></span>

<span data-ttu-id="da0c3-109">为透明地执行此操作，必须使用某种通用方式描所有受支持类型。</span><span class="sxs-lookup"><span data-stu-id="da0c3-109">In order to do this transparently, there has to be a common way to describe all supported types.</span></span> <span data-ttu-id="da0c3-110">这正是通用类型系统 (CTS) 的职责。</span><span class="sxs-lookup"><span data-stu-id="da0c3-110">This is what the Common Type System (CTS) is in charge of doing.</span></span> <span data-ttu-id="da0c3-111">其功能如下：</span><span class="sxs-lookup"><span data-stu-id="da0c3-111">It was made to do several things:</span></span>

*   <span data-ttu-id="da0c3-112">建立用于跨语言执行的框架。</span><span class="sxs-lookup"><span data-stu-id="da0c3-112">Establish a framework for cross-language execution.</span></span>
*   <span data-ttu-id="da0c3-113">提供面向对象的模型，支持在 .NET 实现上实现各种语言。</span><span class="sxs-lookup"><span data-stu-id="da0c3-113">Provide an object-oriented model to support implementing various languages on a .NET implementation.</span></span>
*   <span data-ttu-id="da0c3-114">定义处理类型时所有语言都必须遵守的一组规则。</span><span class="sxs-lookup"><span data-stu-id="da0c3-114">Define a set of rules that all languages must follow when it comes to working with types.</span></span>
*   <span data-ttu-id="da0c3-115">提供包含应用程序开发中使用的基本基元数据类型（如 `Boolean`、`Byte`、`Char` 等）的库。</span><span class="sxs-lookup"><span data-stu-id="da0c3-115">Provide a library that contains the basic primitive types that are used in application development (such as, `Boolean`, `Byte`, `Char` etc.)</span></span>

<span data-ttu-id="da0c3-116">CTS 将定义应支持的两种主要类型：引用和值类型。</span><span class="sxs-lookup"><span data-stu-id="da0c3-116">CTS defines two main kinds of types that should be supported: reference and value types.</span></span> <span data-ttu-id="da0c3-117">其名称表明了其定义。</span><span class="sxs-lookup"><span data-stu-id="da0c3-117">Their names point to their definitions.</span></span>

<span data-ttu-id="da0c3-118">引用类型对象由对对象实际值的引用表示；此处的引用与 C/C++ 中的指针类似。</span><span class="sxs-lookup"><span data-stu-id="da0c3-118">Reference types’ objects are represented by a reference to the object’s actual value; a reference here is similar to a pointer in C/C++.</span></span> <span data-ttu-id="da0c3-119">它仅引用对象值所在的内存位置。</span><span class="sxs-lookup"><span data-stu-id="da0c3-119">It simply refers to a memory location where the objects’ values are.</span></span> <span data-ttu-id="da0c3-120">这对这些类型的用法有重大影响。</span><span class="sxs-lookup"><span data-stu-id="da0c3-120">This has a profound impact on how these types are used.</span></span> <span data-ttu-id="da0c3-121">例如，如果将引用类型分配给个变量，然后将该变量传递到方法，则对该对象的任意更改都将反映到主对象上；不涉及复制操作。</span><span class="sxs-lookup"><span data-stu-id="da0c3-121">If you assign a reference type to a variable and then pass that variable into a method, for instance, any changes to the object will be reflected on the main object; there is no copying.</span></span>

<span data-ttu-id="da0c3-122">值类型则相反，其中对象由其值表示。</span><span class="sxs-lookup"><span data-stu-id="da0c3-122">Value types are the opposite, where the objects are represented by their values.</span></span> <span data-ttu-id="da0c3-123">如果将值类型分配给变量，实质上就是复制对象的值。</span><span class="sxs-lookup"><span data-stu-id="da0c3-123">If you assign a value type to a variable, you are essentially copying a value of the object.</span></span>

<span data-ttu-id="da0c3-124">CTS 将定义多个类型类别，每个类别均有其特定的语义和用法：</span><span class="sxs-lookup"><span data-stu-id="da0c3-124">CTS defines several categories of types, each with their specific semantics and usage:</span></span>

*   <span data-ttu-id="da0c3-125">类</span><span class="sxs-lookup"><span data-stu-id="da0c3-125">Classes</span></span>
*   <span data-ttu-id="da0c3-126">结构</span><span class="sxs-lookup"><span data-stu-id="da0c3-126">Structures</span></span>
*   <span data-ttu-id="da0c3-127">枚举</span><span class="sxs-lookup"><span data-stu-id="da0c3-127">Enums</span></span>
*   <span data-ttu-id="da0c3-128">接口</span><span class="sxs-lookup"><span data-stu-id="da0c3-128">Interfaces</span></span>
*   <span data-ttu-id="da0c3-129">委托</span><span class="sxs-lookup"><span data-stu-id="da0c3-129">Delegates</span></span>

<span data-ttu-id="da0c3-130">CTS 还将定义类型的所有其他属性，例如访问修饰符、有效的类型成员以及继承和重载的工作原理等。</span><span class="sxs-lookup"><span data-stu-id="da0c3-130">CTS also defines all other properties of the types, such as access modifiers, what are valid type members, how inheritance and overloading works and so on.</span></span> <span data-ttu-id="da0c3-131">遗憾的是，有关上述任意一点的深入介绍已超出此类介绍性文章的介绍范围，但可以参阅底部的[更多资源](#more-resources)部分，获取包含这些主题的详细内容的链接。</span><span class="sxs-lookup"><span data-stu-id="da0c3-131">Unfortunately, going deep into any of those is beyond the scope of an introductory article such as this, but you can consult [More resources](#more-resources) section at the end for links to more in-depth content that covers these topics.</span></span>

## <a name="common-language-specification"></a><span data-ttu-id="da0c3-132">公共语言规范</span><span class="sxs-lookup"><span data-stu-id="da0c3-132">Common Language Specification</span></span>

<span data-ttu-id="da0c3-133">为实现完全互操作性情景，代码中创建的所有对象都必须依赖于使用它的语言（即其调用方）的某些共性。</span><span class="sxs-lookup"><span data-stu-id="da0c3-133">To enable full interoperability scenarios, all objects that are created in code must rely on some commonality in the languages that are consuming them (are their _callers_).</span></span> <span data-ttu-id="da0c3-134">由于存在多种不同语言，因此 .NET 在公共语言规范 (CLS) 中指定了这些共性。</span><span class="sxs-lookup"><span data-stu-id="da0c3-134">Since there are numerous different languages, .NET has specified those commonalities in something called the **Common Language Specification** (CLS).</span></span> <span data-ttu-id="da0c3-135">CLS 定义了许多常见应用程序所需的一组功能。</span><span class="sxs-lookup"><span data-stu-id="da0c3-135">CLS defines a set of features that are needed by many common applications.</span></span> <span data-ttu-id="da0c3-136">对于在 .NET 上实现的语言，它还就语言需要支持的内容提供了一组脚本。</span><span class="sxs-lookup"><span data-stu-id="da0c3-136">It also provides a sort of recipe for any language that is implemented on top of .NET on what it needs to support.</span></span>

<span data-ttu-id="da0c3-137">CLS 是 CTS 的子集。</span><span class="sxs-lookup"><span data-stu-id="da0c3-137">CLS is a subset of the CTS.</span></span> <span data-ttu-id="da0c3-138">这意味着，CTS 中的所有规则也适用于 CLS，除非 CLS 规则更严格。</span><span class="sxs-lookup"><span data-stu-id="da0c3-138">This means that all of the rules in the CTS also apply to the CLS, unless the CLS rules are more strict.</span></span> <span data-ttu-id="da0c3-139">如果仅使用 CLS 中的规则生成组件（即在其 API 中仅公开 CLS 功能），则将该组件视为**符合 CLS**。</span><span class="sxs-lookup"><span data-stu-id="da0c3-139">If a component is built using only the rules in the CLS, that is, it exposes only the CLS features in its API, it is said to be **CLS-compliant**.</span></span> <span data-ttu-id="da0c3-140">例如，`<framework-librares>` 完全符合 CLS，因为它们需要对 .NET 支持的所有语言有效。</span><span class="sxs-lookup"><span data-stu-id="da0c3-140">For instance, the `<framework-librares>` are CLS-compliant precisely because they need to work across all of the languages that are supported on .NET.</span></span>

<span data-ttu-id="da0c3-141">可参阅下方[更多资源](#more-resources)部分中的文档，大致了解 CLS 中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="da0c3-141">You can consult the documents in the [More Resources](#more-resources) section below to get an overview of all the features in the CLS.</span></span>

## <a name="more-resources"></a><span data-ttu-id="da0c3-142">更多资源</span><span class="sxs-lookup"><span data-stu-id="da0c3-142">More resources</span></span>

*   [<span data-ttu-id="da0c3-143">常规类型系统</span><span class="sxs-lookup"><span data-stu-id="da0c3-143">Common Type System</span></span>](./base-types/common-type-system.md)
*   [<span data-ttu-id="da0c3-144">公共语言规范</span><span class="sxs-lookup"><span data-stu-id="da0c3-144">Common Language Specification</span></span>](language-independence-and-language-independent-components.md)
