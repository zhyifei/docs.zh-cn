---
title: C# 版本控制 - C# 指南
description: 了解 C# 和 .NET 中的版本控制工作原理
ms.date: 01/08/2017
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.openlocfilehash: 4dc8e7e521bf209d6ca69a84534d277fb8a93ea8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351779"
---
# <a name="versioning-in-c"></a><span data-ttu-id="8a9a4-103">C# 中的版本控制</span><span class="sxs-lookup"><span data-stu-id="8a9a4-103">Versioning in C#</span></span> #

<span data-ttu-id="8a9a4-104">本教程将介绍版本控制在 .NET 中的含义。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-104">In this tutorial you'll learn what versioning means in .NET.</span></span> <span data-ttu-id="8a9a4-105">还将介绍对库进行版本控制以及升级到新版本的库时需要考虑的因素。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-105">You'll also learn the factors to consider when versioning your library as well as upgrading to a new version of the a library.</span></span>

## <a name="authoring-libraries"></a><span data-ttu-id="8a9a4-106">创作库</span><span class="sxs-lookup"><span data-stu-id="8a9a4-106">Authoring Libraries</span></span>

<span data-ttu-id="8a9a4-107">对于创建 .NET 库以供公共使用的开发人员，经常需要推出新更新。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-107">As a developer who has created .NET libraries for public use, you've most likely been in situations where you have to roll out new updates.</span></span> <span data-ttu-id="8a9a4-108">如何处理此过程关系重大，因为开发人员需确保从现有代码无缝转换到新版本的库。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-108">How you go about this process matters a lot as you need to ensure that there's a seamless transition of existing code to the new version of your library.</span></span> <span data-ttu-id="8a9a4-109">以下是创建新版本时的几个注意事项：</span><span class="sxs-lookup"><span data-stu-id="8a9a4-109">Here are several things to consider when creating a new release:</span></span>

### <a name="semantic-versioning"></a><span data-ttu-id="8a9a4-110">语义版本控制</span><span class="sxs-lookup"><span data-stu-id="8a9a4-110">Semantic Versioning</span></span>

