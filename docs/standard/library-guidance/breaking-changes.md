---
title: 重大更改和.NET 库
description: 有关在中导航时创建的.NET 库的重大更改的最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 83c01fdad7d836877bf692b87eeb0230219ded36
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "49369808"
---
# <a name="breaking-changes"></a><span data-ttu-id="299c8-103">重大更改</span><span class="sxs-lookup"><span data-stu-id="299c8-103">Breaking changes</span></span>

<span data-ttu-id="299c8-104">对于 .NET 库，在现有用户的稳定性和未来创新之间找到平衡具有重要意义。</span><span class="sxs-lookup"><span data-stu-id="299c8-104">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="299c8-105">库创作者倾向于重新构建和重新构思代码以使其达成完美程度，但中断对现有客户提供服务将产生消极影响，对低级库尤其如此。</span><span class="sxs-lookup"><span data-stu-id="299c8-105">Library authors lean towards refactoring and rethinking code until it's perfect, but breaking your existing users has a negative impact, especially for low-level libraries.</span></span>

## <a name="project-types-and-breaking-changes"></a><span data-ttu-id="299c8-106">项目类型和重大更改</span><span class="sxs-lookup"><span data-stu-id="299c8-106">Project types and breaking changes</span></span>

<span data-ttu-id="299c8-107">.NET 社区如何使用库更改对最终用户开发人员的重大更改的效果。</span><span class="sxs-lookup"><span data-stu-id="299c8-107">How a library is used by the .NET community changes the effect of breaking changes on end-user developers.</span></span>

* <span data-ttu-id="299c8-108">**低和中间级库**如序列化程序、 HTML 分析器、 数据库对象关系映射器中或 web 框架的最受影响的重大更改。</span><span class="sxs-lookup"><span data-stu-id="299c8-108">**Low and middle-level libraries** like a serializer, HTML parser, database object-relational mapper, or web framework are the most affected by breaking changes.</span></span>

  <span data-ttu-id="299c8-109">构建基块包是通过最终用户开发人员生成应用程序，以及其他库用作 NuGet 依赖项。</span><span class="sxs-lookup"><span data-stu-id="299c8-109">Building block packages are used by end-user developers to build applications, and by other libraries as NuGet dependencies.</span></span> <span data-ttu-id="299c8-110">例如，您正在构建应用程序，并且使用的开源客户端来调用 web 服务。</span><span class="sxs-lookup"><span data-stu-id="299c8-110">For example, you're building an application and are using an open-source client to call a web service.</span></span> <span data-ttu-id="299c8-111">客户端使用的依赖项的一个重大更新不是可以解决问题。</span><span class="sxs-lookup"><span data-stu-id="299c8-111">A breaking update to a dependency the client uses isn't something you can fix.</span></span> <span data-ttu-id="299c8-112">它是需要更改的开源客户端，并且你有无法控制。</span><span class="sxs-lookup"><span data-stu-id="299c8-112">It's the open-source client that needs to be changed and you have no control over it.</span></span> <span data-ttu-id="299c8-113">您必须找到兼容版本的库或提交的客户端库的修复程序并等待新版本。</span><span class="sxs-lookup"><span data-stu-id="299c8-113">You have to find compatible versions of the libraries or submit a fix to the client library and wait for a new version.</span></span> <span data-ttu-id="299c8-114">最坏的情形是如果你想要使用两个依赖于第三个库的互相不兼容版本的库。</span><span class="sxs-lookup"><span data-stu-id="299c8-114">The worst-case situation is if you want to use two libraries that depend on mutually incompatible versions of a third library.</span></span>

* <span data-ttu-id="299c8-115">**高级库**等一系列 UI 控件对不太敏感的重大更改。</span><span class="sxs-lookup"><span data-stu-id="299c8-115">**High-level libraries** like a suite of UI controls are less sensitive to breaking changes.</span></span>

  <span data-ttu-id="299c8-116">最终用户应用程序中直接引用高级库。</span><span class="sxs-lookup"><span data-stu-id="299c8-116">High-level libraries are directly referenced in an end-user application.</span></span> <span data-ttu-id="299c8-117">如果发生重大更改，开发人员可以选择更新到最新版本，或者可以修改其应用程序以使用重大更改。</span><span class="sxs-lookup"><span data-stu-id="299c8-117">If breaking changes occur, the developer can choose to update to the latest version, or can modify their application to work with the breaking change.</span></span>

