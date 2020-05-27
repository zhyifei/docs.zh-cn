---
ms.openlocfilehash: 8c8e87c885c99d28aa9a7a5d5a2b48c80d40d7db
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721580"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a><span data-ttu-id="03c7f-101">ZipArchiveEntry 不再处理具有不一致条目大小的存档</span><span class="sxs-lookup"><span data-stu-id="03c7f-101">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>

<span data-ttu-id="03c7f-102">Zip 存档在中央目录和本地标头中列出压缩的大小和未压缩的大小。</span><span class="sxs-lookup"><span data-stu-id="03c7f-102">Zip archives list both compressed size and uncompressed size in the central directory and local header.</span></span>  <span data-ttu-id="03c7f-103">条目数据本身还指示其大小。</span><span class="sxs-lookup"><span data-stu-id="03c7f-103">The entry data itself also indicates its size.</span></span>  <span data-ttu-id="03c7f-104">在 .NET Core 2.2 及更早版本中，永远不会对这些值进行一致性检查。</span><span class="sxs-lookup"><span data-stu-id="03c7f-104">In .NET Core 2.2 and earlier versions, these values were never checked for consistency.</span></span> <span data-ttu-id="03c7f-105">从 .NET Core 3.0 开始，对它们进行一致性检查。</span><span class="sxs-lookup"><span data-stu-id="03c7f-105">Starting with .NET Core 3.0, they now are.</span></span>

#### <a name="change-description"></a><span data-ttu-id="03c7f-106">更改描述</span><span class="sxs-lookup"><span data-stu-id="03c7f-106">Change description</span></span>

<span data-ttu-id="03c7f-107">在 .NET Core 2.2 及更早版本中，即使本地标头与 zip 文件的中央标头不一致，<xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> 也会成功。</span><span class="sxs-lookup"><span data-stu-id="03c7f-107">In .NET Core 2.2 and earlier versions, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> succeeds even if the local header disagrees with the central header of the zip file.</span></span> <span data-ttu-id="03c7f-108">即使数据长度超出了中央目录/本地标头中列出的未压缩文件大小，数据也会一直进行解压缩，直到达到压缩流的末尾。</span><span class="sxs-lookup"><span data-stu-id="03c7f-108">Data is decompressed until the end of the compressed stream is reached, even if its length exceeds the uncompressed file size listed in the central directory/local header.</span></span>

<span data-ttu-id="03c7f-109">从 .NET Core 3.0 开始，<xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> 方法会检查本地标头和中央标头是否在条目的压缩大小和未压缩大小方面保持一致。</span><span class="sxs-lookup"><span data-stu-id="03c7f-109">Starting with .NET Core 3.0, the <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> method checks that local header and central header agree on compressed and uncompressed sizes of an entry.</span></span>  <span data-ttu-id="03c7f-110">如果不是这样，则该方法在存档的本地标头和/或数据描述符列表大小与 zip 文件的中央目录不一致时会引发 <xref:System.IO.InvalidDataException>。</span><span class="sxs-lookup"><span data-stu-id="03c7f-110">If they do not, the method throws an <xref:System.IO.InvalidDataException> if the archive's local header and/or data descriptor list sizes that disagree with the central directory of the zip file.</span></span> <span data-ttu-id="03c7f-111">当读取条目时，解压缩的数据将被截断为标头中列出的未压缩文件大小。</span><span class="sxs-lookup"><span data-stu-id="03c7f-111">When reading an entry, decompressed data is truncated to the uncompressed file size listed in the header.</span></span>

<span data-ttu-id="03c7f-112">进行此更改是为了确保 <xref:System.IO.Compression.ZipArchiveEntry> 正确表示其数据的大小并且只读取该数据量。</span><span class="sxs-lookup"><span data-stu-id="03c7f-112">This change was made to ensure that a <xref:System.IO.Compression.ZipArchiveEntry> correctly represents the size of its data and that only that amount of data is read.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="03c7f-113">引入的版本</span><span class="sxs-lookup"><span data-stu-id="03c7f-113">Version introduced</span></span>

<span data-ttu-id="03c7f-114">3.0</span><span class="sxs-lookup"><span data-stu-id="03c7f-114">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="03c7f-115">建议操作</span><span class="sxs-lookup"><span data-stu-id="03c7f-115">Recommended action</span></span>

<span data-ttu-id="03c7f-116">对出现这些问题的所有 zip 存档重新打包。</span><span class="sxs-lookup"><span data-stu-id="03c7f-116">Repackage any zip archive that exhibits these problems.</span></span>

#### <a name="category"></a><span data-ttu-id="03c7f-117">类别</span><span class="sxs-lookup"><span data-stu-id="03c7f-117">Category</span></span>

<span data-ttu-id="03c7f-118">CoreFx</span><span class="sxs-lookup"><span data-stu-id="03c7f-118">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="03c7f-119">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="03c7f-119">Affected APIs</span></span>

- <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:System.IO.Compression.ZipArchiveEntry.Open`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A`
`Overload:System.IO.Compression.ZipFile.ExtractToDirectory%2A`

-->