<span data-ttu-id="8a9a4-111">[语义版本控制](http://semver.org/)（简称 SemVer）是应用于库版本的命名约定，用于表示特定里程碑事件。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-111">[Semantic versioning](http://semver.org/) (SemVer for short) is a naming convention applied to versions of your library to signify specific milestone events.</span></span>
<span data-ttu-id="8a9a4-112">理想情况下，提供给库的版本信息应帮助开发人员确定版本是否与使用相同库的早期版本的项目兼容。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-112">Ideally, the version information you give your library should help developers determine the compatibility with their projects that make use of older versions of that same library.</span></span>

<span data-ttu-id="8a9a4-113">SemVer 的最基本方法是 3 组件格式 `MAJOR.MINOR.PATCH`，其中：</span><span class="sxs-lookup"><span data-stu-id="8a9a4-113">The most basic approach to SemVer is the 3 component format `MAJOR.MINOR.PATCH`, where:</span></span>
 
* <span data-ttu-id="8a9a4-114">进行不兼容的 API 更改时，`MAJOR` 将会增加</span><span class="sxs-lookup"><span data-stu-id="8a9a4-114">`MAJOR` is incremented when you make incompatible API changes</span></span>
* <span data-ttu-id="8a9a4-115">以后向兼容方式添加功能时，`MINOR` 将会增加</span><span class="sxs-lookup"><span data-stu-id="8a9a4-115">`MINOR` is incremented when you add functionality in a backwards-compatible manner</span></span>
* <span data-ttu-id="8a9a4-116">进行后向兼容 bug 修复时，`PATCH` 将会增加</span><span class="sxs-lookup"><span data-stu-id="8a9a4-116">`PATCH` is incremented when you make backwards-compatible bug fixes</span></span>

<span data-ttu-id="8a9a4-117">将版本信息应用于 .NET 库时，还可通过其他方法指定其他方案，如预发布版本等。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-117">There are also ways to specify other scenarios like pre-release versions etc. when applying version information to your .NET library.</span></span>

### <a name="backwards-compatibility"></a><span data-ttu-id="8a9a4-118">后向兼容</span><span class="sxs-lookup"><span data-stu-id="8a9a4-118">Backwards Compatibility</span></span>

<span data-ttu-id="8a9a4-119">发布新版本的库时，与先前版本的后向兼容很可能成为主要关注事项之一。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-119">As you release new versions of your library, backwards compatibility with previous versions will most likely be one of your major concerns.</span></span>
<span data-ttu-id="8a9a4-120">如果重新编译时，依赖于先前版本的代码适用于新版本，则新版本的库与先前版本是源兼容的。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-120">A new version of your library is source compatible with a previous version if code that depends on the previous version can, when recompiled, work with the new version.</span></span> <span data-ttu-id="8a9a4-121">在没有重新编译的情况下，如果依赖于先前版本的应用程序适用于新版本，则新版本的库是二进制兼容的。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-121">A new version of your library is binary compatible if an application that depended on the old version can, without recompilation, work with the new version.</span></span>

<span data-ttu-id="8a9a4-122">以下是维护与较旧版本库的后向兼容时的注意事项：</span><span class="sxs-lookup"><span data-stu-id="8a9a4-122">Here are some things to consider when trying to maintain backwards compatibility with older versions of your library:</span></span>

* <span data-ttu-id="8a9a4-123">虚拟方法：如果在新版本中使虚拟方法成为非虚拟方法，则必须更新重写该方法的项目。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-123">Virtual methods: When you make a virtual method non-virtual in your new version it means that projects that override that method will have to be updated.</span></span> <span data-ttu-id="8a9a4-124">这是一项重大更改，强烈建议不要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-124">This is a huge breaking change and is strongly discouraged.</span></span>
* <span data-ttu-id="8a9a4-125">方法签名：虽然更新方法行为也需要更改其签名，但应创建重载，使调用该方法的代码仍可正常运行。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-125">Method signatures: When updating a method behaviour requires you to change its signature as well, you should instead create an overload so that code calling into that method will still work.</span></span>
<span data-ttu-id="8a9a4-126">始终可以使用旧方法签名来调用新方法签名，以使实现保持一致。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-126">You can always manipulate the old method signature to call into the new method signature so that implementation remains consistent.</span></span>
* <span data-ttu-id="8a9a4-127">[已过时属性](programming-guide/concepts/attributes/common-attributes.md#Obsolete)：可在代码中使用此属性指定已弃用且很可能在将来版本中删除的类或类成员。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-127">[Obsolete attribute](programming-guide/concepts/attributes/common-attributes.md#Obsolete): You can use this attribute in your code to specify classes or class members that are deprecated and likely to be removed in future versions.</span></span>
<span data-ttu-id="8a9a4-128">这可确保使用此库的开发人员能更好地为重大更改做好准备。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-128">This ensures developers utilizing your library are better prepared for breaking changes.</span></span>
* <span data-ttu-id="8a9a4-129">可选方法参数：如果使以前的可选方法参数变为强制性方法参数或更改它们的默认值，则需要更新不提供这些参数的所有代码。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-129">Optional Method Arguments: When you make previously optional method arguments compulsory or change their default value then all code that does not supply those arguments will need to be updated.</span></span>
> [!NOTE]
> <span data-ttu-id="8a9a4-130">将强制性参数变为可选参数应几乎没有影响，对于不更改方法的行为的情况尤其如此。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-130">Making compulsory arguments optional should have very little effect especially if it doesn't change the method's behaviour.</span></span>

<span data-ttu-id="8a9a4-131">为用户提供的升级到新版本库的方法越简单，用户升级的速度很可能会越快。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-131">The easier you make it for your users to upgrade to the new version of your library, the more likely that they will upgrade sooner.</span></span>

### <a name="application-configuration-file"></a><span data-ttu-id="8a9a4-132">应用程序配置文件</span><span class="sxs-lookup"><span data-stu-id="8a9a4-132">Application Configuration File</span></span>

<span data-ttu-id="8a9a4-133">.NET 开发人员很可能已在大多数项目类型中遇到过 [`app.config` 文件](https://msdn.microsoft.com/library/1fk1t1t0(v=vs.110).aspx)。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-133">As a .NET developer there's a very high chance you've encountered [the `app.config` file](https://msdn.microsoft.com/library/1fk1t1t0(v=vs.110).aspx) present in most project types.</span></span>
<span data-ttu-id="8a9a4-134">此类简单配置文件对于改进新更新的推出有重要作用。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-134">This simple configuration file can go a long way into improving the rollout of new updates.</span></span> <span data-ttu-id="8a9a4-135">通常应以以下方式设计库：将可能定期更改的信息存储在 `app.config` 文件中。这样，当更新此类信息时，只需使用新版本的配置文件替换旧版本配置文件即可，而无需重新编译库。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-135">You should generally design your libraries in such a way that information that is likely to change regularly is stored in the `app.config` file, this way when such information is updated the config file of older versions just needs to be replaced with the new one without the need for recompilation of the library.</span></span>

## <a name="consuming-libraries"></a><span data-ttu-id="8a9a4-136">使用库</span><span class="sxs-lookup"><span data-stu-id="8a9a4-136">Consuming Libraries</span></span>

<span data-ttu-id="8a9a4-137">作为使用由其他开发人员构建的 .NET 库的开发人员，你很可能已经发现新版本的库可能不与项目完全兼容，你经常需要更新代码以使用这些更改。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-137">As a developer that consumes .NET libraries built by other developers you're most likely aware that a new version of a library might not be fully compatible with your project and you might often find yourself having to update your code to work with those changes.</span></span>

<span data-ttu-id="8a9a4-138">幸运的是，C# 和 .NET 生态系统附带一些功能和技术，通过这些功能和技术，我们可以轻松更新应用，使其适用于可能引入重大更改的新版本库。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-138">Lucky for you C# and the .NET ecosystem comes with features and techniques that allow us to easily update our app to work with new versions of libraries that might introduce breaking changes.</span></span>

### <a name="assembly-binding-redirection"></a><span data-ttu-id="8a9a4-139">程序集绑定重定向</span><span class="sxs-lookup"><span data-stu-id="8a9a4-139">Assembly Binding Redirection</span></span>

<span data-ttu-id="8a9a4-140">可使用 `app.config` 文件更新应用使用的库版本。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-140">You can use the `app.config` file to update the version of a library your app uses.</span></span> <span data-ttu-id="8a9a4-141">通过添加[*绑定重定向*](https://msdn.microsoft.com/library/7wd6ex19(v=vs.110).aspx)，可在无需重新编译应用的情况下使用新的库版本。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-141">By adding what is called a [*binding redirect*](https://msdn.microsoft.com/library/7wd6ex19(v=vs.110).aspx) your can use the new library version without having to recompile your app.</span></span> <span data-ttu-id="8a9a4-142">下面的示例演示更新应用的 `app.config` 文件的方法，以便使用 `ReferencedLibrary` 的 `1.0.1` 修补程序版本，而不是最初编译时使用的 `1.0.0` 版本。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-142">The following example shows how you would update your app's `app.config` file to use the `1.0.1` patch version of `ReferencedLibrary` instead of the `1.0.0` version it was originally compiled with.</span></span>

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> <span data-ttu-id="8a9a4-143">仅当 `ReferencedLibrary` 的新版本与应用二进制兼容时，此方法有效。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-143">This approach will only work if the new version of `ReferencedLibrary` is binary compatible with your app.</span></span>
> <span data-ttu-id="8a9a4-144">有关确定兼容性时需要注意的更改，请参阅上文中的[后向兼容](#backwards-compatibility)部分。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-144">See the [Backwards Compatibility](#backwards-compatibility) section above for changes to look out for when determining compatibility.</span></span>

### <a name="new"></a><span data-ttu-id="8a9a4-145">new</span><span class="sxs-lookup"><span data-stu-id="8a9a4-145">new</span></span>

<span data-ttu-id="8a9a4-146">使用 `new` 修饰符隐藏基类的继承成员。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-146">You use the `new` modifier to hide inherited members of a base class.</span></span> <span data-ttu-id="8a9a4-147">这是派生类响应基类中的更新的一种方法。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-147">This is one way derived classes can respond to updates in base classes.</span></span>

<span data-ttu-id="8a9a4-148">请参见以下示例：</span><span class="sxs-lookup"><span data-stu-id="8a9a4-148">Take the following example:</span></span>

[!code-csharp[Sample usage of the 'new' modifier](../../samples/csharp/versioning/new/Program.cs#sample)]

<span data-ttu-id="8a9a4-149">**输出**</span><span class="sxs-lookup"><span data-stu-id="8a9a4-149">**Output**</span></span>

```
A base method
A derived method
```

<span data-ttu-id="8a9a4-150">上面的示例演示 `DerivedClass` 如何隐藏 `BaseClass` 中的 `MyMethod`方法。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-150">From the example above you can see how `DerivedClass` hides the `MyMethod` method present in `BaseClass`.</span></span>
<span data-ttu-id="8a9a4-151">也就是说，当新版本库中的基类添加派生类中已存在的成员时，在派生类成员上使用 `new` 修饰符即可隐藏基类成员。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-151">This means that when a base class in the new version of a library adds a member that already exists in your derived class, you can simply use the `new` modifier on your derived class member to hide the base class member.</span></span>

<span data-ttu-id="8a9a4-152">未指定 `new` 修饰符时，派生类将默认隐藏基类中的冲突成员，尽管会生成编译器警告，但仍将编译代码。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-152">When no `new` modifier is specified, a derived class will by default hide conflicting members in a base class, although a compiler warning will be generated the code will still compile.</span></span> <span data-ttu-id="8a9a4-153">也就是说，仅需向现有类添加新成员，新版本的库即可与依赖于它的代码实现源兼容和二进制兼容。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-153">This means that simply adding new members to an existing class makes that new version of your library both source and binary compatible with code that depends on it.</span></span>

### <a name="override"></a><span data-ttu-id="8a9a4-154">override</span><span class="sxs-lookup"><span data-stu-id="8a9a4-154">override</span></span>

<span data-ttu-id="8a9a4-155">`override` 修饰符指派生实现会扩展基类成员的实现而不是将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-155">The `override` modifier means a derived implementation extends the implementation of a base class member rather than hides it.</span></span> <span data-ttu-id="8a9a4-156">基类成员需要具有应用于自身的 `virtual` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-156">The base class member needs to have the `virtual` modifier applied to it.</span></span>

[!code-csharp[Sample usage of the 'override' modifier](../../samples/csharp/versioning/override/Program.cs#sample)]

<span data-ttu-id="8a9a4-157">**输出**</span><span class="sxs-lookup"><span data-stu-id="8a9a4-157">**Output**</span></span>

```
Base Method One: Method One
Derived Method One: Derived Method One
```

<span data-ttu-id="8a9a4-158">`override` 修饰符将在编译时计算，如果此修饰符找不到要重写的虚拟成员，编译器将引发错误。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-158">The `override` modifier is evaluated at compile time and the compiler will throw an error if it doesn't find a virtual member to override.</span></span>

<span data-ttu-id="8a9a4-159">了解所讨论的这些技术以及使用情境，对于简化库版本之间的转换有重要作用。</span><span class="sxs-lookup"><span data-stu-id="8a9a4-159">Your knowledge of the discussed techniques as well as your understanding of what situations to use them will go a long way to boost the ease of transition between versions of a library.</span></span>