<span data-ttu-id="299c8-118">**✔️ 执行**考虑将如何使用你的库。</span><span class="sxs-lookup"><span data-stu-id="299c8-118">**✔️ DO** think about how your library will be used.</span></span> <span data-ttu-id="299c8-119">重大更改会在应用程序和使用它的库有何影响？</span><span class="sxs-lookup"><span data-stu-id="299c8-119">What effect will breaking changes have on applications and libraries that use it?</span></span>

<span data-ttu-id="299c8-120">**✔️ 执行**时开发的低级别.NET 库的重大更改降至最低。</span><span class="sxs-lookup"><span data-stu-id="299c8-120">**✔️ DO** minimize breaking changes when developing a low-level .NET library.</span></span>

<span data-ttu-id="299c8-121">**请考虑 ✔️**发布一个较大的库作为新的 NuGet 包重写。</span><span class="sxs-lookup"><span data-stu-id="299c8-121">**✔️ CONSIDER** publishing a major rewrite of a library as a new NuGet package.</span></span>

## <a name="types-of-breaking-changes"></a><span data-ttu-id="299c8-122">类型的重大更改</span><span class="sxs-lookup"><span data-stu-id="299c8-122">Types of breaking changes</span></span>

<span data-ttu-id="299c8-123">重大更改划分为不同类别，并不是同样有影响。</span><span class="sxs-lookup"><span data-stu-id="299c8-123">Breaking changes fall into different categories and aren't equally impactful.</span></span>

### <a name="source-breaking-change"></a><span data-ttu-id="299c8-124">源项重大更改</span><span class="sxs-lookup"><span data-stu-id="299c8-124">Source breaking change</span></span>

<span data-ttu-id="299c8-125">重大更改的源不会影响程序执行，但会导致编译错误下一次重新编译应用程序。</span><span class="sxs-lookup"><span data-stu-id="299c8-125">A source breaking change doesn't affect program execution but will cause compilation errors the next time the application is recompiled.</span></span> <span data-ttu-id="299c8-126">例如，新重载会产生多义性以前，是明确的方法调用中或已重命名的参数将中断调用方使用的命名参数。</span><span class="sxs-lookup"><span data-stu-id="299c8-126">For example, a new overload can create an ambiguity in method calls that were unambiguous previously, or a renamed parameter will break callers that use named parameters.</span></span>

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

<span data-ttu-id="299c8-127">仅在开发人员重新编译其应用程序时有害的重大更改的源，因为它是破坏性最小的重大更改。</span><span class="sxs-lookup"><span data-stu-id="299c8-127">Because a source breaking change is only harmful when developers recompile their applications, it's the least disruptive breaking change.</span></span> <span data-ttu-id="299c8-128">开发人员可以轻松地解决其自己断开的源的代码。</span><span class="sxs-lookup"><span data-stu-id="299c8-128">Developers can fix their own broken source code easily.</span></span>

### <a name="behavior-breaking-change"></a><span data-ttu-id="299c8-129">行为重大更改</span><span class="sxs-lookup"><span data-stu-id="299c8-129">Behavior breaking change</span></span>

<span data-ttu-id="299c8-130">行为更改是最常见的重大更改类型： 行为中的几乎所有更改都可能会都破坏人。</span><span class="sxs-lookup"><span data-stu-id="299c8-130">Behavior changes are the most common type of breaking change: almost any change in behavior could break someone.</span></span> <span data-ttu-id="299c8-131">更改为你的库，如方法签名异常引发或输入或输出数据格式，所有产生负面影响的库使用者。</span><span class="sxs-lookup"><span data-stu-id="299c8-131">Changes to your library, such as method signatures, exceptions thrown or input or output data formats, could all negatively impact your library consumers.</span></span> <span data-ttu-id="299c8-132">如果用户依赖于以前中断的行为，bug 修复，甚至可以限定作为一项重大更改。</span><span class="sxs-lookup"><span data-stu-id="299c8-132">Even a bug fix can qualify as a breaking change if users relied on the previously broken behavior.</span></span>

