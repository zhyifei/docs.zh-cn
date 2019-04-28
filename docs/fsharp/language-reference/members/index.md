---
title: 成员
description: 了解有关对象成员的信息F#编程语言。
ms.date: 05/16/2016
ms.openlocfilehash: c32bd76ab60673563f0cc45ce0fb569b2ea262b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903846"
---
# <a name="members"></a><span data-ttu-id="26408-103">成员</span><span class="sxs-lookup"><span data-stu-id="26408-103">Members</span></span>

<span data-ttu-id="26408-104">本部分介绍 F# 对象类型的成员。</span><span class="sxs-lookup"><span data-stu-id="26408-104">This section describes members of F# object types.</span></span>

## <a name="remarks"></a><span data-ttu-id="26408-105">备注</span><span class="sxs-lookup"><span data-stu-id="26408-105">Remarks</span></span>

<span data-ttu-id="26408-106">*成员*是一种属于类型定义的功能，可使用 `member` 关键字进行声明。</span><span class="sxs-lookup"><span data-stu-id="26408-106">*Members* are features that are part of a type definition and are declared with the `member` keyword.</span></span> <span data-ttu-id="26408-107">记录、类、可区分联合、接口和结构等 F# 对象类型都支持成员。</span><span class="sxs-lookup"><span data-stu-id="26408-107">F# object types such as records, classes, discriminated unions, interfaces, and structures support members.</span></span> <span data-ttu-id="26408-108">有关详细信息，请参阅[记录](../records.md)、[类](../classes.md)、[可区分联合](../discriminated-Unions.md)、[接口](../interfaces.md)和[结构](../structures.md)。</span><span class="sxs-lookup"><span data-stu-id="26408-108">For more information, see [Records](../records.md), [Classes](../classes.md), [Discriminated Unions](../discriminated-Unions.md), [Interfaces](../interfaces.md), and [Structures](../structures.md).</span></span>

<span data-ttu-id="26408-109">成员通常组成类型的公共接口，这就是成员通常是公共成员（除非另外指定）的原因。</span><span class="sxs-lookup"><span data-stu-id="26408-109">Members typically make up the public interface for a type, which is why they are public unless otherwise specified.</span></span> <span data-ttu-id="26408-110">也可以声明私有成员或内部成员。</span><span class="sxs-lookup"><span data-stu-id="26408-110">Members can also be declared private or internal.</span></span> <span data-ttu-id="26408-111">有关详细信息，请参阅[访问控制](../access-Control.md)。</span><span class="sxs-lookup"><span data-stu-id="26408-111">For more information, see [Access Control](../access-Control.md).</span></span> <span data-ttu-id="26408-112">类型的签名还可用于公开或不公开类型的某些成员。</span><span class="sxs-lookup"><span data-stu-id="26408-112">Signatures for types can also be used to expose or not expose certain members of a type.</span></span> <span data-ttu-id="26408-113">有关详细信息，请参阅[签名](../signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="26408-113">For more information, see [Signatures](../signatures.md).</span></span>

<span data-ttu-id="26408-114">只能与类一起使用的私有字段和 `do` 绑定不是真正的成员，因为它们从不是类型的公共接口的一部分，并且也不是用 `member` 关键字声明的，但本部分对它们也进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="26408-114">Private fields and `do` bindings, which are used only with classes, are not true members, because they are never part of the public interface of a type and are not declared with the `member` keyword, but they are described in this section also.</span></span>

## <a name="related-topics"></a><span data-ttu-id="26408-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="26408-115">Related Topics</span></span>

|<span data-ttu-id="26408-116">主题</span><span class="sxs-lookup"><span data-stu-id="26408-116">Topic</span></span>|<span data-ttu-id="26408-117">描述</span><span class="sxs-lookup"><span data-stu-id="26408-117">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="26408-118">类中的 `let` 绑定</span><span class="sxs-lookup"><span data-stu-id="26408-118">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)|<span data-ttu-id="26408-119">介绍类中私有字段和函数的定义。</span><span class="sxs-lookup"><span data-stu-id="26408-119">Describes the definition of private fields and functions in classes.</span></span>|
|[<span data-ttu-id="26408-120">类中的 `do` 绑定</span><span class="sxs-lookup"><span data-stu-id="26408-120">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)|<span data-ttu-id="26408-121">介绍对象初始化代码的规范。</span><span class="sxs-lookup"><span data-stu-id="26408-121">Describes the specification of object initialization code.</span></span>|
|[<span data-ttu-id="26408-122">属性</span><span class="sxs-lookup"><span data-stu-id="26408-122">Properties</span></span>](properties.md)|<span data-ttu-id="26408-123">介绍类和其他类型中的属性成员。</span><span class="sxs-lookup"><span data-stu-id="26408-123">Describes property members in classes and other types.</span></span>|
|[<span data-ttu-id="26408-124">索引属性</span><span class="sxs-lookup"><span data-stu-id="26408-124">Indexed Properties</span></span>](indexed-properties.md)|<span data-ttu-id="26408-125">介绍类和其他类型中的类似数组的属性。</span><span class="sxs-lookup"><span data-stu-id="26408-125">Describes array-like properties in classes and other types.</span></span>|
|[<span data-ttu-id="26408-126">方法</span><span class="sxs-lookup"><span data-stu-id="26408-126">Methods</span></span>](methods.md)|<span data-ttu-id="26408-127">介绍属于类型的成员的函数。</span><span class="sxs-lookup"><span data-stu-id="26408-127">Describes functions that are members of a type.</span></span>|
|[<span data-ttu-id="26408-128">构造函数</span><span class="sxs-lookup"><span data-stu-id="26408-128">Constructors</span></span>](constructors.md)|<span data-ttu-id="26408-129">介绍用于初始化类型的对象的特殊函数。</span><span class="sxs-lookup"><span data-stu-id="26408-129">Describes special functions that initialize objects of a type.</span></span>|
|[<span data-ttu-id="26408-130">运算符重载</span><span class="sxs-lookup"><span data-stu-id="26408-130">Operator Overloading</span></span>](../operator-overloading.md)|<span data-ttu-id="26408-131">介绍类型的自定义运算符的定义。</span><span class="sxs-lookup"><span data-stu-id="26408-131">Describes the definition of customized operators for types.</span></span>|
|[<span data-ttu-id="26408-132">事件</span><span class="sxs-lookup"><span data-stu-id="26408-132">Events</span></span>](events.md)|<span data-ttu-id="26408-133">介绍 F# 中的事件定义和事件处理支持。</span><span class="sxs-lookup"><span data-stu-id="26408-133">Describes the definition of events and event handling support in F#.</span></span>|
|[<span data-ttu-id="26408-134">显式字段：`val` 关键字</span><span class="sxs-lookup"><span data-stu-id="26408-134">Explicit Fields: The `val` Keyword</span></span>](explicit-fields-the-val-keyword.md)|<span data-ttu-id="26408-135">介绍类型中未初始化字段的定义。</span><span class="sxs-lookup"><span data-stu-id="26408-135">Describes the definition of uninitialized fields in a type.</span></span>|