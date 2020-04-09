---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391177"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a><span data-ttu-id="75701-101">静态文件：CSV 内容类型已更改为符合标准</span><span class="sxs-lookup"><span data-stu-id="75701-101">Static files: CSV content type changed to standards-compliant</span></span>

<span data-ttu-id="75701-102">在 ASP.NET Core 5.0 中，[静态文件中间件](/aspnet/core/fundamentals/static-files)用于 .csv  文件的默认 `Content-Type` 响应标头值已更改为符合标准的值 `text/csv`。</span><span class="sxs-lookup"><span data-stu-id="75701-102">In ASP.NET Core 5.0, the default `Content-Type` response header value that the [Static File Middleware](/aspnet/core/fundamentals/static-files) uses for *.csv* files has changed to the standards-compliant value `text/csv`.</span></span>

<span data-ttu-id="75701-103">有关此问题的讨论，请参阅 [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385)。</span><span class="sxs-lookup"><span data-stu-id="75701-103">For discussion on this issue, see [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="75701-104">引入的版本</span><span class="sxs-lookup"><span data-stu-id="75701-104">Version introduced</span></span>

<span data-ttu-id="75701-105">5.0 预览版 1</span><span class="sxs-lookup"><span data-stu-id="75701-105">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="75701-106">旧行为</span><span class="sxs-lookup"><span data-stu-id="75701-106">Old behavior</span></span>

<span data-ttu-id="75701-107">使用 `Content-Type` 标头值 `application/octet-stream`。</span><span class="sxs-lookup"><span data-stu-id="75701-107">The `Content-Type` header value `application/octet-stream` was used.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="75701-108">新行为</span><span class="sxs-lookup"><span data-stu-id="75701-108">New behavior</span></span>

<span data-ttu-id="75701-109">使用 `Content-Type` 标头值 `text/csv`。</span><span class="sxs-lookup"><span data-stu-id="75701-109">The `Content-Type` header value `text/csv` is used.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="75701-110">更改原因</span><span class="sxs-lookup"><span data-stu-id="75701-110">Reason for change</span></span>

<span data-ttu-id="75701-111">符合 [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) 标准。</span><span class="sxs-lookup"><span data-stu-id="75701-111">Compliance with the [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) standard.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="75701-112">建议操作</span><span class="sxs-lookup"><span data-stu-id="75701-112">Recommended action</span></span>

<span data-ttu-id="75701-113">如果此更改影响你的应用，则可以自定义文件扩展名到 MIME 类型的映射。</span><span class="sxs-lookup"><span data-stu-id="75701-113">If this change impacts your app, you can customize the file extension-to-MIME type mapping.</span></span> <span data-ttu-id="75701-114">若要还原到 `application/octet-stream` MIME 类型，请在 `Startup.Configure` 中修改 <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> 方法调用。</span><span class="sxs-lookup"><span data-stu-id="75701-114">To revert to the `application/octet-stream` MIME type, modify the <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> method call in `Startup.Configure`.</span></span> <span data-ttu-id="75701-115">例如：</span><span class="sxs-lookup"><span data-stu-id="75701-115">For example:</span></span>

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

<span data-ttu-id="75701-116">有关自定义映射的详细信息，请参阅 [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider)。</span><span class="sxs-lookup"><span data-stu-id="75701-116">For more information on customizing the mapping, see [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span></span>

#### <a name="category"></a><span data-ttu-id="75701-117">类别</span><span class="sxs-lookup"><span data-stu-id="75701-117">Category</span></span>

<span data-ttu-id="75701-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="75701-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="75701-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="75701-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