<span data-ttu-id="299c8-133">添加功能和改进不良行为是件好事，但不小心的情况下它可以使它很难升级的现有用户。</span><span class="sxs-lookup"><span data-stu-id="299c8-133">Adding features and improving bad behaviors is a good thing, but without care it can make it very hard for existing users to upgrade.</span></span> <span data-ttu-id="299c8-134">于帮助开发人员处理行为的重大更改的一种方法是隐藏在设置。</span><span class="sxs-lookup"><span data-stu-id="299c8-134">One approach to helping developers deal with behavior breaking changes is to hide them behind settings.</span></span> <span data-ttu-id="299c8-135">设置可让开发人员更新到最新版本的同时选择中选择加入或选择退出的重大更改在你的库。</span><span class="sxs-lookup"><span data-stu-id="299c8-135">Settings let developers update to the latest version of your library while at the same time choosing to opt in or opt out of breaking changes.</span></span> <span data-ttu-id="299c8-136">使用此策略，同时允许其使用的代码，随着时间的推移适应保持最新的开发人员。</span><span class="sxs-lookup"><span data-stu-id="299c8-136">This strategy lets developers stay up to date while letting their consuming code adapt over time.</span></span>

<span data-ttu-id="299c8-137">例如，ASP.NET Core MVC 提供的概念[兼容性版本](/aspnet/core/mvc/compatibility-version)修改功能启用和禁用上`MvcOptions`。</span><span class="sxs-lookup"><span data-stu-id="299c8-137">For example, ASP.NET Core MVC has the concept of a [compatibility version](/aspnet/core/mvc/compatibility-version) that modifies the features enabled and disabled on `MvcOptions`.</span></span>

<span data-ttu-id="299c8-138">**请考虑 ✔️**离开的新功能默认情况下，如果它们会影响现有用户，让开发人员选择启用该功能的设置。</span><span class="sxs-lookup"><span data-stu-id="299c8-138">**✔️ CONSIDER** leaving new features off by default, if they affect existing users, and let developers opt in to the feature with a setting.</span></span>

### <a name="binary-breaking-change"></a><span data-ttu-id="299c8-139">二进制的重大更改</span><span class="sxs-lookup"><span data-stu-id="299c8-139">Binary breaking change</span></span>

<span data-ttu-id="299c8-140">更改你的库的公共 API 时发生的重大更改的二进制文件，以便根据编译的程序集的库的较旧版本将不再能够调用 API。</span><span class="sxs-lookup"><span data-stu-id="299c8-140">A binary breaking change happens when you change the public API of your library, so assemblies compiled against older versions of your library are no longer able to call the API.</span></span> <span data-ttu-id="299c8-141">例如，通过添加一个新的参数来更改方法的签名将导致针对较旧版本的库编译的程序集引发<xref:System.MissingMethodException>。</span><span class="sxs-lookup"><span data-stu-id="299c8-141">For example, changing a method's signature by adding a new parameter will cause assemblies compiled against the older version of the library to throw a <xref:System.MissingMethodException>.</span></span>

<span data-ttu-id="299c8-142">重大更改的二进制文件也会中断**整个程序集**。</span><span class="sxs-lookup"><span data-stu-id="299c8-142">A binary breaking change can also break an **entire assembly**.</span></span> <span data-ttu-id="299c8-143">重命名的程序集包含`AssemblyName`也会添加、 删除或更改程序集的强命名密钥会更改程序集的标识。</span><span class="sxs-lookup"><span data-stu-id="299c8-143">Renaming an assembly with `AssemblyName` will change the assembly's identity, as will adding, removing, or changing the assembly's strong naming key.</span></span> <span data-ttu-id="299c8-144">程序集的标识的更改将中断所有使用它的已编译的代码。</span><span class="sxs-lookup"><span data-stu-id="299c8-144">A change of an assembly's identity will break all compiled code that uses it.</span></span>

