---
title: 开放源代码库指南
description: 有关创建高质量的 .NET 库的开发人员最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/17/2018
ms.openlocfilehash: ca95cb5ba1ebf27464397b7850ac02aabded1a5b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188620"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="bc623-103">开放源代码库指南</span><span class="sxs-lookup"><span data-stu-id="bc623-103">Open-source library guidance</span></span>

<span data-ttu-id="bc623-104">本指南向开发人员提供了有关创建高质量的 .NET 库的建议。</span><span class="sxs-lookup"><span data-stu-id="bc623-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="bc623-105">本文档重点介绍在构建 .NET 库时的操作内容和原因，还不是操作方式.。</span><span class="sxs-lookup"><span data-stu-id="bc623-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="bc623-106">有关优质开源 .NET 库的方方面面：</span><span class="sxs-lookup"><span data-stu-id="bc623-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="bc623-107">包容性 - 优秀的 .NET 库致力于支持众多平台、编程语言和应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc623-107">**Inclusive** - Good .NET libraries strive to support many platforms, programming languages, and applications.</span></span>
> * <span data-ttu-id="bc623-108">稳定性：优秀的 .NET 系统在具有众多库的应用程序中运行的 .NET 生态系统中共存。</span><span class="sxs-lookup"><span data-stu-id="bc623-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="bc623-109">设计为可改进：.NET 库要随着时间的推移进行改进和演变，同时支持现有用户。</span><span class="sxs-lookup"><span data-stu-id="bc623-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="bc623-110">可调试：.NET 库要使用最新的工具，为用户打造卓越的调试体验。</span><span class="sxs-lookup"><span data-stu-id="bc623-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="bc623-111">受信任：.NET 库通过安全最佳做法发布到 NuGet，备受开发人员的信赖。</span><span class="sxs-lookup"><span data-stu-id="bc623-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bc623-112">入门</span><span class="sxs-lookup"><span data-stu-id="bc623-112">Get Started</span></span>](./get-started.md)

## <a name="types-of-recommendations"></a><span data-ttu-id="bc623-113">建议类型</span><span class="sxs-lookup"><span data-stu-id="bc623-113">Types of recommendations</span></span>

<span data-ttu-id="bc623-114">每篇文章介绍四种类型的建议：“请执行”、“请考虑”、、“请避免”、和“请勿”。</span><span class="sxs-lookup"><span data-stu-id="bc623-114">Each article presents four types of recommendations: **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="bc623-115">建议类型表示了应遵循的程度。</span><span class="sxs-lookup"><span data-stu-id="bc623-115">The type of recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="bc623-116">应始终遵循“请执行”建议。</span><span class="sxs-lookup"><span data-stu-id="bc623-116">You should almost always follow a **Do** recommendation.</span></span> <span data-ttu-id="bc623-117">例如:</span><span class="sxs-lookup"><span data-stu-id="bc623-117">For example:</span></span>

<span data-ttu-id="bc623-118">✔️请通过 NuGet 包分发库。</span><span class="sxs-lookup"><span data-stu-id="bc623-118">**✔️ DO** distribute your library using a NuGet package.</span></span>

<span data-ttu-id="bc623-119">在另一方面，“请考虑”建议是在一般情况下要遵循的建议，但存在该规则的合法例外，此时不遵循指南也不妨：</span><span class="sxs-lookup"><span data-stu-id="bc623-119">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="bc623-120">✔️请考虑使用 [SemVer 2.0.0](https://semver.org/) 控制 NuGet 包的版本。</span><span class="sxs-lookup"><span data-stu-id="bc623-120">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="bc623-121">“请避免”建议是指在一般情况下不应执行的操作，但有时也可以打破规则：</span><span class="sxs-lookup"><span data-stu-id="bc623-121">**Avoid** recommendations mention things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="bc623-122">❌请避免使用需要确切版本的 NuGet 包引用。</span><span class="sxs-lookup"><span data-stu-id="bc623-122">**❌ AVOID** NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="bc623-123">最后，“请勿”建议是指在大多数情况下不得执行的操作：</span><span class="sxs-lookup"><span data-stu-id="bc623-123">And finally, **Do not** recommendations indicate something you should almost never do:</span></span>

<span data-ttu-id="bc623-124">❌请勿发布库的强名称或非强名称版本。</span><span class="sxs-lookup"><span data-stu-id="bc623-124">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="bc623-125">例如，`Contoso.Api` 和 `Contoso.Api.StrongNamed`。</span><span class="sxs-lookup"><span data-stu-id="bc623-125">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="bc623-126">下一篇</span><span class="sxs-lookup"><span data-stu-id="bc623-126">Next</span></span>](./get-started.md)
