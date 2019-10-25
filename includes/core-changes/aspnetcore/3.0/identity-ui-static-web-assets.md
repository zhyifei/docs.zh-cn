---
ms.openlocfilehash: 8d7942ef6c36c01a9ae7ae2a9739f26dfcda5813
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394359"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a><span data-ttu-id="81cba-101">标识：UI 使用静态 Web 资产功能</span><span class="sxs-lookup"><span data-stu-id="81cba-101">Identity: UI uses static web assets feature</span></span>

<span data-ttu-id="81cba-102">ASP.NET Core 3.0 引入了静态 Web 资产功能，标识 UI 已采用此功能。</span><span class="sxs-lookup"><span data-stu-id="81cba-102">ASP.NET Core 3.0 introduced a static web assets feature, and Identity UI has adopted it.</span></span>

#### <a name="change-description"></a><span data-ttu-id="81cba-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="81cba-103">Change description</span></span>

<span data-ttu-id="81cba-104">由于标识 UI 采用静态 Web 资产功能，因此：</span><span class="sxs-lookup"><span data-stu-id="81cba-104">As a result of Identity UI adopting the static web assets feature:</span></span>

- <span data-ttu-id="81cba-105">可通过使用项目文件中的 `IdentityUIFrameworkVersion` 属性来完成框架选择。</span><span class="sxs-lookup"><span data-stu-id="81cba-105">Framework selection is accomplished by using the `IdentityUIFrameworkVersion` property in your project file.</span></span>
- <span data-ttu-id="81cba-106">Bootstrap 4 是标识 UI 的默认 UI 框架。</span><span class="sxs-lookup"><span data-stu-id="81cba-106">Bootstrap 4 is the default UI framework for Identity UI.</span></span> <span data-ttu-id="81cba-107">Bootstrap 3 的生命周期已经结束，应考虑迁移到受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="81cba-107">Bootstrap 3 has reached end of life, and you should consider migrating to a supported version.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="81cba-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="81cba-108">Version introduced</span></span>

<span data-ttu-id="81cba-109">3.0</span><span class="sxs-lookup"><span data-stu-id="81cba-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="81cba-110">旧行为</span><span class="sxs-lookup"><span data-stu-id="81cba-110">Old behavior</span></span>

<span data-ttu-id="81cba-111">标识 UI 的默认 UI 框架为 Bootstrap 3  。</span><span class="sxs-lookup"><span data-stu-id="81cba-111">The default UI framework for Identity UI was **Bootstrap 3**.</span></span> <span data-ttu-id="81cba-112">可使用 `Startup.ConfigureServices` 中 `AddIdentityUI` 方法调用的参数配置 UI 框架。</span><span class="sxs-lookup"><span data-stu-id="81cba-112">The UI framework could be configured using a parameter to the `AddIdentityUI` method call in `Startup.ConfigureServices`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="81cba-113">新行为</span><span class="sxs-lookup"><span data-stu-id="81cba-113">New behavior</span></span>

<span data-ttu-id="81cba-114">标识 UI 的默认 UI 框架为 Bootstrap 4  。</span><span class="sxs-lookup"><span data-stu-id="81cba-114">The default UI framework for Identity UI is **Bootstrap 4**.</span></span> <span data-ttu-id="81cba-115">UI 框架必须在项目文件中进行配置，而不是在 `AddIdentityUI` 方法调用中配置。</span><span class="sxs-lookup"><span data-stu-id="81cba-115">The UI framework must be configured in your project file, instead of in the `AddIdentityUI` method call.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="81cba-116">更改原因</span><span class="sxs-lookup"><span data-stu-id="81cba-116">Reason for change</span></span>

<span data-ttu-id="81cba-117">采用静态 Web 资产功能要求 UI 框架配置迁移到 MSBuild。</span><span class="sxs-lookup"><span data-stu-id="81cba-117">Adoption of the static web assets feature required that the UI framework configuration move to MSBuild.</span></span> <span data-ttu-id="81cba-118">要在哪个框架上进行嵌入的决策是生成时决策，而非运行时决策。</span><span class="sxs-lookup"><span data-stu-id="81cba-118">The decision on which framework to embed is a build-time decision, not a runtime decision.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="81cba-119">建议的操作</span><span class="sxs-lookup"><span data-stu-id="81cba-119">Recommended action</span></span>

<span data-ttu-id="81cba-120">查看站点 UI，以确保新的 Bootstrap 4 组件兼容。</span><span class="sxs-lookup"><span data-stu-id="81cba-120">Review your site UI to ensure the new Bootstrap 4 components are compatible.</span></span> <span data-ttu-id="81cba-121">如有必要，请使用 `IdentityUIFrameworkVersion` MSBuild 属性还原为 Bootstrap 3。</span><span class="sxs-lookup"><span data-stu-id="81cba-121">If necessary, use the `IdentityUIFrameworkVersion` MSBuild property to revert to Bootstrap 3.</span></span> <span data-ttu-id="81cba-122">将属性添加到项目文件中的 `<PropertyGroup>` 元素：</span><span class="sxs-lookup"><span data-stu-id="81cba-122">Add the property to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="81cba-123">类别</span><span class="sxs-lookup"><span data-stu-id="81cba-123">Category</span></span>

<span data-ttu-id="81cba-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="81cba-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="81cba-125">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="81cba-125">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)`

-->