<span data-ttu-id="299c8-145">**不这样做 ❌**更改程序集名称。</span><span class="sxs-lookup"><span data-stu-id="299c8-145">**❌ DO NOT** change an assembly name.</span></span>

<span data-ttu-id="299c8-146">**不这样做 ❌**添加、 删除或更改的强命名密钥。</span><span class="sxs-lookup"><span data-stu-id="299c8-146">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

<span data-ttu-id="299c8-147">**请考虑 ✔️**使用而不接口的抽象基类。</span><span class="sxs-lookup"><span data-stu-id="299c8-147">**✔️ CONSIDER** using abstract base classes instead of interfaces.</span></span>

> <span data-ttu-id="299c8-148">向接口添加任何内容将导致它无法实现的现有类型。</span><span class="sxs-lookup"><span data-stu-id="299c8-148">Adding anything to an interface will cause existing types that implement it to fail.</span></span> <span data-ttu-id="299c8-149">一个抽象基类，可添加默认虚拟实现。</span><span class="sxs-lookup"><span data-stu-id="299c8-149">An abstract base class allows you to add a default virtual implementation.</span></span>

<span data-ttu-id="299c8-150">**请考虑 ✔️**放置<xref:System.ObsoleteAttribute>类型和想要删除的成员。</span><span class="sxs-lookup"><span data-stu-id="299c8-150">**✔️ CONSIDER** placing the <xref:System.ObsoleteAttribute> on types and members that you intend to remove.</span></span> <span data-ttu-id="299c8-151">该属性应更新代码以不能再使用已过时 API 的说明。</span><span class="sxs-lookup"><span data-stu-id="299c8-151">The attribute should have instructions for updating code to no longer use the obsolete API.</span></span>

> <span data-ttu-id="299c8-152">调用具有类型和方法的代码<xref:System.ObsoleteAttribute>将生成一个生成警告消息提供给该属性。</span><span class="sxs-lookup"><span data-stu-id="299c8-152">Code that calls types and methods with the <xref:System.ObsoleteAttribute> will generate a build warning with the message supplied to the attribute.</span></span> <span data-ttu-id="299c8-153">警告让人客户使用已过时的 API 图面上时为迁移，以便在删除过时的 API，大多数都不能再使用它。</span><span class="sxs-lookup"><span data-stu-id="299c8-153">The warnings give people who use the obsolete API surface time to migrate so that when the obsolete API is removed, most are no longer using it.</span></span>

```csharp
public class Document
{
    [Obsolete("LoadDocument(string) is obsolete. Use LoadDocument(Uri) instead.")]
    public static Document LoadDocument(string uri)
    {
        return LoadDocument(new Uri(uri));
    }

    public static Document LoadDocument(Uri uri)
    {
        // Load the document
    }
}
```

## <a name="see-also"></a><span data-ttu-id="299c8-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="299c8-154">See also</span></span>

* [<span data-ttu-id="299c8-155">C# 开发人员的版本和更新注意事项</span><span class="sxs-lookup"><span data-stu-id="299c8-155">Version and update considerations for C# developers</span></span>](../../csharp/whats-new/version-update-considerations.md)
* [<span data-ttu-id="299c8-156">在.NET 中的 API 重大更改到权威指南</span><span class="sxs-lookup"><span data-stu-id="299c8-156">A definitive guide to API-breaking changes in .NET</span></span>](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
* [<span data-ttu-id="299c8-157">CoreFX 重大更改规则</span><span class="sxs-lookup"><span data-stu-id="299c8-157">CoreFX Breaking Change Rules</span></span>](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
[<span data-ttu-id="299c8-158">上一篇</span><span class="sxs-lookup"><span data-stu-id="299c8-158">Previous</span></span>](./versioning.md)
