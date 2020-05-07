---
ms.openlocfilehash: 7a05f60cf1c04d3d73dadb54541254a83b4ea855
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507064"
---
### <a name="signalr-messagepack-hub-protocol-options-type-changed"></a><span data-ttu-id="a41a7-101">SignalR：MessagePack 中心协议选项类型已更改</span><span class="sxs-lookup"><span data-stu-id="a41a7-101">SignalR: MessagePack Hub Protocol options type changed</span></span>

<span data-ttu-id="a41a7-102">ASP.NET Core SignalR MessagePack 中心协议选项类型已从 `IList<MessagePack.IFormatterResolver>` 更改为 [MessagePack](https://www.nuget.org/packages/MessagePack) 库的 `MessagePackSerializerOptions` 类型。</span><span class="sxs-lookup"><span data-stu-id="a41a7-102">The ASP.NET Core SignalR MessagePack Hub Protocol options type has changed from `IList<MessagePack.IFormatterResolver>` to the [MessagePack](https://www.nuget.org/packages/MessagePack) library's `MessagePackSerializerOptions` type.</span></span>

<span data-ttu-id="a41a7-103">有关此更改的讨论，请参阅 [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506)。</span><span class="sxs-lookup"><span data-stu-id="a41a7-103">For discussion on this change, see [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a41a7-104">引入的版本</span><span class="sxs-lookup"><span data-stu-id="a41a7-104">Version introduced</span></span>

<span data-ttu-id="a41a7-105">5.0 预览版 4</span><span class="sxs-lookup"><span data-stu-id="a41a7-105">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a41a7-106">旧行为</span><span class="sxs-lookup"><span data-stu-id="a41a7-106">Old behavior</span></span>

<span data-ttu-id="a41a7-107">可以添加到选项，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="a41a7-107">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="a41a7-108">并替换选项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a41a7-108">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers = new List<MessagePack.IFormatterResolver>()
        {
            MessagePack.Resolvers.StandardResolver.Instance
        };
    });
```

#### <a name="new-behavior"></a><span data-ttu-id="a41a7-109">新行为</span><span class="sxs-lookup"><span data-stu-id="a41a7-109">New behavior</span></span>

<span data-ttu-id="a41a7-110">可以添加到选项，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="a41a7-110">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="a41a7-111">并替换选项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a41a7-111">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions = MessagePackSerializerOptions
                .Standard
                .WithResolver(MessagePack.Resolvers.StandardResolver.Instance)
                .WithSecurity(MessagePackSecurity.UntrustedData);
    });
```

#### <a name="reason-for-change"></a><span data-ttu-id="a41a7-112">更改原因</span><span class="sxs-lookup"><span data-stu-id="a41a7-112">Reason for change</span></span>

<span data-ttu-id="a41a7-113">此更改是迁移到 MessagePack v2.x 的一部分，已在 [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404) 中公布。</span><span class="sxs-lookup"><span data-stu-id="a41a7-113">This change is part of moving to MessagePack v2.x, which was announced in [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span></span> <span data-ttu-id="a41a7-114">v2.x 库添加了一个更易于使用的选项 API，提供的功能比之前公开的 `MessagePack.IFormatterResolver` 的列表更多。</span><span class="sxs-lookup"><span data-stu-id="a41a7-114">The v2.x library has added an options API that's easier to use and provides more features than the list of `MessagePack.IFormatterResolver` that was exposed before.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a41a7-115">建议操作</span><span class="sxs-lookup"><span data-stu-id="a41a7-115">Recommended action</span></span>

<span data-ttu-id="a41a7-116">此重大更改将影响在 <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> 上配置值的用户。</span><span class="sxs-lookup"><span data-stu-id="a41a7-116">This breaking change affects anyone who is configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span> <span data-ttu-id="a41a7-117">如果使用 ASP.NET Core SignalR MessagePack 中心协议并修改这些选项，请更新用法以使用新的选项 API，如上所示。</span><span class="sxs-lookup"><span data-stu-id="a41a7-117">If you're using the ASP.NET Core SignalR MessagePack Hub Protocol and modifying the options, update your usage to use the new options API as shown above.</span></span>

#### <a name="category"></a><span data-ttu-id="a41a7-118">类别</span><span class="sxs-lookup"><span data-stu-id="a41a7-118">Category</span></span>

<span data-ttu-id="a41a7-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a41a7-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a41a7-120">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a41a7-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
