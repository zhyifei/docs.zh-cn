---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394346"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a><span data-ttu-id="1dc7f-101">标识：已更改 UI 的默认 Bootstrap 版本</span><span class="sxs-lookup"><span data-stu-id="1dc7f-101">Identity: Default Bootstrap version of UI changed</span></span>

<span data-ttu-id="1dc7f-102">从 ASP.NET Core 3.0 开始，标识 UI 默认为使用 Bootstrap 版本 4。</span><span class="sxs-lookup"><span data-stu-id="1dc7f-102">Starting in ASP.NET Core 3.0, Identity UI defaults to using version 4 of Bootstrap.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1dc7f-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="1dc7f-103">Version introduced</span></span>

<span data-ttu-id="1dc7f-104">3.0</span><span class="sxs-lookup"><span data-stu-id="1dc7f-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1dc7f-105">旧行为</span><span class="sxs-lookup"><span data-stu-id="1dc7f-105">Old behavior</span></span>

<span data-ttu-id="1dc7f-106">`services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` 方法调用以前与 `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);` 相同</span><span class="sxs-lookup"><span data-stu-id="1dc7f-106">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call was the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1dc7f-107">新行为</span><span class="sxs-lookup"><span data-stu-id="1dc7f-107">New behavior</span></span>

<span data-ttu-id="1dc7f-108">`services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` 方法调用现在与 `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);` 相同</span><span class="sxs-lookup"><span data-stu-id="1dc7f-108">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call is the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1dc7f-109">更改原因</span><span class="sxs-lookup"><span data-stu-id="1dc7f-109">Reason for change</span></span>

<span data-ttu-id="1dc7f-110">在 ASP.NET Core 3.0 时间范围内发布了 Bootstrap 4。</span><span class="sxs-lookup"><span data-stu-id="1dc7f-110">Bootstrap 4 was released during ASP.NET Core 3.0 timeframe.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1dc7f-111">建议的操作</span><span class="sxs-lookup"><span data-stu-id="1dc7f-111">Recommended action</span></span>

<span data-ttu-id="1dc7f-112">如果使用默认标识用户界面并将其添加到 `Startup.ConfigureServices` 中，则会受到此更改的影响，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="1dc7f-112">You're impacted by this change if you use the default Identity UI and have added it in `Startup.ConfigureServices` as shown in the following example:</span></span>

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

<span data-ttu-id="1dc7f-113">请执行以下一项操作：</span><span class="sxs-lookup"><span data-stu-id="1dc7f-113">Take one of the following actions:</span></span>

- <span data-ttu-id="1dc7f-114">迁移应用，以使用其[迁移指南](https://getbootstrap.com/docs/4.0/migration)来使用 Bootstrap 4。</span><span class="sxs-lookup"><span data-stu-id="1dc7f-114">Migrate your app to use Bootstrap 4 using their [migration guide](https://getbootstrap.com/docs/4.0/migration).</span></span>
- <span data-ttu-id="1dc7f-115">更新 `Startup.ConfigureServices` 以强制使用 Bootstrap 3。</span><span class="sxs-lookup"><span data-stu-id="1dc7f-115">Update `Startup.ConfigureServices` to enforce usage of Bootstrap 3.</span></span> <span data-ttu-id="1dc7f-116">例如:</span><span class="sxs-lookup"><span data-stu-id="1dc7f-116">For example:</span></span>

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a><span data-ttu-id="1dc7f-117">类别</span><span class="sxs-lookup"><span data-stu-id="1dc7f-117">Category</span></span>

<span data-ttu-id="1dc7f-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1dc7f-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1dc7f-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="1dc7f-119">Affected APIs</span></span>

<span data-ttu-id="1dc7f-120">无</span><span class="sxs-lookup"><span data-stu-id="1dc7f-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
