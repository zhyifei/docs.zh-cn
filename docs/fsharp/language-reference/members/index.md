---
title: 成员 (F#)
description: '了解在 F # 编程语言的对象成员。'
keywords: visual f#, f#, 函数编程
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e472f50a-4939-4e62-abbc-471f8f265790
ms.openlocfilehash: ca34c8d073594791ec268a85ad56f50cc6d9e435
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="members"></a><span data-ttu-id="b0039-104">成员</span><span class="sxs-lookup"><span data-stu-id="b0039-104">Members</span></span>

<span data-ttu-id="b0039-105">本部分介绍 F# 对象类型的成员。</span><span class="sxs-lookup"><span data-stu-id="b0039-105">This section describes members of F# object types.</span></span>


## <a name="remarks"></a><span data-ttu-id="b0039-106">备注</span><span class="sxs-lookup"><span data-stu-id="b0039-106">Remarks</span></span>
<span data-ttu-id="b0039-107">*成员*是一种属于类型定义的功能，可使用 `member` 关键字进行声明。</span><span class="sxs-lookup"><span data-stu-id="b0039-107">*Members* are features that are part of a type definition and are declared with the `member` keyword.</span></span> <span data-ttu-id="b0039-108">记录、类、可区分联合、接口和结构等 F# 对象类型都支持成员。</span><span class="sxs-lookup"><span data-stu-id="b0039-108">F# object types such as records, classes, discriminated unions, interfaces, and structures support members.</span></span> <span data-ttu-id="b0039-109">有关详细信息，请参阅[记录](../records.md)、[类](../classes.md)、[可区分联合](../discriminated-Unions.md)、[接口](../interfaces.md)和[结构](../structures.md)。</span><span class="sxs-lookup"><span data-stu-id="b0039-109">For more information, see [Records](../records.md), [Classes](../classes.md), [Discriminated Unions](../discriminated-Unions.md), [Interfaces](../interfaces.md), and [Structures](../structures.md).</span></span>

<span data-ttu-id="b0039-110">成员通常组成类型的公共接口，这就是成员通常是公共成员（除非另外指定）的原因。</span><span class="sxs-lookup"><span data-stu-id="b0039-110">Members typically make up the public interface for a type, which is why they are public unless otherwise specified.</span></span> <span data-ttu-id="b0039-111">也可以声明私有成员或内部成员。</span><span class="sxs-lookup"><span data-stu-id="b0039-111">Members can also be declared private or internal.</span></span> <span data-ttu-id="b0039-112">有关详细信息，请参阅[访问控制](../access-Control.md)。</span><span class="sxs-lookup"><span data-stu-id="b0039-112">For more information, see [Access Control](../access-Control.md).</span></span> <span data-ttu-id="b0039-113">类型的签名还可用于公开或不公开类型的某些成员。</span><span class="sxs-lookup"><span data-stu-id="b0039-113">Signatures for types can also be used to expose or not expose certain members of a type.</span></span> <span data-ttu-id="b0039-114">有关详细信息，请参阅[签名](../signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="b0039-114">For more information, see [Signatures](../signatures.md).</span></span>

<span data-ttu-id="b0039-115">只能与类一起使用的私有字段和 `do` 绑定不是真正的成员，因为它们从不是类型的公共接口的一部分，并且也不是用 `member` 关键字声明的，但本部分对它们也进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="b0039-115">Private fields and `do` bindings, which are used only with classes, are not true members, because they are never part of the public interface of a type and are not declared with the `member` keyword, but they are described in this section also.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b0039-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="b0039-116">Related Topics</span></span>


|<span data-ttu-id="b0039-117">主题</span><span class="sxs-lookup"><span data-stu-id="b0039-117">Topic</span></span>|<span data-ttu-id="b0039-118">说明</span><span class="sxs-lookup"><span data-stu-id="b0039-118">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="b0039-119">类中的 `let` 绑定</span><span class="sxs-lookup"><span data-stu-id="b0039-119">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)|<span data-ttu-id="b0039-120">介绍类中私有字段和函数的定义。</span><span class="sxs-lookup"><span data-stu-id="b0039-120">Describes the definition of private fields and functions in classes.</span></span>|
|[<span data-ttu-id="b0039-121">类中的 `do` 绑定</span><span class="sxs-lookup"><span data-stu-id="b0039-121">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)|<span data-ttu-id="b0039-122">介绍对象初始化代码的规范。</span><span class="sxs-lookup"><span data-stu-id="b0039-122">Describes the specification of object initialization code.</span></span>|
|[<span data-ttu-id="b0039-123">属性</span><span class="sxs-lookup"><span data-stu-id="b0039-123">Properties</span></span>](properties.md)|<span data-ttu-id="b0039-124">介绍类和其他类型中的属性成员。</span><span class="sxs-lookup"><span data-stu-id="b0039-124">Describes property members in classes and other types.</span></span>|
|[<span data-ttu-id="b0039-125">索引属性</span><span class="sxs-lookup"><span data-stu-id="b0039-125">Indexed Properties</span></span>](indexed-properties.md)|<span data-ttu-id="b0039-126">介绍类和其他类型中的类似数组的属性。</span><span class="sxs-lookup"><span data-stu-id="b0039-126">Describes array-like properties in classes and other types.</span></span>|
|[<span data-ttu-id="b0039-127">方法</span><span class="sxs-lookup"><span data-stu-id="b0039-127">Methods</span></span>](methods.md)|<span data-ttu-id="b0039-128">介绍属于类型的成员的函数。</span><span class="sxs-lookup"><span data-stu-id="b0039-128">Describes functions that are members of a type.</span></span>|
|[<span data-ttu-id="b0039-129">构造函数</span><span class="sxs-lookup"><span data-stu-id="b0039-129">Constructors</span></span>](constructors.md)|<span data-ttu-id="b0039-130">介绍用于初始化类型的对象的特殊函数。</span><span class="sxs-lookup"><span data-stu-id="b0039-130">Describes special functions that initialize objects of a type.</span></span>|
|[<span data-ttu-id="b0039-131">运算符重载</span><span class="sxs-lookup"><span data-stu-id="b0039-131">Operator Overloading</span></span>](../operator-overloading.md)|<span data-ttu-id="b0039-132">介绍类型的自定义运算符的定义。</span><span class="sxs-lookup"><span data-stu-id="b0039-132">Describes the definition of customized operators for types.</span></span>|
|[<span data-ttu-id="b0039-133">事件</span><span class="sxs-lookup"><span data-stu-id="b0039-133">Events</span></span>](events.md)|<span data-ttu-id="b0039-134">介绍 F# 中的事件定义和事件处理支持。</span><span class="sxs-lookup"><span data-stu-id="b0039-134">Describes the definition of events and event handling support in F#.</span></span>|
|[<span data-ttu-id="b0039-135">显式字段：`val` 关键字</span><span class="sxs-lookup"><span data-stu-id="b0039-135">Explicit Fields: The `val` Keyword</span></span>](explicit-fields-the-val-keyword.md)|<span data-ttu-id="b0039-136">介绍类型中未初始化字段的定义。</span><span class="sxs-lookup"><span data-stu-id="b0039-136">Describes the definition of uninitialized fields in a type.</span></span>|
