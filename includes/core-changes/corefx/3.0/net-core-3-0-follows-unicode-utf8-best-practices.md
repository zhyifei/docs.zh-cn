---
ms.openlocfilehash: becae23cd810623bbb33c693b707c2d4735aeece
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158460"
---
### <a name="replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines"></a><span data-ttu-id="1f7cd-101">替换格式错误的 UTF-8 字节序列将遵循 Unicode 准则</span><span class="sxs-lookup"><span data-stu-id="1f7cd-101">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>

<span data-ttu-id="1f7cd-102"><xref:System.Text.UTF8Encoding> 类在字节到字符转码操作期间遇到格式错误的 UTF-8 字节序列时，它将在输出字符串中用“�”（U+FFFD 替换字符）替换该序列。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-102">When the <xref:System.Text.UTF8Encoding> class encounters an ill-formed UTF-8 byte sequence during a byte-to-character transcoding operation, it replaces that sequence with a '�' (U+FFFD REPLACEMENT CHARACTER) character in the output string.</span></span> <span data-ttu-id="1f7cd-103">.NET Core 3.0 与以前版本的 .NET Core 和 .NET Framework 的不同之处在于，在转码操作期间按照 Unicode 最佳做法执行此替换。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-103">.NET Core 3.0 differs from previous versions of .NET Core and the .NET Framework by following the Unicode best practice for performing this replacement during the transcoding operation.</span></span>

<span data-ttu-id="1f7cd-104">这是在整个 .NET 中改进 UTF-8 处理的较大工作量（包括通过新的 <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> 和 <xref:System.Text.Rune?displayProperty=nameWithType> 类型）的一部分。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-104">This is part of a larger effort to improve UTF-8 handling throughout .NET, including by the new <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> and <xref:System.Text.Rune?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="1f7cd-105">为 <xref:System.Text.UTF8Encoding> 类型提供了改进的错误处理机制，以便生成与新引入的类型一致的输出。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-105">The <xref:System.Text.UTF8Encoding> type was given improved error handling mechanics so that it produces output consistent with the newly introduced types.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1f7cd-106">更改描述</span><span class="sxs-lookup"><span data-stu-id="1f7cd-106">Change description</span></span>

<span data-ttu-id="1f7cd-107">从 .NET Core 3.0 开始，当将字节转码为字符时，<xref:System.Text.UTF8Encoding> 类会根据 Unicode 最佳做法执行字符替换。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-107">Starting with .NET Core 3.0, when transcoding bytes to characters, the <xref:System.Text.UTF8Encoding> class performs character substitution based on Unicode best practices.</span></span> <span data-ttu-id="1f7cd-108">[Unicode 标准 12.0 版第 3.9 节 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) 的  “U+FFFD 替换最大子部分”标题中描述了使用的替换机制。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-108">The substitution mechanism used is described by [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) in the heading titled _U+FFFD Substitution of Maximal Subparts_.</span></span>

<span data-ttu-id="1f7cd-109">仅当  输入字节序列包含格式错误的 UTF-8 数据时，此行为才适用。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-109">This behavior _only_ applies when the input byte sequence contains ill-formed UTF-8 data.</span></span> <span data-ttu-id="1f7cd-110">此外，如果已通过 `throwOnInvalidBytes: true` 构造了 <xref:System.Text.UTF8Encoding> 实例，则 `UTF8Encoding` 实例将继续对无效输入引发，而不是执行 U+FFFD 替换。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-110">Additionally, if the <xref:System.Text.UTF8Encoding> instance has been constructed with `throwOnInvalidBytes: true`, the `UTF8Encoding` instance will continue to throw on invalid input rather than perform U+FFFD replacement.</span></span> <span data-ttu-id="1f7cd-111">有关 `UTF8Encoding` 构造函数的详细信息，请参阅 <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-111">For more information about the `UTF8Encoding` constructor, see <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>.</span></span>

<span data-ttu-id="1f7cd-112">下表通过无效的 3 字节输入说明了此更改的影响：</span><span class="sxs-lookup"><span data-stu-id="1f7cd-112">The following table illustrates the impact of this change with an invalid 3-byte input:</span></span>

| <span data-ttu-id="1f7cd-113">格式无效的 3 字节输入</span><span class="sxs-lookup"><span data-stu-id="1f7cd-113">Ill-formed 3-byte input</span></span> | <span data-ttu-id="1f7cd-114">.NET Core 3.0 之前的输出</span><span class="sxs-lookup"><span data-stu-id="1f7cd-114">Output before .NET Core 3.0</span></span>          | <span data-ttu-id="1f7cd-115">从 .NET Core 3.0 开始的输出</span><span class="sxs-lookup"><span data-stu-id="1f7cd-115">Output starting with .NET Core 3.0</span></span>        |
|-------------------------|--------------------------------------|-------------------------------------------|
| `[ ED A0 90 ]`          | <span data-ttu-id="1f7cd-116">`[ FFFD FFFD ]`（2 字符输出）</span><span class="sxs-lookup"><span data-stu-id="1f7cd-116">`[ FFFD FFFD ]` (2-character output)</span></span> | <span data-ttu-id="1f7cd-117">`[ FFFD FFFD FFFD ]`（3 字符输出）</span><span class="sxs-lookup"><span data-stu-id="1f7cd-117">`[ FFFD FFFD FFFD ]` (3-character output)</span></span> |

<span data-ttu-id="1f7cd-118">根据以前链接的 Unicode 标准 PDF 的表 3-9  ，此 3 字符输出为首选输出。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-118">The 3-char output is the preferred output, according to _Table 3-9_ of the previously linked Unicode Standard PDF.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1f7cd-119">引入的版本</span><span class="sxs-lookup"><span data-stu-id="1f7cd-119">Version introduced</span></span>

<span data-ttu-id="1f7cd-120">3.0</span><span class="sxs-lookup"><span data-stu-id="1f7cd-120">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1f7cd-121">建议操作</span><span class="sxs-lookup"><span data-stu-id="1f7cd-121">Recommended action</span></span>

<span data-ttu-id="1f7cd-122">开发人员一方不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="1f7cd-122">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="1f7cd-123">类别</span><span class="sxs-lookup"><span data-stu-id="1f7cd-123">Category</span></span>

<span data-ttu-id="1f7cd-124">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="1f7cd-124">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1f7cd-125">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="1f7cd-125">Affected APIs</span></span>

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
